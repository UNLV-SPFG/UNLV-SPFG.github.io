---
permalink: /liquid/
title: "Liquid"
---

This page demonstrates the capabilities of Liquid, Jekyll's templating language.

## Objects
{% raw  %}
Objects tell Liquid where to output content. They’re denoted by double curly braces: `{{` and `}}`. For example:
{% endraw %}

{% highlight markdown %}
{{ "{{ page.title " }}}}
{% endhighlight %}

Outputs a variable called `page.title` on the page, in this case `{{ page.title }}`.

## Tags
{% raw  %}
Tags create the logic and control flow for templates. They are denoted by curly braces and percent signs: `{%` and `%}`. For example:
{% endraw %}

{% highlight md %}
{% raw  %}
{% if page.show_sidebar %}
  <div class="sidebar">
    sidebar content
  </div>
{% endif %}
{% endraw %}
{% endhighlight %}

{% raw  %}
Outputs the sidebar if `page.show_sidebar` is true.
{% endraw %}

## Filters
Filters change the output of a Liquid object. They are used within an output and are separated by a `|`. For example:

{% highlight md %}
{% raw  %}
{{ "hi" | capitalize }}
{% endraw %}
{% endhighlight %}

Outputs `{{ "hi" | capitalize }}`.
