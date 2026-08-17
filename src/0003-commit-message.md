# Terra Commit Messages

— mado

## Rationale

I would like to submit a new commit message format for packaging in Terra.
We are currently using [conventional commits] but it is not really designed for the needs of Terra.
It's a solution for say coding projects that didn't have any kind of commit formats. It works,
because well having 1 format is better than having none at all, but it's definitely not the best,
especially since we are dealing with package sources, and a lot of package sources every single day.

## Scope

I believe the format should be used only when submitting changes that modify package sources.
For example, changes to documentations and workflow files should not use this format.

## Format

The (first line of the) commit message should start with the *short package name*, which is the
package name used on the name of the `.spec` file. For example, the *short package name* for
`anki-bin.spec` is `anki-bin`.

The name shall then be followed by `: ` (colon and 1 space) and a short, concise description of the
commit. Then, optionally add a new line and then provide additional context (similar to
[conventional commits]).

For new package additions, the parts after the *short package name* can be omitted entirely.

I recommend having the first line of the additioanl context to be something like `Fix #1234` or
`Close #1234`.

## Special Cases

- when removing packages, just write `-anki-bin` (prefix package name with `-`)
- I figured some people might think it's a bit weird that writing only `zed-nightly` already means
  adding the package, so having a `+` prefix is also allowed.

## Examples

When adding a new package:

```
zed-nightly
```
```
+nim
```

When fixing a package:

```
fresh: bdep pkgconfig(icu-uc)
```

When adding features(?) to a package:

```
ghostty-tip: track each tip release
```

When removing a package:

```
-zig0.15
```

[conventional commmits]: https://www.conventionalcommits.org/
