## 2026-07-14 - DOM-based XSS in Dynamic Gallery Rendering
**Vulnerability:** The project gallery was using `innerHTML +=` to inject project data (titles, descriptions, and image paths) into the modal DOM. This pattern is susceptible to DOM-based XSS if the underlying data source is ever compromised or contains unsanitized user-controlled input.
**Learning:** In static sites using vanilla JavaScript for "dynamic" feel, `innerHTML` is often the first choice for convenience, but it introduces significant security risks by parsing strings as HTML.
**Prevention:** Strictly enforce the use of `document.createElement()`, `replaceChildren()`, and direct attribute/property assignments (`textContent`, `src`, `className`) for all dynamic DOM updates.
