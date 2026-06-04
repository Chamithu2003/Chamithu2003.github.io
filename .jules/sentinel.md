## 2026-06-04 - [Subresource Integrity Verification Challenges]
**Vulnerability:** Missing Subresource Integrity (SRI) on Font Awesome CDN links.
**Learning:** Adding `crossorigin="anonymous"` (required for SRI) to CDN assets in a project that lacks a build system causes CORS failures when tested via the `file://` protocol in Playwright. This mimics a "broken" site during automated verification even if the code is correct for production deployment.
**Prevention:** Always verify security enhancements involving CORS/SRI using a local HTTP server (e.g., `python3 -m http.server`) rather than direct file access to ensure environment parity with the intended deployment target.
