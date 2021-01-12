---
title: Netlify DNS Review
date: 2021-01-11
descripion: I recently swiched my domain to Netlify DNS. Here is my review.
layout: article
published: true
---
## Setup
Setup was very easy; all you need to do is input your domain name and change your name servers. You could also register a domain through the Netlify UI, but the price was more than Namecheap. The dns servers are from NS1. There also was an option to add records before transferring servers, so that emails, etc. would never be interrupted. <br>
<img src="/uploads/image4.jpeg" width="300" alt="adding the domain"><br><img src="/uploads/image2.jpg" width="300" alt="Adding records"><br><img src="/uploads/image0.jpeg" width="300" alt="adding dns records><br>

## Supported Records
- A
- AAAA
- ALIAS
- CAA
- CNAME
- MX
- NS
- SPF
- SRV
- TXT


As you can see, Netlify DNS is not only for Netlify-hosted sites, but there are many extra features for Netlify.
Namecheap's dns service has an option to redirect subdomains. Netlify does not have this in the DNS interface, but it is still possible with ` _redirects`.
## Summary
It is nice to have a clean interface without constant upsells. I am not sure if there is a limit on records, but it does not appear so. I recommend it if you are already using Netlify, and will continue to use it.

### Pros
- Free ($)
- Seems fast to propagate
- Easy to use on and off Netlify
- Better load balancing
- Branch subdomains and other features
- Uninterrupted switching
### Cons 
- Not as many features as Cloudflare
- Tell me! I am not a DNS expert.

 
