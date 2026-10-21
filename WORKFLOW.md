# Workflow design and mapping

## Flow
`Gmail: Watch emails` → `AI: Draft a reply` → `Gmail: Create a draft email` → human reviews and sends.

## Input to AI
Pass only what is needed:
- Sender name/address
- Original subject
- Plain-text email body
- Optional: limited relevant thread context, if supported and appropriate

## Suggested AI output
Prefer structured fields if your AI module supports JSON or a structured response:
- `summary`: 1–2 sentence summary
- `reply_subject`: subject line
- `reply_body`: ready-to-review body

If structured output isn't available, use clear delimiters and configure parsing before mapping the reply body to Gmail.

## Gmail draft fields
- Recipient: sender address from the triggering email
- Subject: generated reply subject
- Body: generated reply body
- Thread: original thread ID if the selected Gmail action supports it

## Human approval
The draft is the approval checkpoint. The user checks recipient, quoted context, claims, attachments, and tone before manually sending.
