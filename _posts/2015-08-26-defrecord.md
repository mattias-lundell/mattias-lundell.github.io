---
layout: post
title: "[NOTE] defrecord"
date: 2015-08-26 17:30:00 +0200
comments: true
categories: 
---

Clojure defrecord does not expose the constructor outside the namespace

```
(defrecord Point [x y])
(def origin (Point. 0 0)) ; only avalable in namespace
```

Instead use the automatically generated constructor

```
(def origin (->Point 0 0)) ; available in other namespaces
```
