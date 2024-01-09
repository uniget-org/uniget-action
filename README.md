# uniget-action

GitHub Action to run [`uniget`](https://github.com/uniget-org/cli) and install tools from the container ecosystem.

## Inputs

### `version`

Version of `uniget` to use. It can be set to any existing version (at least 2.2.49) and defaults to `latest`.

### `path`

Path to install `uniget` into. Defaults to `/usr/local/bin`.

### `tools`

Space separated list of tools to install. If this is not empty, the metadata will be updated automatically. Defaults to an empty string.

### `prefix`

Directory under which to install tools. Defaults to an empty string.

### `target`

Subdirectory of `prefix` under which to install tools. Defaults to `usr/local`.

### `skip-conflicts`

Skip tools that cause a conflict. Defaults to `true`.

## Outputs

None

## Examples

Install all tools using the latest version of `uniget`:

```yaml
    - name: Install
      uses: uniget-org/uniget-action
```

Install only some tools:

```yaml

  - name: Install
    uses: uniget-org/uniget-action
    with:
      only: true
      list: "docker yq"
```

Install using a specific version of `uniget`:

```yaml

    - name: Install
      uses: uniget-org/uniget-action
      with:
        version: 2.2.50
```
