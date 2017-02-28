Run tests with `cucumber`

```
Feature: CLI
  Scenario: Run command
    When I run `cli`
    Then the stdout should contain "hello"
    Then the stderr should not contain "hello"
```
