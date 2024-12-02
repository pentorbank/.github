<!-- action-docs-header source="action.yml" -->

<!-- action-docs-header source="action.yml" -->

<!-- action-docs-description source="action.yml" -->
## Description

Action container build image push to AWS ECR
<!-- action-docs-description source="action.yml" -->

<!-- action-docs-inputs source="action.yml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `aws-region` | <p>AWS Region, e.g. us-east-2</p> | `true` | `""` |
| `role-to-assume` | <p>The Amazon Resource Name (ARN) of the role to assume. Use the provided credentials to assume an IAM role and configure the Actions environment with the assumed role credentials rather than with the provided credentials.</p> | `false` | `""` |
| `aws-access-key-id` | <p>AWS Access Key ID. Provide this key if you want to assume a role using access keys rather than a web identity token.</p> | `false` | `""` |
| `aws-secret-access-key` | <p>AWS Secret Access Key. Required if aws-access-key-id is provided.</p> | `false` | `""` |
| `repository` | <p>AWS ECR repository name</p> | `true` | `""` |
| `tag` | <p>tag versioning</p> | `true` | `""` |
| `aqua-username` | <p>aquasec username</p> | `true` | `""` |
| `aqua-password` | <p>aquasec password</p> | `true` | `""` |
| `aqua-scanner-token` | <p>aquasec scanner token</p> | `true` | `""` |
| `aqua-scanner-host` | <p>aquasec scanner host</p> | `true` | `""` |
| `container-scan` | <p>enable container scan</p> | `false` | `true` |
<!-- action-docs-inputs source="action.yml" -->

<!-- action-docs-outputs source="action.yml" -->
## Outputs

| name | description |
| --- | --- |
| `image-tag` | <p>Container image tag</p> |
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
