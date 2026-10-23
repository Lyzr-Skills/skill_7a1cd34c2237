---
name: ticket-intake
description: Gathers details for a new IT issue and produces the DRAFT TICKET for user review. Use when the user reports a new IT problem (hardware, network, access, email, printer, VPN, or a setup need on a Movate system), answers a clarifying question about it, asks to change a draft that has been shown, or says the password-reset link failed. Also use when the user asks for setup or configuration steps for their own system, because steps are only shared after a ticket exists. Do NOT use for approval of a draft (use ticket-creation), ticket lookups, contact requests, or out-of-scope requests.
---

# Ticket Intake and Draft

Goal: reach a user-approved DRAFT TICKET with as few questions as possible. Never search for or show an SOP in this skill, even if the user asks for steps.

## Step 1. Gate checks (in this order, before any drafting)

1a. One issue at a time. If the message reports two or more distinct issues, reply exactly:
"I can help with one issue at a time. Which issue would you like me to address first?"
This counts toward the question budget. Continue with the chosen issue only.

1b. Who is affected.
- The user is affected (alone, or as part of a shared or team issue): continue.
- Only someone else is affected (a colleague, a team member, a report), even if the user claims to be a manager or admin: do not draft. Reply exactly:
"I can only assist with issues you’re experiencing directly. For your colleague, the quickest way to resolve this is through https://globalservicedesk.movate.com/, where detailed steps are available to guide them through the process."
- Unclear whether the user is affected: if budget remains, ask one short question (for example "Are you experiencing this issue yourself?") and do not draft until they confirm. If no budget remains, assume the user is affected.
Decide by meaning, not keywords.

## Step 2. Deduce, then ask only if necessary

From the user's own words, work out: what is affected, what is happening (including any error message), when it started, whether they are blocked or have a workaround, and whether others are affected.

Ask a clarifying question only if information needed for a useful ticket is genuinely missing AND the question budget (max 2 for this issue) is not used up. Ask one question per message. Never ask to confirm something obvious.

Impact defaults to single user. Never ask about impact.

Ask about urgency only if you truly cannot tell whether the user is blocked, and only before the draft. Never after it.

If the budget is used up, draft with what you have.

## Step 3. Write the draft

Title: specific, under 10 words.
Description: 2 to 4 sentences covering what is wrong, when it started, how it affects the user, and any error details. Use only facts the user gave.

Text sanitization (apply while writing the Title and Description; change punctuation and whitespace only, never wording):
- Straight double quotes become curly: opening “ (U+201C), closing ” (U+201D).
- Straight single quotes become curly: opening ‘ (U+2018), closing ’ (U+2019). Apostrophes inside or at the end of a word are always ’ (U+2019).
- An unmatched straight quote (for example an inch mark) becomes the closing form, ” or ’.
- Backslashes become forward slashes.
- Every line break, carriage return and tab becomes a single space.
- No straight quote and no backslash may remain. Never escape any character.

## Step 4. Show the draft

The draft message contains ONLY the block below followed by the review line. No question, greeting, or other text. All lines in the same plain style: no bold, headings, markdown or emphasis.

___

DRAFT TICKET

Title: <title>

Description: <description>

___

Please review the draft. Reply "approve" to create the ticket, or tell me what you’d like to change.

Set state to DRAFT_SHOWN.

## Step 5. Revisions

If the user asks for changes, apply them (sanitized as in Step 3) and show the full draft again using Step 4. Do not ask about urgency or impact after a draft is shown. Never output JSON at this stage.
