# gulp-inline-string
Inline file content into js file as string.

# Usage
use __inline(filePath) to inline content to js file(Only relative path support);

# Example
var tpl = __inline("./content.tpl") ==> var tpl = "{content in file}"