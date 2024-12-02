<!-- action-docs-header source="action.yml" -->

<!-- action-docs-header source="action.yml" -->

<!-- action-docs-description source="action.yml" -->

## Description

Action generate Github app token from Vault

<!-- action-docs-description source="action.yml" -->

<!-- action-docs-inputs source="action.yml" -->

## Inputs

| name                   | description                      | required | default                          |
| ---------------------- | -------------------------------- | -------- | -------------------------------- |
| `vault-addr`           | <p>vault address</p>             | `true`   | `""`                             |
| `vault-namespace`      | <p>vault namespace</p>           | `true`   | `""`                             |
| `vault-method`         | <p>vault auth method</p>         | `false`  | `jwt`                            |
| `vault-path`           | <p>vault auth path</p>           | `false`  | `gha`                            |
| `vault-role`           | <p>vault auth role</p>           | `true`   | `""`                             |
| `vault-kv`             | <p>vault github secret path</p>  | `false`  | `secrets/data/github/ptc-github` |
| `app-id-name`          | <p>key of github app id</p>      | `false`  | `app_id`                         |
| `app-private-key-name` | <p>key of github private key</p> | `false`  | `app_private_key`                |

<!-- action-docs-inputs source="action.yml" -->

<!-- action-docs-outputs source="action.yml" -->

## Outputs

| name         | description                |
| ------------ | -------------------------- |
| `token`      | <p>github token</p>        |
| `user-name`  | <p>github bot username</p> |
| `user-email` | <p>github bot email</p>    |

<!-- action-docs-outputs source="action.yml" -->

## Usage

```yaml
- name: Generate git token and user
  id: git
  uses: ./.github/actions/vault-github-app
  with:
    vault-addr: ${{ secrets.VAULT_ADDR_NONPROD }}
    vault-role: ${{ secrets.VAULT_ROLE_NONPROD }}
    vault-namespace: ${{ secrets.VAULT_NAMESPACE_NONPROD }}
```
