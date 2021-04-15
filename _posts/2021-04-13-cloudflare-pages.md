---
layout: article
title: Cloudflare Pages Mini Review
date: 2021-04-14
published: true
---
TLDR: Pretty good, but I won't switch.

[Cloudflare Pages](https://pages.cloudflare.com), a new static site hosting platform, is now [generally available](https://blog.cloudflare.com/cloudflare-pages-ga/). I decided to give it a try. Here are my thoughts.

## Getting started

The only way to use Cloudflare pages is to use a linked GitHub Repository. GitLab, self hosted git, or uploads are not supported. Once you add the GitHub app, you can deploy any repo with a static site. 
When you select a repository, however, there is no search feature. You must look through all repos to find the one you want.
![selecting repo](/uploads/cf/repos.jpeg)

Then, you select a subdomain of `*.pages.dev`, and the build commands. There is a drop-down menu to select from the most common frameworks. All of the ones that I could think of were included, but if you use something else, you can type a custom command.
![configuring](/uploads/cf/config.jpeg)

## Build

Compared to Netlify, the build takes quite a while. Updating one word on one post took 5:28.  Netlify takes 28s to build and a total of 43.077174914s for the same change. For some reason, Hugo was installed, even though my site uses Jekyll.
![build](/uploads/cf/build.jpeg)

## Analytics and other features

Cloudflare has built-in free analytics, which are supposedly privacy-friendly. On Netlify, you must pay a seperate fee ($9/month/site), or provide your own. I use [GoatCounter](https://www.goatcounter.com). Cloudflare's solution seems pretty comprehensive. It also measures core web vitals, which I found interesting. My main website was getting several views every minute from Boing Boing and Hacker News, so I decided to try it out there. It was interesting to see, for example, which countries use which operating systems, and that my page loads slower in Brazil. You can see the [Cloudflare dashboard here](/uploads/cf/cfa.png) and the [Goatcounter dashboard here](https://lukesempire.goatcounter.com).  Besides that, Netlify has much more features, such as forms, identity, large media support, and snippet injection, which are not supported by Cloudflare. This is to be expected, as static site hosting is Netlify's buisiness, but Cloudflare's new side project.

## It's Cloudflare, so...

According to w3techs, [16.4% of the web uses Cloudflare](https://w3techs.com/technologies/details/cn-cloudflare). I don't want to make the web more centralized than it already is, and I am considering taking my site self-hosted sometime. I also don't need every reader to enter a captcha. I want it to be usable for people using tor. And I don't want to [ruin the internet for non-first world countries](https://www.slashgeek.net/2016/05/17/cloudflare-is-ruining-the-internet-for-me/).  I know these are arguments against their proxy, but they seem to apply to their pages as well.

## Pricing and limits
[There is unlimited bandwidth on all plans, and 1 concurrent build, with a limit of 500 builds per month. You can upgrade to $20/mo or $200/mo to increase this.](https://pages.cloudflare.com/#pricing)

## Summary
I won't be switching to Cloudflare Pages, but if I have a high traffic, low update project, I might consider it. If this applies to you, and you are fine with Cloudflare, then this might be a good choice.
