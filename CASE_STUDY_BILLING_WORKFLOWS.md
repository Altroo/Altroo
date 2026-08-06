# Billing Platform — Reliable Document Workflows

## What this demonstrates

I built the backend and frontend foundations for a business billing platform that manages clients, articles, quotes, delivery notes, pro forma invoices, customer invoices, credit notes, and payments.

This is not presented as a customer-growth story. It is engineering proof: public code, business workflow depth, and current test evidence.

## The engineering problem

Billing documents look similar, but small inconsistencies create expensive failures: incorrect totals, broken create/edit behavior, missing permissions, invalid status transitions, lost line items, or payments linked to the wrong invoice.

The platform treats these as connected workflows instead of unrelated CRUD screens:

- shared document forms and line-item behavior across quotes, delivery notes, and invoices;
- company-scoped API access and role-aware payment controls;
- create, edit, status-change, search, pagination, and document-number flows;
- totals, discounts, PDF/export paths, unpaid invoices, and document conversions;
- explicit loading, empty-data, API-error, and permission-denied states.

## Current verification

Verified locally on 2026-08-06:

- `bun x tsc --noEmit` — passed with zero TypeScript errors;
- four targeted Jest suites — passed;
- 62 targeted tests — passed across quote, customer-invoice, delivery-note, and payment forms.

The targeted tests cover add/edit modes, API query and mutation wiring, status updates, validation and routes, permission gates, loading states, empty data, API errors, and payment-data variations.

These results verify the named frontend workflows, not the entire platform or its backend test suite.

## Public code

- [Django REST backend](https://github.com/Altroo/facturation_backend)
- [Next.js frontend](https://github.com/Altroo/facturation_frontend)

## Relevance to client work

This is the kind of system I can rescue or extend for an agency or product team: business-critical Django/React workflows where permissions, state, calculations, tests, and a clean handoff matter more than a superficial demo.
