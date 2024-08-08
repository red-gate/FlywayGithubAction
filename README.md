# Flyway GitHub Action

![Badge](./badge.svg)

![Flyway logo](./Flyway_logo.svg)

Official Redgate GitHub Action for Flyway.

Use this action to run a Flyway migrate command.

## Example usage

```
steps:
  - uses: red-gate/FlywayGitHubAction@main
    with:
      url: jdbc:postgresql://postgres:5432/db
      user: user
      password: password
      locations: filesystem:./sql
      extraArgs: -outOfOrder=true
```

## `extraArgs`

The Flyway Github Action provides direct support for the most common parameters. The `extraArgs` input is provided so that parameters that aren't directly supported by the GitHub Action can be used.

Items supplied to `extraArgs` need to be specified as if they're being passed on the commandline. E.g:

`extraArgs: -outOfOrder=true -stream=true`

## Disclaimer
This GitHub Action is provided on an as is basis and no warranties or representations of any sort are made. Please note that you are solely responsible for any data which you input into the Action. We recommend that no personal or confidential information is included.
