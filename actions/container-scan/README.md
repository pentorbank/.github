<!-- action-docs-header source="action.yml" -->

<!-- action-docs-header source="action.yml" -->

<!-- action-docs-description source="action.yml" -->
## Description

Action container image security scan
<!-- action-docs-description source="action.yml" -->

<!-- action-docs-inputs source="action.yml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `image-tag` | <p>container image tag</p> | `true` | `""` |
| `aqua-username` | <p>aquasec username</p> | `true` | `""` |
| `aqua-password` | <p>aquasec password</p> | `true` | `""` |
| `aqua-scanner-token` | <p>aquasec scanner token</p> | `true` | `""` |
| `aqua-scanner-host` | <p>aquasec scanner host</p> | `true` | `""` |
| `output` | <p>output file name</p> | `false` | `image-scanner-report.sarif` |
| `artifact` | <p>enable upload artifact</p> | `false` | `true` |
<!-- action-docs-inputs source="action.yml" -->

<!-- action-docs-outputs source="action.yml" -->

<!-- action-docs-outputs source="action.yml" -->

## Usage

```yaml
- uses: ./.github/actions/container-scan
  with:
    image-tag: ${{ steps.container-build.outputs.image }}
    aqua-username: ${{ secrets.AQUA_USERNAME }}
    aqua-password: ${{ secrets.AQUA_PASSWORD }}
    aqua-scanner-token: ${{ secrets.AQUA_SCANNER_TOKEN }}
    aqua-scanner-host: ${{ secrets.AQUA_SCANNER_HOST }}
```
