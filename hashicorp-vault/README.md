# kyverno-policies

## auto-inject-vault-annotations

After applying this policy, any `Deployment` or `Pod` created in a namespace labeled with `vault-injector=true` will automatically have the following annotations injected:

```yaml
{
  "vault.hashicorp.com/agent-inject": "true",
  "vault.hashicorp.com/role": "devops-dev-role",
  "vault.hashicorp.com/namespace": "devops"
}
```
