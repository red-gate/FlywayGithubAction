# Flyway GitHub Action

![Badge](./badge.svg)

![Flyway logo](./flyway.png)

Official Redgate GitHub Action for Flyway

## Example usage

```
steps:
  - uses: red-gate/FlywayGitHubAction@main
  with:
    url: jdbc:postgresql://postgres:5432/db
    user: user
    password: password
    locations: ./sql
    extraArgs: -outOfOrder=true
```

## `extraArgs`

The Flyway Github Action provides direct support for the most common Flyway parameters. The `extraArgs` input is provided so that parameters that aren't directly supported by the GitHub Action can be used.

Items supplied to `extraArgs` need to be specified as if they're being passed on the commandline. E.g:

`extraArgs: -outOfOrder=true -stream=true`
