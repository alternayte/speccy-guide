---
type: sdd
title: Invoices — design
---

# Invoices — design

## Context

Each paid order gets a PDF invoice that the customer can download.

## Decisions

- **DEC-001:** The billing service makes the invoice after the payment succeeds.

## Components

The billing service listens for paid orders and stores the PDF in object storage.

## Interfaces

`GET /orders/{orderId}/invoice` returns the PDF.

## Failure handling

If the PDF does not render, the service logs the error.
