# Agentforce Quoting Agent

Salesforce Revenue Cloud + Agentforce project for quote creation, quote updates, discount changes, and AI-assisted quote email workflows.

## Overview

This project documents how I built an Agentforce Employee Agent in Salesforce Revenue Cloud to support quoting workflows through natural language. The agent is configured to create quotes, update quote line items, modify discounts, summarize quote output, and support quote email drafting through Einstein. The build flow includes pricing sync, Einstein enablement, Sales Emails, Agentforce activation, Quote Management topic setup, testing, permission-set access, and end-to-end quote generation inside Revenue Cloud.

## Business Problem

In many sales environments, quoting is still a manual, click-heavy process. Sales reps often move between accounts, opportunities, products, pricing, and email communication just to produce a customer-ready quote. That slows response time and creates unnecessary friction.

## Solution

I built an Agentforce Quoting Agent to streamline quote-related actions inside Salesforce. Instead of manually navigating multiple screens, users can interact with the agent using natural-language prompts to create and update quotes while staying within pricing and access guardrails.

## What This Project Demonstrates

- Salesforce Pricing data sync
- Einstein enablement
- Sales Emails enablement
- Agentforce activation
- Agentforce Employee Agent setup
- Quote Management topic configuration
- Enhanced event logging
- Conversation-based quote testing
- Permission-set based agent access
- Revenue Cloud quote generation
- Einstein-assisted quote email drafting

## Platform Setup

Before creating the agent, the environment must be prepared in a special Agentforce-enabled Developer Edition org connected to Trailhead. The setup flow includes syncing pricing data, enabling Einstein, enabling Sales Emails, and turning on Agentforce. The source also notes that this project currently uses the legacy builder while the newer Agentforce Builder is now generally available. :contentReference[oaicite:0]{index=0} :contentReference[oaicite:1]{index=1}

## Agent Configuration

The Quoting Agent is created as an **Agentforce Employee Agent**. During setup, the **General FAQ** topic is removed, the agent is named **Quoting Agent**, the API name is set to **Quoting_Agent**, the company context is set to **Quantum Bit**, and enhanced event logging is enabled. After creation, the **Quote Management** topic is added from the Asset Library and the agent is activated. :contentReference[oaicite:2]{index=2} :contentReference[oaicite:3]{index=3}

## Test Scenarios

### 1) Create a quote in Agent Builder
Prompt:
`Please create a quote for the EdgeMX account for Laptop Basic Bundle for 2 units for the Office Upgrade opportunity.`

Expected result:
A new quote is created with the Laptop Basic Bundle added as a quote line item. If needed, the fallback prompt is:
`Please show me the quote.` :contentReference[oaicite:4]{index=4}

### 2) Modify the quote
Prompt:
`Great, can you please add 5 units of Headset to this change quote too?`

Expected result:
The quote is updated to include 5 units of Headset. :contentReference[oaicite:5]{index=5}

### 3) Generate a discounted quote in Revenue Cloud
Prompt:
`Hi! Can you please create a quote for this account with 15 units of the Headset product. Please apply a 15% discount.`

Expected result:
A quote is generated for the selected account and opportunity with the requested discount. :contentReference[oaicite:6]{index=6}

### 4) Update the discount
Prompt:
`Please change the discount to 10% for the first product.`

Expected result:
The first product discount is updated from 15% to 10%. :contentReference[oaicite:7]{index=7}

## User Access Setup

To make the agent available to users, a permission set labeled **Agentforce User** is created, **Quoting Agent** is added under Agent Access, and the permission set is assigned to the target user. :contentReference[oaicite:8]{index=8}

## Quote Email Workflow

After generating the quote, the workflow continues in Revenue Cloud by opening the opportunity, selecting the quote, choosing **Email Quote**, sending through Salesforce, and drafting the email with Einstein using **Create Quote Email**. The example email is sent to **Rose Gonzalez** with the subject **New quote for your office upgrade**. :contentReference[oaicite:9]{index=9}

## Business Value

This project shows how Agentforce can improve real sales operations by reducing manual effort in quoting workflows. The main value is faster quote turnaround, less screen-by-screen navigation, more consistent quoting actions, and a smoother path from quote generation to customer communication. The source specifically describes Agentforce for Sales as helping teams generate accurate quotes faster while maintaining role-based permissions and system guardrails around valid products, pricing, and discounting. :contentReference[oaicite:10]{index=10}

## Skills Demonstrated

- Salesforce Agentforce
- Revenue Cloud
- Einstein for Sales
- Sales process automation
- Prompt-driven workflow design
- Quote Management configuration
- Permission set configuration
- AI-assisted sales workflows
- End-to-end testing and validation

## Repository Structure

```text
agentforce-quoting-agent/
├── README.md
├── docs/
│   ├── project-overview.md
│   ├── setup-steps.md
│   ├── testing-scenarios.md
│   ├── business-value.md
│   └── lessons-learned.md
├── prompts/
│   └── test-prompts.md
├── assets/
│   └── screenshots/
└── linkedin/
    └── linkedin-post.md