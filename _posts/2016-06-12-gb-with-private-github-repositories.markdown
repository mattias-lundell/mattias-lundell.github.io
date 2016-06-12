---
title: gb with private github repositories
date: 2016-06-12T21:44:18+02:00
---

Workaround for getting gb to play nice with vendored private repositories. Add following lines to `.gitconfig` file:

{% highlight INI %}
[url "git@github.com:mattias-lundell"]
  insteadOf = https://github.com/mattias-lundell
{% endhighlight %}
