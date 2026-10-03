---
type: sdd
title: Refunds — design
---

# Refunds — design

## Context

The payment service refunds a paid order when support asks for it.

## Non-goals

- Partial refunds of one line of an order.
- Refunds to a card other than the one that paid.

## Decisions

- **DEC-001:** The payment service owns refunds, because it holds the provider credentials.

## Components

The support tool calls the payment service. The payment service calls the provider.

## Interfaces

`POST /orders/{orderId}/refund` takes an amount and returns 200 when the provider accepts it.

## Failure handling

When the provider times out, the service tries again later.
