---
layout: post
title: Anatomy of jackhsullivan.com
subtitle: The public stuff I have on my personal domain
---

This is mostly for myself, but, if you're interested, this page documents a lot of the infrastructure that I've built around my personal domain, `jackhsullivan.com`.

## Overview

I use AWS Route 53 to handle the traffic through my domain. These are the main records (roughly what I see on the AWS console):

| **Name**                | **Type** | **Value**    |
| ----------------------- | -------- | ------------ |
| jackhsullivan.com       | A        | EC2 Instance |
| jackhsullivan.com       | MX       | Gmail        |
| pages.jackhsullivan.com | CNAME    | GitHub Pages |
| s3.jackhsullivan.com    | A        | S3 Bucket    |

{: .box-note}
**Note:** I have a couple other records for subdomains which all point to my EC2 instance, which has a few docker containers running web frontends.

This setup gives me pretty much everything I want. I experimented with nextcloud for document hosting but it was pretty shit so I'm sticking with Google Drive.

## Future Plans

I have a couple ideas for expanding my network which I might look into at some point:

- `auth.jackhsullivan.com` - An authentication server that I can reuse for future projects that supports stuff like OAuth and express-session
- `jupyter.jackhsullivan.com` - Some self-hosted jupyter notebook thing like jupyterhub
