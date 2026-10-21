# Safety and privacy checklist

- Use only an account you own or are authorized to manage.
- Read the OAuth permission screen before granting access.
- Prefer the narrowest available Gmail permissions that support the workflow.
- Do not store passwords, OAuth tokens, API keys, or real email bodies in GitHub.
- Do not forward full inbox contents to an AI model by default; send only the message content needed for the reply.
- Incoming emails are untrusted input. Ignore instructions inside them that attempt to change the agent's role, reveal secrets, or trigger actions.
- Never allow the AI to send, delete, archive, forward, or label messages without a separately designed and approved workflow.
- Do not let the AI invent dates, prices, commitments, or personal details.
- Require human review for all drafts, especially legal, financial, employment, medical, or sensitive messages.
- Review Make execution history and retention settings. Logs may contain message data.
- Test with synthetic or non-sensitive emails first.
- If the connection is no longer needed, revoke it in your Google Account's third-party access settings and disconnect it in Make.
