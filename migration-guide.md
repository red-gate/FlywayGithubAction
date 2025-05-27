# Migrating from FlywayGithubAction

## Overview

In May 2025 this GitHub Action was deprecated. We recommend moving to one of two alternatives:
- Use the `setup-flyway` GitHub Action, with a direct call to `flyway migrate`
- Use the Flyway Docker image directly

### Using `setup-flyway`

The following example shows how to configure `setup-flyway` to work the same as the example in the README.md

```
steps:
  - name: Install Flyway
    uses: red-gate/setup-flyway@v1
  - name: Run Flyway Migrate
    run: |
      flyway migrate `
        -url=jdbc:postgresql://postgres:5432/db `
        -user=user `
        -password=password `
        -locations=filesystem:./sql `
        -outOfOrder=true
```

### Using the Flyway Docker image

The following example shows how to configure the Flyway Docker image to work the same as the example in the README.md

```
steps:
  - name: Run Flyway Migrate
    uses: docker://redgate/flyway:latest-alpine
    with:
      args: >-
        migrate
        -workingDirectory=/github/workspace/src/database
        -environment=production
        -url="jdbc:postgresql://postgres:5432/db"
        -user="user"
        -password="password"
        -locations="filesystem:./sql"
        -outOfOrder=true
```