# Friendly Text Moderation Demo

Stack:

- Vibe coded with ** **ChatGPT-5.2

- The Hugging Face API running [Duc Haba's Friendly Text Moderation](https://huggingface.co/spaces/duchaba/Friendly_Text_Moderation).

- Notion.com - the cloud-based workspace platform

Use Notion as the UI. Text Friendly’s Moderation web app embed the inside.

[embed: https://text-moderation-demo.netlify.app/](https://text-moderation-demo.netlify.app/)

Architecture:
Notion (presentation layer)
↓ embed
Netlify-hosted mini app
↓ API call
Hugging Face Space
