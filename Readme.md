# Make Code Archive

GitHub composite action that archives Shamrock (including submodules) and uploads the result as a workflow artifact.

## Usage

```yaml
jobs:
  archive:
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - uses: shamrock-dev/action-make-code-archive@v1.1
        with:
          output_name: archive_name.tar.gz
```

## Inputs

| Name | Required | Description |
|------|----------|-------------|
| `output_name` | Yes | Output archive filename and artifact name. Must end with `.tar.gz`. |

## Requirements

- The action checks out the repository and initializes submodules, so it works whether or not the caller has already run `actions/checkout`.
- Artifact upload uses the default `GITHUB_TOKEN`. Ensure the job has permission to upload artifacts (the default `permissions` in most workflows is sufficient).

## License

MIT — see [LICENSE](LICENSE).
