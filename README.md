# AI Lead Follow-Up Automation

An n8n workflow that captures inbound leads and sends a personalized,
AI-generated response within seconds.

Built for savautomations, my freelance automation practice, after I kept
losing leads to slow reply times while carrying a full course load.

## Architecture

Webhook -> Set -> Basic LLM Chain (Anthropic API) -> Gmail

- **Webhook** receives the inbound lead payload from a form or CRM
- **Set** normalizes and maps the incoming fields
- **Basic LLM Chain** calls the Anthropic API (claude-haiku-4-5) with a
  prompt template that produces a consistent, on-brand reply
- **Gmail** sends the response and logs the thread

![Workflow](workflow.png)

## Setup

1. Import `workflow.json` into your n8n instance
2. Add your Anthropic API credential to the LLM Chain node
3. Connect a Gmail account to the Gmail node
4. Activate the workflow and point your form at the webhook URL

## Notes

Credentials are stripped from the exported workflow. Response latency is
typically under five seconds end to end.

Packaged version available at https://savarix.gumroad.com
