---
layout: post
title: "Want to try PHP with Foreign Function Interface (FFI) ?"
date: 2019-03-11 06:54:35 +0100
author: Jérémy DECOOL
categories: "7.4"
---

The [_Foreign Function Interface_](https://wiki.php.net/rfc/ffi) (or FFI), allow PHP to call C functions and using C data types directly from the language. It's seems that you don't have to write a PHP extension in C, you can do it directly in your PHP code. PHP FFI is available as a [core extension](https://github.com/php/php-src/tree/master/ext/ffi) and it's not enabled by default.

<!--more-->

If you want to try this new feature, you can do it very simply with phpdaily Docker images. You just have to extend the default PHP image, and install the extension.

```
# Dockerfile
FROM phpdaily/php:7.4.0-dev

RUN apk add --no-cache --virtual .persistent-deps libffi-dev \
    && docker-php-ext-configure ffi --with-ffi \
    && docker-php-ext-install ffi
```

Then build your Docker image using `docker build -t php/ffi`.

Your PHP Docker image with FFI is now ready.
