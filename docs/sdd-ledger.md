---
type: sdd
title: Ledger export — design
---

# Ledger export — design

## Context

Finance needs a daily file of every payment, refund and fee.

## Decisions

- **DEC-001:** A nightly job writes the file, because finance reads it once a day.

## Components

The export job reads the payment tables and writes a CSV to the finance bucket.

## Interfaces

The CSV has one row per money movement, with the columns date, order_id, kind (payment, refund or fee), amount_cents and currency.

## Failure handling

If the job fails, someone is told.
