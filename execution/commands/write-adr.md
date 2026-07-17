# Command — Write ADR (`write-adr`)

A command contract of the APEF Execution Framework. Full definition, inputs, outputs, and
execution flow are in the [Command Catalog](../COMMAND_CATALOG.md#write-adr).

- **Purpose:** Record a significant decision — context, options, and consequences — durably.
- **Primary skills:** Owning architect
- **Reviews & gates:** Architecture review; decision-record gate
- **Prompt contract:** follows the standard structure in [Execution Framework](../EXECUTION_FRAMEWORK.md#prompt-contracts).

This is a contract, not implementation: it defines what the command requires, produces, and
guarantees — never how it is carried out.
