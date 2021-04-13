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

Then, you select a subdomain of `*.pages.dev`, and the build commands. There is a drop-down menu to select from the most common frameworks. All of the ones that I could think of were included, but if you use something else, you can type a custom command.
![configuring](/uploads/cf/config.jpeg)

## Build

Compared to Netlify, the build takes quite a while. Updating one word on one post took 5:28. For some reason, Hugo was installed, even though my site uses Jekyll.
![build](/uploads/cf/build.jpeg)

## Analytics and other features

Cloudflare has built-in free analytics, which are supposedly privacy-friendly. On Netlify, you must pay a seperate fee ($9/month/site), or provide your own. I use [GoatCounter](https://www.goatcounter.com). Cloudflare's solution seems pretty comprehensive. It also measures core web vitals, which I found interesting. My main website was getting several views every minute from Boing Boing and Hacker News, so I decided to try it out there. It was interesting to see, for example, which countries use which operating systems, and that my page loads slower in Brazil. You can see the [Cloudflare dashboard here](/uploads/cf/cf.pdf) and the [Goatcounter dashboard here](https://lukesempire.goatcounter.com).  Besides that, Netlify has much more features, such as 

