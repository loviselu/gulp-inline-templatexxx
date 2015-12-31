# gulp-inline-template
Inline template into js file as string or function.

# Usage
use __inline(filePath) to inline template to js file as string             (Only relative path support);
use __template(filePath) to inline ejs template to js file as function     (Only relative path support);

# Example
```html
<!-- content.tpl -->
<ul class="ul">
	<% for(var i=0;i<list.length;i++) { %>
	<li><%=list[i]%></li>
	<% } %>
</ul>
```

```js
var a = __inline("./content.tpl")
var b = __template("./content.tpl")

//after compile:
var a = "<ul class=\"ul\">\n\t<% for(var i=0;i<list.length;i++) { %>\n\t<li><%=list[i]%></li>\n\t<% } %>\n</ul>\n";
var b = function(data,escape
/**/) {
escape = escape || function (markup) {
  return markup == undefined
    ? ''
    : String(markup)
        .replace(_MATCH_HTML, encode_char);
};
var _ENCODE_HTML_RULES = {
      "&": "&amp;"
    , "<": "&lt;"
    , ">": "&gt;"
    , '"': "&#34;"
    , "'": "&#39;"
    }
  , _MATCH_HTML = /[&<>'"]/g;
function encode_char(c) {
  return _ENCODE_HTML_RULES[c] || c;
};
;
  var __output = [], __append = __output.push.bind(__output);
    ; __append("<ul class=\"ul\">\n	")
    ;  for(var i=0;i<data.list.length;i++) { 
    ; __append("\n	<li>")
    ; __append(escape(data.list[i]))
    ; __append("</li>\n	")
    ;  } 
    ; __append("\n</ul>\n")
  return __output.join("");

}
```