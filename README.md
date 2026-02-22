# DNS Shield: Edge-Compatible DoH Resolver

DNS Shield is a high-performance, serverless DNS-over-HTTPS (DoH) resolver and ad-blocker deployed on Cloudflare's global edge network. It intercepts and neutralizes advertising, tracking, and malware domains at the network level, providing enhanced privacy and reduced bandwidth consumption across all connected applications.

## Features

- **Advanced Domain Filtering:** Aggregates high-reputation blocklists from Steven Black and OISD to provide 135,000+ unique definitions.
- **Encrypted Resolution:** Implements DNS-over-HTTPS (DoH) to prevent ISP eavesdropping and DNS hijacking.
- **Security Hardening:** Includes per-IP rate limiting (150 RPM), Strict Content Security Policy (CSP), and anti-clickjacking headers.
- **Live Diagnostic Dashboard:** A custom-built interface for real-time domain analysis, activity logging, and persistent local statistics.
- **Optimized Performance:** Features multi-layer caching (V8 Isolate and Cloudflare Cache API) for sub-10ms response times.
- **Mobile & OS Ready:** Compatible with system-level DoH configurations on Linux (systemd-resolved), Android, iOS, and modern browsers.

## Live Demo

[DNS-Shield](https://dns-adblock.indresik.workers.dev/)

Visit the dashboard to test domains and see the system in action.

## API Usage

Check any domain programmatically:

`https://dns-adblock.indresik.workers.dev/api/check?domain=doubleclick.net`

## Technical Architecture

- **Platform:** Cloudflare Workers (Serverless V8 Isolates).
- **Blocklist Logic:** Utilizes a recursive subdomain matching algorithm for efficient filtering of complex domain structures.
- **Data Integrity:** Implements deduplication using JavaScript Sets to ensure minimal memory footprint while maximizing coverage.
- **Binary Handling:** Parses DNS wire format directly using Uint8Array and ArrayBuffer for standard-compliant resolution.
- **Global Distribution:** Deployed across Cloudflare's 200+ global edge locations, ensuring the resolver is always geographically close to the user.



## Why I Built This
I wanted to create a practical networking project that demonstrates serverless architecture while solving a real problem. Traditional ad blockers run in your browser, but this approach blocks ads at the DNS level, which means it can protect all devices on a network, not just web browsers.

## Implementation Details

### Security & Privacy
This project prioritizes data integrity and user privacy. By resolving DNS queries over an encrypted HTTPS tunnel, it ensures that DNS metadata remains private. The integration of OISD Small ensures a high blocking ratio with a focus on zero false positives, maintaining web functionality while stripping intrusive elements.

### Efficiency at the Edge
The resolver is designed to fit within the constraints of serverless environments. It pre-compiles blocklists into a flat JSON structure and utilizes `ctx.waitUntil` for background cache updates, ensuring that the main request path is never blocked by remote fetch operations.



## Skills Demonstrated

- **Network Security:** Implementation of DoH protocols and DNS sinkholing techniques.
- **Systems Programming:** Efficient buffer handling and binary data parsing (Uint8Array/ArrayBuffer).
- **Serverless Engineering:** Managing global state, isolate persistence, and Cloudflare-specific cache APIs.
- **Defensive Coding:** Implementing rate limiting, CORS policy enforcement, and strict security headers.
- **Performance Optimization:** Strategic deduplication and recursive string matching for high-throughput environments.

---

The entire project runs for free within Cloudflare's generous free tier limits, demonstrating that enterprise-grade security tools can be built with zero infrastructure costs.
