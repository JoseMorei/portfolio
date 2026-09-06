# Friendly Text Moderation Demo

Stack:

- Vibe coded with **ChatGPT-5.2**

- The Hugging Face API running [Duc Haba's Friendly Text Moderation](https://huggingface.co/spaces/duchaba/Friendly_Text_Moderation).

- [Netlify](https://www.netlify.com/) - hosting the mini app that fronts the API.

The demo is embedded directly in this page, which acts as the presentation layer.

<iframe src="https://text-moderation-demo.netlify.app/"
        title="Friendly Text Moderation demo"
        width="100%" height="620" loading="lazy"
        style="border:1px solid var(--md-default-fg-color--lightest); border-radius:4px;">
</iframe>

If the frame does not load, open it directly:
<https://text-moderation-demo.netlify.app/>

Architecture:

```
This page (presentation layer)
  ↓ embed
Netlify-hosted mini app
  ↓ API call
Hugging Face Space
```
