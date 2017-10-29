Linky
=====
Extract and check links.


Features
--------
* Input:
  * Command line interface.
  * Extract links from Markdown files.
  * Read links to check from stdin in `grep -Hn` format.
* Checking:
  * Verify that HTTP(S) URLs are resolvable to successful HTTP status codes.
  * Verify that local URLs are resolvable to local files.
  * Verify that fragments in HTTP(S) URLs correspond HTML anchors.
  * Verify that fragments in local URLs correspond Markdown headings.



Installation
------------
[Install stable Rust and Cargo]:

```sh
$ curl -sSf https://static.rust-lang.org/rustup.sh | sh
```

Download and unpack source code from the current master branch:

```sh
$ curl https://github.com/mattias-p/linky/archive/master.zip
$ unzip master.zip
$ cd linky-master
```

Compile and link the binary:

```sh
$ cargo build --release
```

[Install stable Rust and Cargo]: http://doc.crates.io/


Examples
--------

### Inputs

Extract links from Markdown files:

```sh
$ linky examples/single.md examples/exhibition.md
```

Extract and check links from Markdown files:

```sh
$ linky --check examples/single.md
```

Extract links from Markdown and check the ones containing "README":

```sh
$ linky examples/single.md | grep 'README[^ ]*' | linky --check
```

### Resolution

Resolve absolute local URLs as relative to a local directory:

```sh
$ linky --check --base ./examples/markdown_site examples/exhibition.md
```

Resolve absolute local URLs as relative to a base domain:

```sh
$ linky --check --base https://github.com/ examples/exhibition.md
```

Resolve absolute local URLs as relative to a base domain, allowing HTTP redirects:

```sh
$ linky --check --relative --base http://github.com/ examples/exhibition.md
```
