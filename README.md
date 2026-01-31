# DNS Ad-Blocker

A serverless DNS-level ad blocker that runs on Cloudflare's edge network. This blocks advertising and tracking domains before they reach your browser, improving privacy and page load times.

## Features

- Real-time domain filtering with 70,000+ blocked ad/tracker domains
- Live dashboard to test domains and view statistics  
- REST API for programmatic access
- Zero cost infrastructure using Cloudflare's free tier
- Deployed globally with sub-10ms response times
- Easily added to any browser as a Custom DNS

## Live Demo

[DNS-Shield](https://dns-adblock.indresik.workers.dev/)

Visit the dashboard to test domains and see the system in action.

## API Usage

Check any domain programmatically:

https://dns-adblock.indresik.workers.dev/api/check?domain=doubleclick.net

## Technical Details
- Built with Cloudflare Workers (serverless platform)

- Written in modern JavaScript

- Blocks 70,000+ advertising and tracking domains

- Zero infrastructure costs - runs entirely on free tier

- Deployed across 200+ global edge locations

- Typically responds in under 10ms

## Why I Built This
I wanted to create a practical networking project that demonstrates serverless architecture while solving a real problem. Traditional ad blockers run in your browser, but this approach blocks ads at the DNS level, which means it can protect all devices on a network, not just web browsers.

## Skills Demonstrated
- Cloudflare Workers and serverless deployment

- REST API design and implementation

- DNS and network security concepts

- JavaScript development

- Performance optimization for edge computing

The entire project runs for free within Cloudflare's generous free tier limits.
