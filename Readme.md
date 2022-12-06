## Hacker Slides

[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/msoedov/hacker-slides/blob/master/LICENSE)
[![Build Status](https://travis-ci.org/msoedov/hacker-slides.svg?branch=master)](https://travis-ci.org/msoedov/hacker-slides)
[![](https://images.microbadger.com/badges/image/msoedov/hacker-slides:latest.svg)](https://microbadger.com/images/msoedov/hacker-slides "Hacker slides image")
[![Open Source Helpers](https://www.codetriage.com/msoedov/hacker-slides/badges/users.svg)](https://www.codetriage.com/msoedov/hacker-slides)

Hacker Slides is a self hosted reveal.js presentations editor form markdown files.


#### Features:

- Reach ui editor
- Markdown markup
- Live reload
- Color schemes
- Pdf print
- Tiny 10 Mb docker image
- Optional Basic auth



This repo is a reworked version of Sandstorm Hacker Slides which features easy set up run outside of Sandstorm and without vagrant-spk. Likewise you can publish and edit your previous markdown slides which is not supported in the original version. This was forked from [https://github.com/msoedov/hacker-slides](msoedov/hacker-slides) 


Run from docker image
-----
```shell
docker run -it -p 8080:8080 -v $(pwd)/slides:/app/slides msoedov/hacker-slides
```

Build locally
----
To build and run it locally
```go
go get
go run main.go

[GIN-debug] Listening and serving HTTP on :8080
```

And then you can just open [http://127.0.0.1:8080](http://127.0.0.1:8080) and it's ready to use with sample slides.

Run with docker

```shell
docker run -it -p 8080:8080 -v $(pwd)/slides:/app/slides msoedov/hacker-slides
```

Protect slides with password
----
Basic auth (disabled by default)
```shell
USER=bob PASSWORD=password1 go run main.go
[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

WARN[0000] Auth mode enabled
WARN[0000] Visit http://bob:password1@0.0.0.0:8080
```

```shell
docker run -it -p 8080:8080 -e USER=bob -e PASSWORD=password1 -v $(pwd)/slides:/app/slides msoedov/hacker-slides
```

Use local images
----
Store pictures you want to use in the images subfolder, slides/images/ and reference them in the editor as Markdown:
```
![demoPicture](/images/demo.png)
```
or as HTML:
```
<img src="/images/demo.png">
```

Getting Help
------------

For **feature requests** and **bug reports**  submit an issue
to the GitHub issue tracker
