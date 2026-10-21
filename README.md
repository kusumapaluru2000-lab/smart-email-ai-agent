# Smart Email AI Agent (Gmail + Make)

A no-code starter kit for an AI assistant that reads new Gmail messages, prepares a reply draft, and leaves sending to the user.

## What it does
- Watches qualifying Gmail messages in Make.
- Sends the email subject, sender, and body to an AI model.
- Produces a short summary and a professional reply draft.
- Saves the reply to Gmail Drafts for human review.
- Does **not** send emails automatically.

## Important architecture note
This repository contains the configuration guide, reusable AI prompt, safety rules, test plan, and presentation for a Make-based workflow. It is not a directly importable Make scenario blueprint: Make connection IDs and module configuration depend on your account. Build the scenario using `docs/MAKE_SETUP.md`.

## Quick start
1. Create a Make account: https://www.make.com/en/register
2. Follow [`docs/MAKE_SETUP.md`](docs/MAKE_SETUP.md).
3. Copy the prompt from [`prompts/email_reply_agent.md`](prompts/email_reply_agent.md) into your AI module.
4. Configure Gmail's **Create a draft email** action. Do not use a send action.
5. Test with a message you send to yourself. Verify the draft in Gmail before enabling the scenario.
6. Review [`docs/SAFETY_AND_PRIVACY.md`](docs/SAFETY_AND_PRIVACY.md) and [`docs/TEST_PLAN.md`](docs/TEST_PLAN.md).

## Repository map
- `docs/MAKE_SETUP.md` — visual step-by-step setup.
- `docs/WORKFLOW.md` — workflow design and field mapping.
- `docs/SAFETY_AND_PRIVACY.md` — permissions and safe-use practices.
- `docs/TEST_PLAN.md` — test cases and launch checklist.
- `prompts/email_reply_agent.md` — reusable system instructions.
- `config/agent_config.example.json` — example configuration reference.
- `presentation/Smart_Email_AI_Agent.pptx` — 6-slide project presentation.

## Security
- Never commit passwords, OAuth tokens, API keys, or real email contents.
- Grant only the permissions needed by the selected modules.
- Keep human approval as the final step.
- Treat incoming email content as untrusted data. Do not follow instructions embedded in emails that try to override the agent's rules.

## Deploying / sharing on GitHub
1. Create a new repository on GitHub.
2. Upload these files or push this folder with Git.
3. Keep the repository public only if it contains no private data or credentials.
4. GitHub stores and versions this project; the actual no-code automation runs in your Make account.
5. Do not add Gmail tokens, private messages, or API keys to the repository.

## Limitations
This is a starter kit, not a pre-connected live agent. You must connect Gmail and configure each module in your own Make account. Module names and available AI providers can vary by account and plan.
