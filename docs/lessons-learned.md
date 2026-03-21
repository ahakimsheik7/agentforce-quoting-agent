# Lessons Learned

## Overview

This project provided a practical view of how Agentforce can be used inside a Salesforce sales workflow. Beyond the setup itself, the build highlighted several important lessons about dependencies, configuration, testing, access control, and business value.

## 1) Platform setup matters before agent setup

One of the biggest lessons from this project is that agent performance depends heavily on the platform being prepared correctly first.

Before the Quoting Agent could function as expected, the environment needed:
- pricing sync
- Einstein enabled
- Sales Emails enabled
- Agentforce enabled

Without these supporting features, the quoting workflow would be incomplete or fail during later steps. This reinforced an important implementation principle: AI configuration depends on core platform readiness.

## 2) Data readiness affects agent usefulness

The pricing sync step may look small, but it is important. Quote generation depends on having up-to-date pricing information available in the environment.

This shows that even when the user experience is conversational, the underlying business data still drives whether the agent can perform useful actions correctly.

## 3) Topics define what the agent can actually do

Creating the agent alone is not enough. The key business capability in this project came from adding the **Quote Management** topic from the Asset Library.

That was a useful design lesson:
the agent framework provides the shell, but the topic configuration shapes the actual job the agent can perform.

In other words, the usefulness of the agent is directly tied to the topics, instructions, and actions attached to it.

## 4) Testing should focus on action, not just response

Another important lesson is that testing an agent is not only about whether it gives a reasonable reply.

The stronger test is whether it can complete the intended business action.

In this project, useful validation meant confirming that the agent could:
- create a quote
- modify a quote
- update a discount
- surface the quote in Revenue Cloud
- support the email workflow

This is a more practical way to evaluate business AI systems, especially inside enterprise platforms.

## 5) Builder testing and app testing are both necessary

The project uses two different levels of testing:
- Builder testing
- Revenue Cloud workflow testing

That distinction matters.

Builder testing helps confirm that the topic and prompts are functioning. Revenue Cloud testing proves that the workflow works inside the actual business application context.

This showed that successful AI validation should happen both in the design environment and in the live user workflow.

## 6) Access control is part of implementation, not an afterthought

The permission set step is an important reminder that activation alone does not mean users can use the agent.

The agent still must be assigned through **Agent Access** and linked to the proper user. This highlights a broader enterprise lesson:
AI deployment includes access design, not just technical setup.

## 7) Prompt phrasing influences usability

The test prompts in this project are direct, structured, and context-rich. They include the account, opportunity, product, quantity, and discount request.

That demonstrates a helpful prompt design lesson:
clear prompts improve task execution, especially when the agent is expected to perform a specific record-based action.

This project reinforced the importance of using precise, business-oriented prompts during testing and implementation.

## 8) AI becomes more valuable when tied to the full workflow

A major takeaway from this project is that the real value of the agent is not limited to quote creation alone.

The workflow becomes stronger because it continues through:
- quote creation
- quote revision
- quote visibility
- quote email drafting
- quote sending

That makes the implementation feel operational, not experimental.

## 9) Einstein strengthens the final customer-facing step

The quote email drafting step adds practical value because it helps move from internal action to external communication.

This is an important lesson in workflow design:
AI becomes more useful when it supports the handoff between internal system activity and customer engagement.

## 10) Business value should be documented, not assumed

Another lesson from this project is that a strong portfolio implementation should clearly explain why the solution matters.

It is not enough to say an agent was built. It is stronger to connect the work to business outcomes such as:
- faster quote turnaround
- less manual effort
- improved sales efficiency
- smoother customer communication
- governed AI adoption inside CRM

Documenting this value makes the project more credible to recruiters, hiring managers, and stakeholders.

## 11) Portfolio framing matters

This project also reinforced the difference between a learning exercise and a portfolio asset.

A simple badge completion is useful for learning, but turning it into a GitHub project with:
- a clear README
- setup steps
- testing scenarios
- business value
- lessons learned
- LinkedIn summary

makes it much more valuable professionally.

## Final Takeaway

The biggest lesson from this project is that Salesforce AI is most compelling when it is tied to a real workflow, supported by proper setup, validated through business actions, and documented in a way that shows both technical skill and operational thinking.

The Agentforce Quoting Agent is a strong example of that approach.