---
layout: post
title:  "How to decrease page load times"
date:   2017-09-24 23:10:21 +0000
---


Nothing makes users lose interest in a website more than slow page load times. Fortunately, there are many solutions to this problem, all of which you can use in conjunction with each other. Here are three of them -


#### Keep HTTP requests to a minimum

Instead of using multiple CSS stylesheets and multple Javascript files, combine them to create minified versions. This way the browser will not need to make as many separate HTTP requests, since a request is needed for each individual file.


#### Use a CDN (Content Delivery Network)

Inages, CSS, and Javascript files may be uploaded onto content delivery networks such as [Amazon's AWS Cloudfront](https://aws.amazon.com/cloudfront/) or [Cloudflare](https://www.cloudflare.com/). These work by delivering your files through servers that are physically closer to the individual user. This results in higher transfer speeds and lower latency.


#### Optimize your images
There are many different image formats, and it is best to use the appropriate image format. JPEGs are best for detailed images that use a lot of color, GIFs are best for images with less colors, and PNGs are best for images that have transparency involved. Also, make sure the image is properly resized. Smaller images have lower file sizes than larger ones.
