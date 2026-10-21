# infra-patterns

Reusable infrastructure patterns for deploying applications with
[infrapipe](https://github.com/foolswithtools/infrapipe-releases). Each pattern
is a module you can copy into your own repository, with a README and example
GitHub Actions workflows that call it.

This repository is the public face of the patterns. It holds **pattern code,
docs and examples only**. The test harness that proves each pattern against
real infrastructure lives in a private repository and is not published here,
and nothing in this repository applies infrastructure: it has no workflows.

## Layout

Each pattern lives in its own directory:

```
patterns/<name>/
  README.md                 what the pattern builds, its inputs and outputs
  ...                       the module code
  examples/github-actions/  example workflows that deploy the pattern
```

No patterns are published yet; the first arrives with the first snapshot.

## Deploying

infrapipe is the deploy contract. The example workflows under
`examples/github-actions/` run the infrapipe binary from
[infrapipe-releases](https://github.com/foolswithtools/infrapipe-releases); its
documentation defines the configuration, commands and CI behaviour the patterns
rely on. Pin the infrapipe version your workflows use.

## How content arrives

Nothing is committed to this repository directly. Patterns arrive only as
snapshot pull requests from the private repository: a tagged, allowlisted,
scanned and squashed copy of the published paths, which a maintainer reviews
and merges. There is no live mirror. `main` is protected; a reviewed pull
request is the only way in.

Every example uses `example.com` and placeholder values for domains, account
ids and role names. Replace them with your own.

## Licence

MIT, see [`LICENSE`](LICENSE). The licence covers the pattern code, docs and
examples.
