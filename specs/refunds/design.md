# Refunds design

## Context

This design implements the refunds PRD.

## Architecture

The order service calls the provider's refund API. It stores each refund in the refunds table.

## Data model

- refunds: id, order_id, amount, status, created_at.

## Interfaces

- POST /orders/{id}/refunds with an amount.

## Failure handling

A refund that fails is retried.

## Decisions

- **DEC-001:** Refunds go through the order service, so that the audit trail stays in one place.
