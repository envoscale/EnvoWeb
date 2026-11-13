<img src="https://raw.githubusercontent.com/envoscale/EnvoScale/main/docs/images/logo.svg" alt="" width="56" align="left">

# EnvoScaleWeb

Websites in [Envol](https://github.com/envoscale/EnvoScale): `envoweb` (routes, pages, a
server, and static builds from the same code), `envoweb.markdown`, and page templates drawn
with Envor's theme. [`site/`](site) is EnvoScale's own website, built with them.

```cs
use envoweb as web;
use envo.http;

http.Response Home(in http.Request req, in web.Params ps) => http.Response.Html(200, "<h1>Hello</h1>");

web.App app = web.App.New();
app.Get("/", new web.Page { Fn = Home });
web.Serve(ref app, "127.0.0.1", 8080);
```

## The website

From an EnvoScale checkout (the site renders its docs):

```bash
envo build path/to/EnvoScaleWeb/site
path/to/EnvoScaleWeb/site/build/site build      # the static site in build/site
```

## Use

```
dependencies {
    envoweb = { git = "https://github.com/envoscale/EnvoScaleWeb", rev = "<commit>" }
}
```

## License

Same as EnvoScale: see [LICENSE](LICENSE).
