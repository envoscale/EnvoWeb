# site/

The EnvoScale website, written in EnvoL
([plan](https://github.com/envoscale/EnvoScale/blob/main/project/website-plan.md)).
[`main.envol`](main.envol) renders the home page with EnvoR's Landing template, and every
Markdown document of the [EnvoScale documentation](https://github.com/envoscale/EnvoScale)
with the Docs template. Pages keep their paths, so `envol/README.md` becomes
`envol/README.html` and the documents' links keep working. All links are relative, so the
site works at any address.

From a checkout of the documentation:

```sh
envo build path/to/EnvoWeb/site
path/to/EnvoWeb/site/build/site build          # the static site in build/site
path/to/EnvoWeb/site/build/site serve 8080     # the same pages, rendered per request
```

The **sandbox** (`/sandbox/`) is the compiler itself, built for WebAssembly. It compiles
and runs programs in the visitor's browser, so nothing they type leaves their machine. To include it,
build the compiler for WebAssembly in an EnvoLang checkout and point `ENVOLANG` at it:

```sh
cd EnvoLang/compiler
../build/envoc/envoc build -O2 --target wasm32-web $(cat files.txt) -o ../build/envoc.wasm
```
