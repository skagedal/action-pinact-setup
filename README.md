# action-pinact-setup

A GitHub Action that installs [pinact](https://github.com/suzuki-shunsuke/pinact)
and puts it on `PATH`, and does nothing else.

pinact's own action, [pinact-action](https://github.com/suzuki-shunsuke/pinact-action),
runs pinact and commits the result itself. This is for when something else is
going to run it — a script that updates a repository's dependencies, say, and
pins the actions as one part of that.

```yaml
- uses: skagedal/action-pinact-setup@<sha> # v1.0.0
- run: pinact run --update
  env:
    PINACT_GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

The release is downloaded from GitHub and checked against the checksums file
published with it before it is installed.

## Inputs

| Input | Default | |
|---|---|---|
| `version` | `5.0.0` | The pinact version to install, without the leading `v`. |

Linux and macOS runners, on x86-64 and ARM.

## Outputs

| Output | |
|---|---|
| `version` | The pinact version that was installed. |

## License

MIT
