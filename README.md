dapplo.github.io
================

dapplo .NET website

## Single-page tools

Put standalone HTML files in `tools/` to publish them at `/tools/<filename>.html`.
For a completely self-contained tool, omit Jekyll front matter; Jekyll copies the
file unchanged, without a layout or Liquid processing. For example, the
volunteer wheel is available at `/tools/WheelOfVolunteer.html`.

To use Jekyll includes instead, add front matter and explicitly disable the
layout, then include fragments from `_includes/`. Set a permalink to keep the
`.html` URL, since the site's default permalink uses directory URLs:

```html
---
layout: null
permalink: /tools/my-tool.html
---
<!doctype html>
<html lang="en">
<head><meta charset="utf-8"><title>My tool</title></head>
<body>
{% include my-tool-fragment.html %}
</body>
</html>
```

Jekyll renders the include at build time; any scripts, styles, or other assets
referenced by the resulting page must still be available to the browser. Use
`bundle exec jekyll build` to build the site locally.
