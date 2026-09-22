# Audit trail

## Context

Every refund writes a row.

## Decisions

- **DEC-001:** The audit log is append-only.

## Interfaces

The writer takes a refund ID and returns nothing.
