---
layout: post

title: How to display web pages without HTML or PHP extension
permalink: /articles/how-to-display-web-pages-without-html-extension/

excerpt: "Apache web server settings to return web pages without HTML extension"

categories:
  - Technology
  - How To

bitcoin: 113KQJwePSu5E9ZrQhNyjskwkjfnTpRQuR

---

I've been working on plain HTML website, in which I wanted to have URLs without
the `.html` extension in the end of the URLs. It turns out its relatively easy.

In apache `.htaccess` file add the below line whereever appropriate

    Options +MultiViews

Multiview option tries to find a best match for the request received by server
But keep in mind there are priorities in how it handles files types in directories.

From what I've tested the priority is directories first then `php` and then
`html`. So lets say if you want your server to return `example.com/gallery.html`
for the request `example.com/gallery` then you should avoid having a `gallery`
directory in the same location because the directory will be prioritised and the
server will return the directory.

Likewise if you have two files one `HTML` and one `PHP`. The request without the
file extension will return `PHP` since apache by default prioritizes `PHP` over
`HTML` in Multiviews.
