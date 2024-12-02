<!-- action-docs-header source="action.yml" -->

<!-- action-docs-header source="action.yml" -->

<!-- action-docs-description source="action.yml" -->

## Description

Action patch and sync with ArgoCD

<!-- action-docs-description source="action.yml" -->

<!-- action-docs-inputs source="action.yml" -->

## Inputs

| name           | description                      | required | default |
| -------------- | -------------------------------- | -------- | ------- |
| `gh_token`     | <p>github app token</p>          | `true`   | `""`    |
| `repository`   | <p>gitops repository</p>         | `true`   | `""`    |
| `bot-username` | <p>github app bot user name</p>  | `true`   | `""`    |
| `bot-email`    | <p>github app bot user email</p> | `true`   | `""`    |
| `service-name` | <p>service name</p>              | `true`   | `""`    |
| `image-tag`    | <p>image tag version</p>         | `true`   | `""`    |
| `path`         | <p>gitops deployment path</p>    | `true`   | `""`    |

<!-- action-docs-inputs source="action.yml" -->

<!-- action-docs-outputs source="action.yml" -->

<!-- action-docs-outputs source="action.yml" -->

## Usage

```yaml
- name: Argocd patch and sync
  uses: ./.github/actions/argocd
  with:
    gh_token: ${{ steps.git.outputs.token }}
    repository: "example-gitops"
    bot-username: ${{ steps.git.outputs.user-name }}
    bot-email: ${{ steps.git.outputs.user-email }}
    service-name: ${{ env.SERVICE_NAME }}
    image-tag: ${{ needs.build.outputs.image-tag }}
    path: "config/${{ env.SERVICE_NAME }}/dev/values.yml"
```
