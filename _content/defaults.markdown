---
title: Default fields
date: 2016-05-25 22:00:00 -04:00
position: 10
---

Instead of defining fields each time you create a page, post, or document, you can set defaults in your `_config.yml` theme file. In most cases, it'll be handy to set at least the default layout.

The `defaults` key in your `_config.yml` file is a list of different defaults. Each list item has two objects: `scope` and `values`.

- `scope` is how you choose which collection and files you're defining defaults on.
- `values` is where you define your default fields.

For example:

{% highlight yaml %}
defaults:
  -
    scope:
      path: ""
      type: "posts"
    values:
      layout: "default"
      author: "Ethan"
  -
    scope:
      path: ""
      type: "pages"
    values:
      layout: "page"
  -
    scope:
      path: "projects"
      type: "pages"
    values:
      colors: ["red", "green", "blue"]
      layout: "project"
{% endhighlight %}

In this case, we're:

- Setting the default `layout` and `author` for all posts
- Setting the default `layout` for all pages.
- Overriding the previous default `layout` for all pages in the `projects/` path, and setting a default `colors` List field with the values `red`, `green`, `blue`.

Note that `type` can be `posts`, `pages` or any other collection name (e.g. `people`).

---

### Further Reading:

- [Jekyll: Front Matter defaults](http://jekyllrb.com/docs/configuration/#front-matter-defaults)
