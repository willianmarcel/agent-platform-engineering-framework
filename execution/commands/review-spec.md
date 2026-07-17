# Command — Review Spec (`review-spec`)

A command contract of the APEF Execution Framework. Full definition, inputs, outputs, and
execution flow are in the [Command Catalog](../COMMAND_CATALOG.md#review-spec).

- **Purpose:** Verify a specification is complete, consistent, and faithful to intent.
- **Primary skills:** Product Architect, Enterprise Architect
- **Reviews & gates:** Product & Domain review; specification-completeness gate
- **Prompt contract:** follows the standard structure in [Execution Framework](../EXECUTION_FRAMEWORK.md#prompt-contracts).

This is a contract, not implementation: it defines what the command requires, produces, and
guarantees — never how it is carried out.
