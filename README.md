# AI Lead Follow-Up Automation

An n8n workflow that captures an inbound lead and sends a personalized,
AI-generated reply in under a minute.

Built for my freelance automation practice after I kept losing leads to
slow response times.

## Architecture

Webhook → Set (field normalization) → Basic LLM Chain (Anthropic API) → Gmail

- **Webhook** receives the inbound lead payload from a web form
- **Set** normalizes and maps incoming fields
- **LLM Chain** calls the Anthropic API with a prompt template tuned for
  consistent tone and structure
- **Gmail** sends the reply and logs the thread

## Notes

Self-hosted after the cloud trial expired. Response latency is typically
under a minute end to end.

Workflow export to be published here once credentials are fully stripped.
