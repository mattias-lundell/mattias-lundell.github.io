---
layout: post
title: "[NOTE] defer timing trick"
date: 2015-12-06 21:17:00 +0200
comments: true
categories: golang
---

Example of how to use `defer` in golang as a crude way of measure execution time. Start by defining the `timeit` function. The function just prints the duration from the time given by `start`.

```go
{% highlight go %}
func timeit(start time.Time, text string) {
    log.Info("PERF [%s] [%s]", text, time.Since(start))
}
{% endhighlight %}
```

Using the `defer` keyword we can make `timeit` execute directly after the function that we want to measure. Passing `time.Now()` as argument gives us a timer that measures execution time for the function body.

{% highlight go %}
func timedFunction() {
    defer timeit(time.Now())
    time.Sleep(500 * time.Millisecond)
}
{% endhighlight %}

Calling `timedFunction()` should print

```
PERF [timedFunction] [500ms]
```
