# Project Overview

## Project Name

Agentforce Quoting Agent

## Summary

This project documents the setup and testing of an Agentforce Employee Agent inside Salesforce Revenue Cloud for quote-related workflows. The agent is designed to support internal sales users by turning natural-language requests into quoting actions such as quote creation, quote updates, discount changes, quote review, and AI-assisted quote email drafting.

The implementation follows an end-to-end workflow that begins with environment preparation and feature enablement, continues through agent creation and topic configuration, and finishes with testing, user access assignment, quote generation, and quote email delivery.

## Project Objective

The main objective of this project is to demonstrate how Salesforce Agentforce can improve a real sales workflow rather than operate only as a conversational interface.

The project focuses on showing how a quoting process can be simplified by allowing a sales user to ask the system to perform actions such as:

- create a quote for an account and opportunity
- add products to a quote
- revise product discounts
- show the quote
- assist with customer-facing quote email drafting

## Business Context

Quoting is an important part of the sales cycle, but it is often manual and repetitive. A sales user may need to move through several screens in Salesforce to prepare a quote, update products, apply pricing changes, and then email the result to a customer.

This project presents a more efficient model where the user works through an Agentforce conversation panel and allows the platform to carry out much of the operational work.

## Core Components

The project includes the following major components:

- special Agentforce-enabled Developer Edition org
- Salesforce Pricing data sync
- Einstein enablement
- Sales Emails enablement
- Agentforce enablement
- Agentforce Employee Agent setup
- Quote Management topic from Asset Library
- enhanced event logging
- permission-set based user access
- Revenue Cloud quote generation workflow
- Einstein-assisted quote email workflow

## Agent Design

The agent used in this project is configured as an internal Employee Agent rather than a public-facing support agent.

Key setup details include:
- Agent name: `Quoting Agent`
- API name: `Quoting_Agent`
- Company context: `Quantum Bit`
- Topic added: `Quote Management`

The Quote Management topic is central to the project because it provides the quoting-related instructions and actions required for quote generation and management.

## Workflow Covered

This project covers the following workflow sequence:

1. Prepare the org
2. Enable supporting features
3. Create the Quoting Agent
4. Add the Quote Management topic
5. Activate the agent
6. Test quote creation in Builder
7. Test quote modification in Builder
8. Create a permission set for access
9. Assign the user
10. Use the agent inside Revenue Cloud
11. Generate a quote with discount
12. Update the discount
13. Open the created quote
14. Draft and send the quote email with Einstein

## Testing Scope

Testing in this project focuses on whether the agent can successfully complete useful actions, not only whether it responds conversationally.

The tested actions include:

- quote creation from a prompt
- quote modification after creation
- discount application
- discount revision
- quote visibility in Revenue Cloud
- quote email drafting through Einstein
- quote send workflow through Salesforce

## Why This Project Is Valuable

This project is valuable because it demonstrates a practical use case for Salesforce AI inside a business workflow. It shows how Agentforce can be tied to operational outcomes such as faster quote turnaround, less manual navigation, more intuitive user interaction, and smoother movement from quote creation to customer communication.

It also highlights that AI workflows in Salesforce can remain governed through platform configuration, access controls, and business rules.

## Skills Demonstrated

This project demonstrates hands-on skills in:

- Salesforce Agentforce
- Revenue Cloud
- Einstein for Sales
- AI-assisted workflow design
- prompt-based task execution
- permission set configuration
- user access control
- workflow testing and validation
- sales process automation

## Intended Use of This Repository

This repository is intended to serve as:

- a portfolio project
- a hands-on implementation record
- a GitHub showcase for Salesforce AI work
- a reference for future Agentforce workflow projects

## Conclusion

The Agentforce Quoting Agent project shows how conversational AI can be embedded into Salesforce to support a real business process. Rather than functioning only as a chat experience, the agent becomes part of a governed quoting workflow that supports productivity, efficiency, and better sales operations.