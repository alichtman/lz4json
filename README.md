# `lz4jsoncat`

A little utility to unpack `lz4json` files as generated by Firefox's bookmark backups and session restore.
This is a different format from what the normal lz4 utility expects.
The data is dumped to stdout.

## Dependencies

Requires `liblz4` (Debian package `liblz4-dev`, Fedora package `lz4-devel`) to be installed.

## Usage

```bash
$ lz4jsoncat ~/.mozilla/.../bookmarkbackups/bookmarks-2014-12-27_151_0UCIWGB4x3hhQXpuSMs5WQ==.jsonlz4
```

## Building

On some non Linux systems the `lz` libraries might be installed into directories that are not searched by the linker by default. If that's the case, please override the `CFLAGS` and `LDFLAGS` on the command line:

```bash
# e.g. if they are in /usr/local:
$ make CFLAGS="-I/usr/local/include -O2" LDFLAGS="-L/usr/local/lib"
```

## Installation

For a default installation, run:

```bash
$ make install
```

If you hit permission errors, try running the command with `sudo`.

To install to a custom prefix, run:

```bash
PREFIX=/your/custom_prefix_here make install
```

## Contributors

- [Andi Kleen](https://github.com/andikleen)
- [Aaron Lichtman](https://github.com/alichtman)
