---
layout: post

title: How to Return 503 Service Unavailable or other specific HTTP Status Code
permalink: /how-to-return-503-service-unavailable-or-other-specific-http-status-code/

excerpt: "Incorporated provides a great typography, responsive design, author details, semantic markup and more."

categories:
  - Technology

author: 
  name: Sathish
  twitter: sathishmanohar
  bio: Co-founder Invoice Jet and Work Life
  image: ks.png
---
Recently major websites like reddit and wikipedia, decided to go black in protest of SOPA. This is when a Googler joined the conversation and instructed sites to go black the right way. In short [Pierre Far][1] instructed sites to return &#8220;503 Service Unavailable&#8221; Status code, to show bots, that the website in question was taken down, intentionally and temporarily.

So, Here are the various ways to return 503 status code. You can always customize these, to any other HTTP status, as you see fit.

<!--more-->

### PHP

You can set custom headers with PHP. Just include() this piece of code in the top of the pages, you want to blackout.

{% highlight php %}
<?php
header("HTTP/1.0 503 Service Unavailable");
?>
{% endhighlight %}

### Plan HTML Websites

To return specific HTTP Status codes in a Plain HTML Site, You can edit web server config. Include the Following snippet in .htaccess file in apache to achieve the same.

{% highlight ApacheConf %}
<pre class="wp-code-highlight prettyprint"># Don't forget to turn on the rewrite engine
RewriteEngine on

# Maintenance Redirection
# Replace 555\.555\.555\.555 with your own IP address
# Uncomment first conditional to turn off the redirection
# RewriteCond %{REQUEST_URI} ^$a
# RewriteCond %{REMOTE_ADDR} !^555\.555\.555\.555$
# RewriteCond %{REMOTE_ADDR} !^127\.0\.0\.1$

# Here strike.html is the custom page, thats displayed
RewriteCond %{REQUEST_URI} !strike.html
# strike_files/ directory contains supporting files for strike.html
RewriteCond %{REQUEST_URI} !^/strike_files/

# Uncomment the below line, if you want to serve styles/ images/
# RewriteCond %{REQUEST_FILENAME} !(styles|images).+$

RewriteRule (.*) /strike.html [R=503,L]
ErrorDocument 503 /strike.html
</pre>
{% endhighlight %}

For More Explanation about the code, visit [css-tricks][2]

### Ruby On Rails

If you are Running a Ruby on Rails, Application. You can use the following snippets to set return specific HTML status codes.

For the entire application:

{% highlight ruby %}
# ApplicationController
before_filter :return_unavailable_status

private
def return_unavailable_status
render :nothing => true, :status => :service_unavailable
end
{% endhighlight %}

If you wanted a custom error page, you could do:

{% highlight ruby %}
render 'custom_unavailable_page', :status => :service_unavailable
{% endhighlight %}

If you don&#8217;t want it for specific controllers:

{% highlight ruby %}
# SomeController, where you don't want to display
# custom unavailable page
skip_before_filter :return_unavailable_status
{% endhighlight %}

Hope this Helps! <img src='http://sathishmanohar.com/wp-includes/images/smilies/icon_smile.gif' alt=':)' class='wp-smiley' /> 

Thanks for Stack Overflow user, [iWasRobbed][3] For providing snippets for Rails Version.

 [1]: https://plus.google.com/115984868678744352358/posts/Gas8vjZ5fmB
 [2]: http://css-tricks.com/snippets/htaccess/temporary-maintenance-using-mod_rewrite/
 [3]: http://stackoverflow.com/users/308315/iwasrobbed
