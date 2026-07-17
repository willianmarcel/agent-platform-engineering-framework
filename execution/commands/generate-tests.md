# Command — Generate Tests (`generate-tests`)

A command contract of the APEF Execution Framework. Full definition, inputs, outputs, and
execution flow are in the [Command Catalog](../COMMAND_CATALOG.md#generate-tests).

- **Purpose:** Design the testing that verifies software correctness (a test plan, not test code).
- **Primary skills:** Code Reviewer, Runtime Architect
- **Reviews & gates:** Testing review; test-coverage gate
- **Prompt contract:** follows the standard structure in [Execution Framework](../EXECUTION_FRAMEWORK.md#prompt-contracts).

This is a contract, not implementation: it defines what the command requires, produces, and
guarantees — never how it is carried out.
