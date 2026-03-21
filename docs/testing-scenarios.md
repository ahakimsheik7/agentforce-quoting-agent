# Testing Scenarios

## Purpose

This document records the main test cases used to validate the Agentforce Quoting Agent after setup. The goal is to confirm that the agent can create quotes, update quote line items, adjust discounts, and support the quote email workflow inside Revenue Cloud.

## Testing Approach

The testing process is divided into two stages:

1. **Builder testing**
   - Validate agent behavior directly in Agentforce Builder
   - Confirm quote creation and quote modification

2. **Revenue Cloud testing**
   - Validate the agent in the actual app workflow
   - Confirm quote generation, discount updates, and quote email flow

This follows the project sequence from the source, where the agent is first tested in the conversation preview window and then used in Revenue Cloud for a full quote workflow. :contentReference[oaicite:0]{index=0} :contentReference[oaicite:1]{index=1}

---

## Test Case 1: Create a quote in Builder

### Objective
Validate that the agent can create a new quote from a natural-language prompt.

### Test Prompt
`Please create a quote for the EdgeMX account for Laptop Basic Bundle for 2 units for the Office Upgrade opportunity.`

### If Prompted
Select:
`Laptop Basic Bundle Product2`

### Expected Result
A new quote is created with the Laptop Basic Bundle products as a quote line item.

### Notes
If the quote does not immediately appear, use the fallback prompt:
`Please show me the quote.`

### Source Reference
This is the first test prompt provided in the guided build flow. :contentReference[oaicite:2]{index=2}

---

## Test Case 2: Modify the quote in Builder

### Objective
Validate that the agent can update an existing quote by adding a new product and quantity.

### Test Prompt
`Great, can you please add 5 units of Headset to this change quote too?`

### Expected Result
The quote updates successfully and includes 5 units of Headset.

### Notes
This confirms that the Quote Management topic is functioning for quote modification, not just quote creation.

### Source Reference
The guide explicitly uses this test to confirm the updated quote includes 5 Headset units. :contentReference[oaicite:3]{index=3}

---

## Test Case 3: Create a discounted quote in Revenue Cloud

### Objective
Validate that the agent can generate a quote from the account context in Revenue Cloud and apply a discount.

### Precondition
- Revenue Cloud app is open
- Account selected: `EdgeMX`
- Agentforce conversation panel is open

### Test Prompt
`Hi! Can you please create a quote for this account with 15 units of the Headset product. Please apply a 15% discount.`

### If Prompted
Select:
`Office Upgrade`

### Expected Result
A new quote is created for the selected account and opportunity with:
- product: Headset
- quantity: 15
- discount: 15%

### Notes
After creation, enter:
`Please show me the quote.`

This helps confirm the quote was generated and allows the tester to review the result. :contentReference[oaicite:4]{index=4}

---

## Test Case 4: Update the discount

### Objective
Validate that the agent can modify an existing quote by revising the discount amount.

### Test Prompt
`Please change the discount to 10% for the first product.`

### Expected Result
The quote updates successfully and the first product discount changes from 15% to 10%.

### Notes
This confirms the agent can handle quote adjustment actions after initial quote generation.

### Source Reference
This is the second Revenue Cloud quote prompt used in the guided exercise. :contentReference[oaicite:5]{index=5}

---

## Test Case 5: Open and review the quote record

### Objective
Validate that the generated quote can be reviewed from the linked opportunity record.

### Steps
1. Open the opportunity from the Agentforce conversation panel.
2. If the opportunity does not appear in the panel, open the **Opportunities** tab manually.
3. Open the **Related** tab.
4. Select the newly created quote.

### Expected Result
The quote is visible from the opportunity’s related records and ready for further actions such as email.

### Notes
This confirms the quote exists in the core Revenue Cloud workflow, not only in the chat conversation. :contentReference[oaicite:6]{index=6}

---

## Test Case 6: Draft and send the quote email

### Objective
Validate the final workflow step of sending the generated quote to the customer through Salesforce using Einstein.

### Steps
1. Open the quote record.
2. Click the menu dropdown.
3. Select **Email Quote**.
4. Choose **No, Send through Salesforce**.
5. Enter:
   - To: `Rose Gonzalez`
   - Subject: `New quote for your office upgrade`
6. Click **Draft with Einstein**
7. If needed, select **Use pre-made instructions**
8. Select **Create Quote Email**
9. Select the most recent quote for Office Upgrade
10. Click **Continue**
11. Review the draft
12. Click **Done**
13. Click **Send**

### Expected Result
The quote email is generated and sent through Salesforce.

### Notes
If the email body appears blank initially, the source notes that it may still be loading and this does not necessarily block challenge completion. :contentReference[oaicite:7]{index=7}

---

## Validation Checklist

Use this checklist after testing:

- [ ] Pricing data was synced
- [ ] Einstein was enabled
- [ ] Sales Emails was enabled
- [ ] Agentforce was enabled
- [ ] Quoting Agent was created successfully
- [ ] Quote Management topic was added
- [ ] Agent was activated
- [ ] Builder quote creation worked
- [ ] Builder quote update worked
- [ ] Permission set access was assigned
- [ ] Revenue Cloud quote creation worked
- [ ] Discount update worked
- [ ] Quote email draft worked
- [ ] Quote email was sent

---

## Success Criteria

The Quoting Agent is considered successfully validated when it can:

1. Create a quote from natural-language instructions
2. Modify quote contents
3. Apply and update discounts
4. Surface the quote in Revenue Cloud
5. Support Einstein-assisted quote email drafting
6. Complete the send flow through Salesforce

---

## Key Testing Insight

The most important validation is not only whether the agent answers correctly in Builder, but whether it performs useful actions inside the full sales workflow. In this project, that means the agent successfully supports quote creation, quote revision, and customer communication from the same end-to-end flow.