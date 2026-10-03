---
type: sdd
title: Fraud checks — design
---

# Fraud checks — design

## Context

Orders above a limit go through a fraud check before the payment service charges the card.

## Decisions

- **DEC-001:** The fraud service decides, and the payment service follows the decision.

## Components

The checkout service asks the fraud service, then calls the payment service.

## Interfaces

`POST /fraud/check` takes the order and returns allow, review, or deny.

## Failure handling

If the fraud service does not answer in time, the order is held.
