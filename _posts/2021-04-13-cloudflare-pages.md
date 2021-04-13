---
layout: article
title: Cloudflare Pages Review
date: 2021-04-13
published: false
---
TLDR: Good, but won't switch

[Cloudflare Pages](https://pages.cloudflare.com), a new static site hosting platform, is now [generally available]. I decided to give it a try. Here are my thoughts.

## Getting started

The only way to use Cloudflare pages is to use a linked GitHub Repository. GitLab, self hosted git, or uploads are not supported. Once you add the github app, you can deploy any repo with a static site. 
When you select a repository, however, there is no search feature. You must look through all repos to find the one you want.
![selecting repo](/uploads/cf/repos.jpeg)

Then, you select a subdomain of `*.pages.dev`, and the build commands. There is a drop-down menu to select from the most common frameworks.
![configuring](/uploads/cf/config.jpeg)

## Build

Compared to Netlify, the build takes quite a while. Updating one word on one post took 5:28. For some reason, Hugo was installed, even though my site uses Jekyll.
