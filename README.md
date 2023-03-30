# Errata: Amazon Web Services in Action (3rd Edition)

![Cover of Amazon Web Services in Action, 3rd Edition](https://images.manning.com/264/352/resize/book/f/bc1b7ca-d446-42bf-a66d-a522d312c86e/Wittig-3ed-HI.png)

> If you find any any errors in [Amazon Web Services in Action (3rd Edition)](https://bit.ly/amazon-web-services-in-action-3rd-edition) not listed in the errata, or just find something that you think is not well explained, it would be most appreciated if you would post in the book's [errata discussion](https://livebook.manning.com/book/amazon-web-services-in-action-third-edition/Errata/) so that they may be collected here for everyone's benefit. Thanks!

## Using this project

[Install Hugo](http://gohugo.io/overview/installing/) to build the site.

### Run locally

```
docker run --rm -it -v $(pwd):/src -p 1313:1313 klakegg/hugo:0.83.1-ext-ubuntu server --buildDrafts --bind 0.0.0.0 -w
```

Open http://localhost:1313/ to see the site.

### Generate HTML

```
rm -rf public/
docker run --rm -it -v $(pwd):/src klakegg/hugo:0.83.1-ext-ubuntu --buildDrafts
```

send file `./public/index.html` to Susan Harkins <suha@manning.com>
