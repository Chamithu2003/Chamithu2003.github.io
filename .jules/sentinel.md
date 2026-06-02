## 2026-06-02 - [Subresource Integrity (SRI) for External Assets]
**Vulnerability:** External CSS resources (Font Awesome) were loaded without integrity checks, exposing users to risks if the CDN is compromised.
**Learning:** Using 'crossorigin="anonymous"' with the Tailwind Play CDN causes CORS errors when loading via 'file://', but works correctly over HTTP.
**Prevention:** Always include SRI attributes ('integrity', 'crossorigin', 'referrerpolicy') for static external assets and verify them using a local HTTP server.
