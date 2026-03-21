# Setup Steps

## Goal

This document records the full setup flow for building an Agentforce Quoting Agent in Salesforce Revenue Cloud, from org preparation to agent activation and quote generation.

## 1) Create the required org

This project starts with a special Agentforce-enabled Developer Edition org for the Quoting Agent experience.

Steps:
1. Sign up for the special Developer Edition org for Quoting Agent.
2. Use an active email address.
3. Create a unique username in email format.
4. Verify the account from the activation email.
5. Set your password and challenge question.
6. Log in to the Developer Edition org.
7. Connect the org to Trailhead from the challenge page.

Why this matters:
The project uses a special org designed for this badge flow and Agentforce quoting setup. :contentReference[oaicite:0]{index=0}

## 2) Sync pricing data

Before creating the agent, pricing data must be synced so the latest pricing information is available.

Steps:
1. Open **Setup**.
2. Search for **Salesforce Pricing Setup**.
3. In **Sync Pricing Data**, click **Sync**.
4. Click **Confirm**.

Why this matters:
The source explains that pricing sync ensures the latest pricing information is available in decision tables and for users. :contentReference[oaicite:1]{index=1}

## 3) Enable Einstein

Steps:
1. In **Setup**, search for **Einstein Setup**.
2. Turn the **Einstein** toggle to **On**.
3. Refresh the browser window.

This is one of the required supporting features before the agent can be used. :contentReference[oaicite:2]{index=2}

## 4) Enable Sales Emails

Steps:
1. In **Setup**, search for **Einstein for Sales**.
2. Turn on **Sales Emails**.
3. Refresh the browser window.

This prepares the quote email drafting workflow used later in the project. :contentReference[oaicite:3]{index=3}

## 5) Enable Agentforce

Steps:
1. In **Setup**, search for **Agentforce Agents**.
2. Turn the **Agentforce Agents** toggle to **On**.
3. Refresh the browser window.

Agentforce must be enabled before creating the Quoting Agent. :contentReference[oaicite:4]{index=4}

## 6) Create the Quoting Agent

Steps:
1. Open **Agentforce Agents**.
2. Click **+ New Agent**.
3. Select **Agentforce Employee Agent**.
4. Click **Next**.
5. In topic selection, remove **General FAQ**.
6. Click **Next**.
7. On the customization screen, enter:
   - **Name:** `Quoting Agent`
   - **API Name:** `Quoting_Agent`
   - **Description:** leave as is
   - **Role:** leave as is
   - **Company:** `Quantum Bit provides integration software for connecting applications, data and devices. They produce specialized hardware and direct-to-consumer services but primarily work with medium and large businesses to modernize their integration infrastructure.`
8. Enable **Keep a record of conversations with enhanced event logs**.
9. Click **Next**.
10. Leave the data sources selection as is.
11. Click **Create**.

Why this matters:
This creates the Employee Agent used for quote creation and updates, and the event logs help review behavior during testing. :contentReference[oaicite:5]{index=5}

## 7) Add the Quote Management topic

After creating the agent, add the topic that powers quoting actions.

Steps:
1. Inside the agent, click **New**.
2. Select **Add from Asset Library**.
3. Select **Quote Management** from the topic list.
4. Click **Finish**.
5. Click **Activate**.
6. If a popup appears, click **Ignore & Activate**.

Why this matters:
The source states that Agentforce Quoting uses the instructions in the Quote Management topic and actions based on Salesforce flows to generate and manage quotes. :contentReference[oaicite:6]{index=6} :contentReference[oaicite:7]{index=7}

## 8) Test the agent in Builder

Before assigning users, test the agent inside the builder.

### Test A: Create a quote
Prompt:
`Please create a quote for the EdgeMX account for Laptop Basic Bundle for 2 units for the Office Upgrade opportunity.`

If prompted:
Select `Laptop Basic Bundle Product2`.

Expected result:
A new quote is created with Laptop Basic Bundle as a quote line item.

Fallback prompt:
`Please show me the quote.`

### Test B: Modify the quote
Prompt:
`Great, can you please add 5 units of Headset to this change quote too?`

Expected result:
The quote updates to include 5 Headset units.

When done:
Click the back arrow to exit Agentforce Builder.

These tests confirm the agent can create and modify quotes before rollout. :contentReference[oaicite:8]{index=8}

## 9) Create a permission set for access

Once the agent works, give users access.

Steps:
1. Go to **Setup**.
2. Search for **Permission Sets**.
3. Click **New**.
4. Enter:
   - **Label:** `Agentforce User`
   - **API Name:** `Agentforce_User`
   - **License:** None
5. Click **Save**.
6. Scroll down and click **Agent Access**.
7. Click **Edit**.
8. Add **Quoting Agent**.
9. Click **Save**.
10. Click **Manage Assignments**.
11. Click **Add Assignment**.
12. Select your logged-in system admin user.
13. Click **Next** → **Assign** → **Done**.

Why this matters:
The agent must be added to a permission set and assigned to users before they can use it. :contentReference[oaicite:9]{index=9} :contentReference[oaicite:10]{index=10}

## 10) Generate a quote in Revenue Cloud

Now test the real workflow in the app.

Steps:
1. Open the **App Launcher**.
2. Search for and open **Revenue Cloud**.
3. Open the **Accounts** tab.
4. Change the view to **All Accounts**.
5. Select **EdgeMX**.
6. Open the **Agentforce** conversation panel.
7. Paste this prompt:

`Hi! Can you please create a quote for this account with 15 units of the Headset product. Please apply a 15% discount.`

8. If prompted, select **Office Upgrade** as the opportunity.
9. Enter:

`Please show me the quote.`

10. Then enter:

`Please change the discount to 10% for the first product.`

Expected result:
A quote is created and then updated with the revised discount. :contentReference[oaicite:11]{index=11} :contentReference[oaicite:12]{index=12}

## 11) Email the quote

Finish the workflow by drafting and sending the quote email.

Steps:
1. Open the related **Opportunity** from the Agentforce panel or from the Opportunities tab.
2. Open the **Related** tab.
3. Select the new quote from the quote list.
4. Open the menu dropdown.
5. Click **Email Quote**.
6. Choose **No, Send through Salesforce**.
7. Enter:
   - **To:** `Rose Gonzalez`
   - **Subject:** `New quote for your office upgrade`
8. Click **Draft with Einstein**.
9. If needed, choose **Use pre-made instructions**.
10. Select **Create Quote Email**.
11. Choose the most recent quote for **Office Upgrade**.
12. Click **Continue**.
13. Review the draft.
14. Click **Done**.
15. Click **Send**.

Why this matters:
This completes the end-to-end quoting workflow from agent conversation to customer communication. :contentReference[oaicite:13]{index=13}

## Result

At the end of this setup, the Quoting Agent is:
- enabled
- activated
- tested
- assigned to a user
- used inside Revenue Cloud
- capable of generating and emailing quotes

This is the core implementation flow for the portfolio project.