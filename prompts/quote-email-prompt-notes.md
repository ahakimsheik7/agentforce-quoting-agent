# Quote Email Prompt Notes

## Purpose

This file documents the email drafting portion of the Agentforce Quoting Agent workflow.

After the quote is created and reviewed in Revenue Cloud, Einstein is used to help draft the customer-facing quote email. This is an important part of the workflow because it connects internal quote generation with external customer communication.

---

## Workflow Context

The quote email step happens after:

- the quote has been created
- the quote has been reviewed
- any needed discount changes have been made
- the user is ready to send the quote to the customer

The email is sent through Salesforce using the built-in quote email flow and Einstein drafting support.

---

## Email Workflow Steps

1. Open the related Opportunity.
2. Go to the **Related** tab.
3. Select the newly created quote.
4. Open the action menu.
5. Click **Email Quote**.
6. Choose **No, Send through Salesforce**.
7. Enter the recipient and subject.
8. Click **Draft with Einstein**.
9. If needed, choose **Use pre-made instructions**.
10. Select **Create Quote Email**.
11. Select the most recent quote.
12. Continue to generate the draft.
13. Review the generated message.
14. Send the email.

---

## Example Email Inputs

### Recipient
`Rose Gonzalez`

### Subject
`New quote for your office upgrade`

These values were used in the guided quoting workflow.

---

## What Einstein Adds

Einstein helps generate the initial draft of the quote email so the user does not need to write the message from scratch.

This improves workflow efficiency by:

- reducing manual writing effort
- helping sales users move faster
- supporting more consistent communication
- speeding up customer follow-up after quote creation

---

## Business Value

The quote email step matters because business value does not stop at creating the quote.

A complete quoting workflow should also help the team move from:

- internal quote preparation
to
- customer-ready communication

That makes the Quoting Agent workflow more practical and more valuable in a real sales environment.

---

## Design Insight

This part of the project shows that AI is more useful when it supports the full workflow, not just the first transaction.

In this case:
- Agentforce supports quote actions
- Einstein supports the communication step

Together, they create a smoother quote-to-customer process inside Salesforce.

---

## Notes for Portfolio Use

This section is useful in the project because it shows that the Quoting Agent workflow includes both:

- operational sales activity
- customer communication enablement

That makes the project stronger as a business workflow example, not just an agent setup exercise.

---

## Summary

The quote email drafting step extends the value of the Agentforce Quoting Agent by helping users complete the final communication step after quote generation.

This makes the overall solution more complete, more practical, and more aligned with real sales operations.