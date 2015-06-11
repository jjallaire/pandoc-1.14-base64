
This repo documents a potential bug in base64 encoding in pandoc 1.14. 

The `test.md` file attempts to include `bootstrap.min.css` using a `<style>` tag. The `test.sh` file calls pandoc on this file with the `--self-contained` flag. I observe different results depending on whether I use pandoc 1.13.2 or pandoc 1.14.1:

* In pandoc 1.13.2 the CSS file is fully inlined as base64 content and all boostrap styles are applied to the content (i.e. the background of the code blocks is shaded). The size of this file is 385.5 KB.


* In pandoc 1.14.1 it looks like only part of the CSS file is inlined (the size of the generated HTML file is 78.5 KB). Not surprisingly the bootstrap styles are not applied to the code blocks (there is no background shading).

