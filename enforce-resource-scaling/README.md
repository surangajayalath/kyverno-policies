# kyverno-policies

## auto-generate-production-hpa-if-not-exists

When a production Deployment or StatefulSet is created, automatically create an HPA only when the expected HPA does not already exist.

### The overall flow is:
```yaml
             Deployment / StatefulSet
                       │
                       ▼
              production=true?
                 │          │
                NO         YES
                 │          │
                 ▼          ▼
              Ignore    Check <name>-hpa
                              │
                       ┌──────┴──────┐
                       │             │
                     200            404
                       │             │
                       ▼             ▼
                   Already        Generate
                    exists           HPA
                       │             │
                       ▼             ▼
                    Ignore       min: 2
                                 max: 100
                                 CPU: 80%
```
