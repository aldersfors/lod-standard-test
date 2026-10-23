# Example standard repository

A minimal engineering standard for lod. Point `[standard]` in config at a repository
with this layout:

```
standard.toml          version = "..."
rules/*.toml           one or more [[rule]] tables per file
```

Each rule has an `id` (A-Z, 0-9, '-'), a `title`, a `level` (`must` or `should`), an
optional `applies_to` selector (`topics`, `paths` globs, `languages`), a `check`, and a
`remediation` with a `hint` and the `scope` globs a campaign may change.

Check kinds: `file_exists`, `file_absent`, `file_matches`, `toml_path`, `yaml_path`,
`json_path`, `ci_includes`, `codeowners_present`, `renovate_extends`, and `exec`
(external tool, off unless `checks.exec_enabled = true`).

Globs: `*` stays within one directory; `**` crosses directories.

`example-repo/.standard/waivers.toml` shows the waiver format repositories use.
