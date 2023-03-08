# Storyblok Custom CKEditor Field Plugin

> A example of how to make a custom field plugin for a CKEditor RichText editor.<br>

(note: this editor uses pure html which is a security risk. you can read more here: https://softwareengineering.stackexchange.com/questions/303099/is-there-any-danger-in-rendering-user-entered-html-and-can-it-be-mitigated)

This repository doesnt go into how to set up a custom field plugin in storyblok. Checkout my TipTap plugin if you want a more step by step guide: https://github.com/SebbeJohansson/storyblok-custom-tiptap-plugin<br>
I suggest the TipTap Editor instead of the CKEditor since the TipTap Editor has a json output option which is *A LOT* safer than rendering raw html.

## Rendering the richtext
Since this editor returns the richtext as html, you need to use some way to render it. Never trust user generated html. Make sure to take the necessary steps to prevent any foulplay.
### Vue
Render the html using `v-html`, but keep in [mind the risks](https://vuejs.org/guide/best-practices/security.html#potential-dangers).<br>
How to render html with vue - https://vuejs.org/guide/essentials/template-syntax.html#raw-html<br>
Built in v-html directive - https://vuejs.org/api/built-in-directives.html#v-html<br>
### React
Render the html using `dangerouslySetInnerHTML`, but keep in [mind the risks](https://stackoverflow.com/questions/26158874/why-does-react-js-api-warn-against-inserting-raw-html).<br>
How to render html with react - https://stackoverflow.com/questions/27934238/rendering-raw-html-with-reactjs<br>
Built in dangerouslySetInnerHTML feature - https://reactjs.org/docs/dom-elements.html#dangerouslysetinnerhtml<br>
### JS
Render the html using `Element.innerHTML`, but keep in [mind the risks](https://www.dhairyashah.dev/posts/why-innerhtml-is-a-bad-idea-and-how-to-avoid-it/#:~:text=How%20innerHTML%20can%20be%20dangerous%3F).<br>
How to render html with javascript - https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML<br>
### PHP
Render the html using `echo` or similar printing function, but keep in [mind the risks](http://htmlpurifier.org/#:~:text=and%20other%20downloads...-,Background,-There%20are%20a).<br>
How to render html with echo - https://www.php.net/manual/en/function.echo.php<br>
Strip html tags - https://www.php.net/manual/en/function.strip-tags.php<br>

### Others
Pretty much everything can render html. Just google.

## Customize CKEditor
Configuration - https://ckeditor.com/docs/ckeditor5/latest/installation/getting-started/configuration.html<br>
Plugins - https://ckeditor.com/docs/ckeditor5/latest/installation/plugins/plugins.html


*Am I irresponsible for even doing this? maybe...*
