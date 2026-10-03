---
type: sdd
title: Provider webhooks — design
---

# Provider webhooks — design

## Context

The provider sends a webhook when a payment settles. The payment service must record it.

## Decisions

- **DEC-001:** The payment service checks the webhook signature with the provider's shared secret.

## Components

A webhook endpoint in the payment service writes each event to the payment_event table.

## Interfaces

`POST /webhooks/provider` takes the provider's event and returns 204.

## Failure handling

An event with a bad signature is dropped. A duplicate event is handled appropriately.
