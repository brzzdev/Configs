# Vendored anti-slop

Source: [dmmulroy/anti-slop](https://github.com/dmmulroy/anti-slop), commit
`13909c9e07590f5a85d93c62712259fe14a883f7`.

Copied from `skills/install-anti-slop/assets/anti-slop/`, which at that commit is `src/` without
the rule tests. The root `LICENSE` is kept verbatim beside it.

## Local deviations

- The Effect group (`effect/`) is not vendored: this repo doesn't use Effect.

## Updating

Fetch an explicit upstream revision, diff it against the commit above, port the changes, and update
this record. Keep `oxlint` and `@oxlint/plugins` on the same exact version.
