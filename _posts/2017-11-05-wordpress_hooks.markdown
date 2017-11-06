---
layout: post
title:      "Wordpress Hooks"
date:       2017-11-05 11:28:25 -0400
permalink:  wordpress_hooks
---

This week, I got acquainted with the conveniences of Wordpress Hooks. 

Wordpress hooks exist so that core Wordpress files won't need to be modified at all. It is used to change default Wordpress functionality. With hooks, adding features become much more simplified because there is no need to hunt down specific lines of Wordpress code.

Hooks not only make it easier to add functionality, but they also make it easier to add additional HTML. You can reference a specific hook and write functions to add anything you want to it.

You can also remove elements with the correct references, and reorder elements on the page by either specifying their priorities and/or attaching them to different hooks.