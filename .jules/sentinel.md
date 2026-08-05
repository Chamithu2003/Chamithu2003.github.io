## 2026-08-05 - Hardening Dynamic Project Modals against DOM-based XSS

**Vulnerability:**
The web application uses static HTML (`gallery.html`) but dynamically renders a project detail modal using a JavaScript database containing project metadata. This metadata included list of image paths (`projects[id].images`) which were iterated over and directly concatenated into the gallery modal's image grid container using `innerHTML`. This posed a potential DOM-based Cross-Site Scripting (XSS) vulnerability if any of the project objects or image sources were manipulated or loaded dynamically from external inputs in the future.

**Learning:**
Using `innerHTML` to dynamically construct HTML elements from arrays of strings is a risky pattern, even in simple static sites. Furthermore, this repository uses CRLF (`\r\n`) line endings and deep indentation (e.g. 16 spaces for attributes) which makes exact-match search-and-replace tools fail. Utilizing targeted Python byte-string reading/writing scripts is highly effective to make precise modifications without corrupting formatting.

**Prevention:**
Always construct elements programmatically using safe browser APIs like `document.createElement()`, `element.className`, and programmatic property assignment before appending to the DOM tree. Never concatenate untrusted strings into `innerHTML`.
