## Insp3ct0r

**Category:** Web Exploitation
**Points:** 50
**Date:** April 9, 2026
**Status:** ✅ Solved

### Challenge
A website is hiding a flag somewhere in its source code. Find it!

### Solution
The flag was split into 3 parts across the HTML, CSS, and JavaScript files.

1. Opened the challenge website in browser
2. Pressed `Ctrl + U` to view the HTML page source
3. Found part 1/3 hidden in an HTML comment:
   ```html
   <!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
   ```
4. Located the CSS file link in the HTML source and opened it
5. Found part 2/3 hidden in a CSS comment:
   ```css
   /* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
   ```
6. Located the JavaScript file link in the HTML source and opened it
7. Found part 3/3 hidden in a JS comment:
   ```javascript
   /* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?302945a7} */
   ```
8. Combined all 3 parts to form the complete flag

### What I Learned
Web developers can hide comments in HTML, CSS, and JavaScript files that are not visible on the page itself but are readable in the source code. In real-world security, sensitive information like API keys, internal notes, or credentials are sometimes accidentally left in source code comments — this is a common vulnerability.

Key tools for Web Exploitation challenges:
- `Ctrl + U` — view full HTML page source
- Browser DevTools (`F12`) → Sources tab — browse all JS and CSS files
- Look for `<!-- -->` in HTML, `/* */` in CSS and JS

### Personal Note
This one clicked immediately once I knew where to look! The trick is that the flag isn't on the visible page — it's hiding in the code behind it. Made me realize how important it is to never leave sensitive info in comments. Also "true detective or just lucky" is such a funny hidden message 😂

### Flag
```
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?302945a7}
```
