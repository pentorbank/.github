<!-- action-docs-header source="action.yml" -->

<!-- action-docs-header source="action.yml" -->

<!-- action-docs-description source="action.yml" -->

## Description

Action code security scan

<!-- action-docs-description source="action.yml" -->

<!-- action-docs-inputs source="action.yml" -->

## Inputs

| name                       | description                                                                                                                                                      | required | default                                             |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | --------------------------------------------------- |
| `gh_token`                 | <p>Github token</p>                                                                                                                                              | `false`  | `${{ github.token }}`                               |
| `aqua-key`                 | <p>aquasec key</p>                                                                                                                                               | `true`   | `""`                                                |
| `aqua-secret`              | <p>aquasec secret</p>                                                                                                                                            | `true`   | `""`                                                |
| `aqua-url`                 | <p>aqua url see on github integration Aquasec</p>                                                                                                                | `false`  | `https://api.asia-1.supply-chain.cloud.aquasec.com` |
| `cspm-url`                 | <p>cspm url see on github integration Aquasec</p>                                                                                                                | `false`  | `https://asia-1.api.cloudsploit.com`                |
| `aqua-username`            | <p>aquasec username</p>                                                                                                                                          | `true`   | `""`                                                |
| `aqua-password`            | <p>aquasec password</p>                                                                                                                                          | `true`   | `""`                                                |
| `scanners`                 | <p>comma-separated list of what security issues to detect (vuln,misconfig,secret,license) (default [vuln,secret])</p>                                            | `false`  | `vuln,secret`                                       |
| `severity`                 | <p>severities of vulnerabilities to be displayed [UNKNOWN,LOW,MEDIUM,HIGH,CRITICAL]</p>                                                                          | `false`  | `HIGH,CRITICAL`                                     |
| `db-repository`            | <p>OCI repository(ies) to retrieve trivy-db in order of priority (default [mirror.gcr.io/aquasec/trivy-db:2,ghcr.io/aquasecurity/trivy-db:2])</p>                | `false`  | `registry.aquasec.com/trivy-db:2`                   |
| `checks-bundle-repository` | <p>OCI registry URL to retrieve checks bundle from (default 'ghcr.io/aquasecurity/trivy-checks:1')</p>                                                           | `false`  | `registry.aquasec.com/trivy-checks:1`               |
| `java-db-repository`       | <p>OCI repository(ies) to retrieve trivy-java-db in order of priority (default [mirror.gcr.io/aquasec/trivy-java-db:1,ghcr.io/aquasecurity/trivy-java-db:1])</p> | `false`  | `registry.aquasec.com/trivy-java-db:1`              |
| `exit-code`                | <p>specify exit code when any security issues are found</p>                                                                                                      | `false`  | `1`                                                 |
| `format`                   | <p>format (table,json,template,sarif,cyclonedx,spdx,spdx-json,github,cosign-vuln) (default sarif)</p>                                                            | `false`  | `sarif`                                             |
| `output`                   | <p>output file name</p>                                                                                                                                          | `false`  | `trivy-report.sarif`                                |
| `review`                   | <p>enable reviewdog pr check</p>                                                                                                                                 | `false`  | `true`                                              |
| `artifact`                 | <p>enable upload artifact</p>                                                                                                                                    | `false`  | `true`                                              |

<!-- action-docs-inputs source="action.yml" -->

<!-- action-docs-outputs source="action.yml" -->

<!-- action-docs-outputs source="action.yml" -->

## Usage

```yaml
- uses: ./.github/actions/code-scan
  with:
    aqua-key: ${{ secrets.AQUA_KEY }}
    aqua-secret: ${{ secrets.AQUA_SECRET }}
    aqua-username: ${{ secrets.AQUA_USERNAME }}
    aqua-password: ${{ secrets.AQUA_PASSWORD }}
```
