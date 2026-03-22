# Test Prompts

## Purpose

This file captures the main prompts used to test the Agentforce Quoting Agent in both Agentforce Builder and Revenue Cloud.

These prompts are designed to validate that the agent can perform practical quote-related actions such as quote creation, quote modification, discount updates, quote review, and support for the quote email workflow.

---

## Builder Prompts

### 1) Create a quote
Prompt:
`Please create a quote for the EdgeMX account for Laptop Basic Bundle for 2 units for the Office Upgrade opportunity.`

Expected outcome:
A new quote is created for the EdgeMX account with Laptop Basic Bundle added as a quote line item.

If prompted:
Select `Laptop Basic Bundle Product2`

Fallback prompt:
`Please show me the quote.`

---

### 2) Update the quote
Prompt:
`Great, can you please add 5 units of Headset to this change quote too?`

Expected outcome:
The existing quote is updated to include 5 units of Headset.

---

## Revenue Cloud Prompts

### 3) Create a discounted quote
Prompt:
`Hi! Can you please create a quote for this account with 15 units of the Headset product. Please apply a 15% discount.`

Expected outcome:
A quote is created for the selected account and opportunity with:
- product: Headset
- quantity: 15
- discount: 15%

If prompted:
Select `Office Upgrade`

Follow-up prompt:
`Please show me the quote.`

---

### 4) Revise the discount
Prompt:
`Please change the discount to 10% for the first product.`

Expected outcome:
The quote is updated and the first product discount changes from 15% to 10%.

---

## Prompt Design Notes

These prompts work well because they are:
- specific
- action-oriented
- grounded in account and opportunity context
- clear about quantities and discount values

This helps the agent perform structured quoting actions more reliably.

---

## Key Prompting Pattern

A strong quoting prompt usually includes:

- account context
- opportunity context
- product name
- quantity
- discount request if needed
- follow-up review request

Example pattern:

`Please create a quote for [account] for [product] with [quantity] units for the [opportunity].`

Discount version:

`Please create a quote for this account with [quantity] units of [product]. Please apply a [discount]% discount.`

---

## Why This Matters

Prompt quality directly affects how well the agent can execute quote-related actions.

In this project, clear and business-specific prompts helped validate that the Quoting Agent could support real operational tasks rather than only provide conversational responses.