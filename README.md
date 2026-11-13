<img src="https://raw.githubusercontent.com/envoscale/.github/main/profile/assets/logo.svg" alt="" width="56" align="left">

# EnvoWeb

Websites in [EnvoL](https://github.com/envoscale/EnvoLang): `envoweb` (routes, pages, a
server, and static builds from the same code), `envoweb.markdown`, and page templates drawn
with EnvoR's theme. [`site/`](site) is the EnvoScale website, built with them.

```cs
use envoweb as web;
use envo.http;

http.Response Home(in http.Request req, in web.Params ps) => http.Response.Html(200, "<h1>Hello</h1>");

web.App app = web.App.New();
app.Get("/", new web.Page { Fn = Home });
web.Serve(ref app, "127.0.0.1", 8080);
```

## The website

The site is the [EnvoScale documentation](https://github.com/envoscale/EnvoScale), rendered.
From a checkout of it:

```bash
envo build path/to/EnvoWeb/site
path/to/EnvoWeb/site/build/site build      # the static site in build/site
```

Set `ENVOLANG` to an EnvoLang checkout with `build/envoc.wasm` to include the sandbox,
where the compiler runs in the browser.

## Use

```
dependencies {
    envoweb = { git = "https://github.com/envoscale/EnvoWeb", rev = "<commit>" }
}
```

## License

Apache-2.0: see [LICENSE](LICENSE) and [NOTICE](NOTICE).
