## 2025-05-14 - Subresource Integrity (SRI) Constraints with Tailwind Play CDN
**Vulnerability:** Lack of integrity checks on external CDN assets.
**Learning:** While SRI is essential for static assets like Font Awesome, it cannot be applied to the Tailwind Play CDN (`cdn.tailwindcss.com`) because the script is dynamic and changes frequently. Attempting to add SRI or certain CORS attributes (`crossorigin="anonymous"`) to the Tailwind Play script can break styling or cause loading failures depending on the protocol used (e.g., `file://` vs `http://`).
**Prevention:** Use SRI for static versioned assets (like Font Awesome 6.0.0). For Tailwind, move to a build-time CSS generation process in the future to eliminate the dependency on a dynamic CDN script and allow for strict CSP/SRI.
