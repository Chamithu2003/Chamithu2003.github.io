## 2026-05-22 - Tab-nabbing protection on external links
**Vulnerability:** External links using `target="_blank"` without `rel="noopener noreferrer"` (Reverse Tab-nabbing).
**Learning:** Even static websites are vulnerable to security risks if they allow opened pages to control the parent page via `window.opener`.
**Prevention:** Always add `rel="noopener noreferrer"` to any link that opens in a new tab.
