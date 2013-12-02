---
layout: post

title: We need a web content spec
permalink: /articles/we-need-a-web-content-spec/

excerpt: "I think we are missing an essential spec for web content"

categories:
  - Thoughts

author: 
  name: Sathish
  twitter: sathishmanohar
  bio: Co-founder Invoice Jet and Work Life
  image: sathish.png

---
Its been a pain for me choosing a work flow to write web content. Most of the content editors out there are word processors. Problem is word processors were designed a few decades before. The main use case for word processors is to make a digital document which at some point is outputted to a paper, Good old Paper. Word processors are fine for people, who are still involved in computer to paper work flow.

But for someone like me, who almost only writes for web, word processors completely irrelevant. It even seems weird and archaic when I open a word processor for web content. The markup generated my these word processors are mostly garbage. All I care about is content in a schematic markup ready to be pushed to live web.

## Markdown
Markdown is the most popular plain text to HTML converter. Markdown is tremendously helpful if you only use the elements markdown supports without utilizing the full power of HTML elements. I love [Markdown] [1]. In fact I'm writing this in markdown. But, markdown is not without its limitations. For example there is no clear way to represent tabular data in markdown. It is well known that lack of coverage for web content spectrum has created many variants of markdown and implementation issues for many projects and developers and there were attempts to create an unified [markdown spec] [2].

## Need for Content Spec
I feel instead of focusing our efforts on markdown spec, It would be much more beneficial for the wider community if there were a web content spec. It could be a subset of HTML with only elements that are designed for consumption rather than creation or interaction.

## HTML for consumption
Although HTML is one of the most solid specs out there, It has moved quite a bit from the original document (only) model, adding lot of features for the modern web, while I certainly like color pickers and date pickers to be part of HTML. It has moved much farther from the document for consumption approach. This creates a need for a spec that only has the elements mostly used for consumption. The kind of markup that can be pasted anywhere and should just work.

## What can a spec do
A spec like this will help a great deal for the development of text to HTML syntaxes, Web content editors, and tool sets surrounding content creation for web. Having a spec can finally give a basement for third parties to develop tools for web content creation and will tremendously improve the overall experience for developing content for the web. Web content spec will be to content, what RSS is to web content distribution.

[1]: http://daringfireball.net/projects/markdown/	"MarkDown Project"
[2]: http://www.codinghorror.com/blog/2012/10/the-future-of-markdown.html	"The Future of Markdown"
