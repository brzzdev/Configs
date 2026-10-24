# Configs

Starting configs to copy into new projects, one folder per platform.

## Swift

SwiftFormat, SwiftLint and SwiftGen, installed with mise and wired up by `just tools`.

## Web

TypeScript projects on pnpm:

- Oxfmt formats with its defaults, plus sorted imports.
- Oxlint lints with type information (`oxlint-tsgolint`): the correctness, suspicious, perf and
  pedantic categories, hand-picked restriction rules, and the vendored
  [anti-slop](https://github.com/dmmulroy/anti-slop) rules in `tools/oxlint/anti-slop/`.
  `UPSTREAM.md` there records the vendored commit.
- `tsconfig.base.json` extends `@tsconfig/strictest`. Projects add their DOM or worker types.
- Knip reports unused files, exports and dependencies.
- pnpm holds back releases younger than a day and refuses trust downgrades.
- Lefthook formats and lints the staged files before each commit, hiding their unstaged hunks so
  both check what gets committed.
- GitHub Actions runs `just check` on pull requests and `main`.

To adopt it, copy `Web/` into the project root and restore the leading dots (`gitignore` and
`github/`), merge `package.json` into the project's own, then run `just tools`. `just check` runs
every check; `just fix` applies the fixes.

`tsconfig.json` excludes the vendored plugin, which fails strictest. Setting `exclude` also stops
TypeScript skipping `outDir`, so a project that emits adds its `outDir` to that list.

Disable a rule only on the line that needs it, with the reason after `--`. A type assertion also
needs a `// SAFETY:` comment stating the invariant that makes it sound.
