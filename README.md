# Web Security

This repository contains the source of "Web Security" book, a comprehensive guide to understanding and implementing web security practices.

## About

This book covers everything from the fundamentals of web security to advanced attack techniques and defense strategies. Whether you're a beginner looking to understand the basics or an experienced developer wanting to deepen your security knowledge, this book is for you.

## Reading the Book

You can read the book online or build it locally.

### Reading Online

The book is available for free online. Visit the hosted version for the latest content.

### Building Locally

Building the book requires [mdBook](https://github.com/rust-lang/mdBook), a tool for creating modern online books from Markdown files. To get it:

```bash
$ cargo install mdbook
```

Or if you prefer using a package manager:

```bash
# Ubuntu/Debian
$ sudo apt install mdbook

# macOS (Homebrew)
$ brew install mdbook
```

To build the book, type:

```bash
$ mdbook build
```

The output will be in the `book` subdirectory. To check it out, open it in your web browser.

_Firefox:_

```bash
$ firefox book/index.html                       # Linux
$ open -a "Firefox" book/index.html             # macOS
$ Start-Process "firefox.exe" .\book\index.html # Windows (PowerShell)
```

_Chrome:_

```bash
$ google-chrome book/index.html                 # Linux
$ open -a "Google Chrome" book/index.html       # macOS
$ Start-Process "chrome.exe" .\book\index.html  # Windows (PowerShell)
```

To serve the book locally with live reloading:

```bash
$ mdbook serve
```

This will start a local server at `http://localhost:3000` and automatically reload the page when you make changes.

## Contributing

We'd love your help! Please see [CONTRIBUTING.md](CONTRIBUTING.md) to learn about the kinds of contributions we're looking for.

### Translations

We'd love help translating the book! See the [Translations](https://github.com/yourusername/web-security-book/issues?q=is%3Aopen+is%3Aissue+label%3ATranslations) label to join in efforts that are currently in progress. Open a new issue to start working on a new language!

## License

This book is licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the Apache-2.0 license, shall be dual licensed as above, without any additional terms or conditions.
