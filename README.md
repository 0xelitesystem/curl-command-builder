# curl Command Builder

Fill in a form and get a properly quoted `curl` command in real time. Method, URL, query params, headers, body and auth, plus the common toggles. It only builds the string, it never sends your request. No server, no tracking, no external dependencies.

## Live demo

https://0xelitesystem.github.io/curl-command-builder/

## Features

- Method: GET, POST, PUT, PATCH, DELETE (`-X` is omitted for a plain GET)
- URL plus repeatable query parameter rows (urlencoded and appended to the URL)
- Repeatable header rows
- Body modes: none, raw, JSON (adds `Content-Type: application/json`), or form (each pair becomes a `--data-urlencode` field)
- Auth: none, Basic (`-u user:pass`), or Bearer (`Authorization: Bearer ...`)
- Toggles: `-i`, `-L`, `-k` (with an insecure TLS warning), `--compressed`, `-s`
- Live single-line output and an equivalent multi-line, backslash-continued form
- Copy button for each form
- Dark-mode toggle, keyboard usable

## How it works

As you type, the tool assembles an argument list and renders it two ways: one long line and one backslash-continued block. Values are quoted for POSIX shells. Text that is entirely safe (letters, digits, and a small set of URL-safe punctuation) is left unquoted, and anything else is wrapped in single quotes with embedded single quotes escaped as the canonical `'\''` sequence, which closes the quote, adds a literal escaped quote, and reopens. That guarantees the shell treats the value literally. Query parameters are percent-encoded with `encodeURIComponent` before being appended to the URL. The tool makes no network calls of its own, so it works fully offline.

## Privacy

Everything runs in your browser. The values you type never leave your machine. You can confirm this by viewing the page source or watching the network tab in DevTools, no requests are made. The tool works offline with no external dependencies. Copy the command and run it yourself in a terminal you trust.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT. Copyright 0xelitesystem 2026.
