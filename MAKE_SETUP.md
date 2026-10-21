# Make setup guide

## Before you start
- A Gmail account you control.
- A Make account.
- Access to a Make AI provider or an AI integration supported in your Make account.
- Start with test messages; don't begin with your whole inbox.

## Build the scenario
1. Sign in to Make and select **Create a new scenario**.
2. Add a Gmail module: **Watch emails**.
3. Connect your Gmail account through Google's authorization screen.
4. Configure it to watch new messages. For the first test, limit the trigger to a test label or a small set of messages if the module supports that.
5. Add an AI text-generation / agent module. Use the built-in Make AI provider if it is available and suitable, or connect an AI provider you already use.
6. Paste the contents of `prompts/email_reply_agent.md` into the instructions/system prompt field.
7. Map the incoming message's sender, subject, and plain-text body into the AI input. Avoid sending unnecessary attachments or sensitive data to the model.
8. Add Gmail **Create a draft email** as the final action. Do not add **Send an email**.
9. Map:
   - **To:** original sender's email address.
   - **Subject:** generated reply subject, or original subject with `Re:` if needed.
   - **Body:** generated reply body only. If the AI output includes `SUMMARY:` and `SUBJECT:` labels, parse the fields first or ask the model to return structured fields using Make's supported output format.
10. If available, use a thread-aware reply-draft action and map the original thread ID. Otherwise, a new draft may not appear inside the original conversation.
11. Save the scenario.

## First test
1. Send a simple test message from a second email account, e.g. “Could you confirm our meeting on Friday? Please reply that you will check the schedule.”
2. Click **Run once** in Make.
3. Inspect the scenario execution and correct any unmapped fields.
4. Open Gmail → Drafts.
5. Verify the draft recipient, subject, tone, and facts.
6. Confirm no message was sent.
7. Only after successful tests, turn the scenario on.

## Recommended first-run restrictions
- Use a Gmail label such as `AI-DRAFT-TEST` if your trigger can filter by label.
- Exclude newsletters, bulk mail, spam, and messages sent by your own account.
- Don't process messages with highly sensitive personal, financial, medical, legal, or employment information until you have reviewed the privacy implications.
- Start with one email per run and inspect execution logs.
