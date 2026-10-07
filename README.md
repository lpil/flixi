# flixi

Use the [fixi.js hypermedia library](https://fixiproject.org/fixi.html) with [Lustre](https://hexdocs.pm/lustre)!

[![Package Version](https://img.shields.io/hexpm/v/flixi)](https://hex.pm/packages/flixi)
[![Hex Docs](https://img.shields.io/badge/hex-docs-ffaff3)](https://hexdocs.pm/flixi/)

```sh
gleam add flixi@1
```
```gleam
import flixi
import lustre/element.{type Element}
import gleam/http
import lustre/attribute
import lustre/element/html

pub fn fixi_button() -> List(Element(a)) {
  let attributes = [
    // The URL to issue request to
    flixi.action("/content"),
    // The HTTP Method to use
    flixi.method(http.Get),
    // The event that triggers the request
    flixi.trigger("click"),
    // The element to swap
    flixi.target("#output"),
    // How to swap the element
    flixi.swap("innerHTML"),
  ]
  [
    html.button(attributes, [html.text("Get Content")]),
    html.output([attribute.id("output")], []),
  ]
}
```

Further documentation can be found at <https://hexdocs.pm/flixi>.
