# Voice & Text Healthcare Demo Bot

This n8n workflow demonstrates a Telegram bot that can handle both **text** and **voice messages** from users, providing AI-powered responses in both formats.

## Features

- Receives **text messages** from Telegram and replies in text.
- Receives **voice messages**, converts them to text, and generates a response.
- AI responses can be sent as both **text** and **voice**.
- Uses **Google Gemini (PaLM)** for AI text generation.
- Uses **Lemonfox API** for speech-to-text and text-to-speech conversions.
- Implements a **simple memory** to keep context of previous conversations.

## Workflow Overview

1. **Telegram Trigger** – Listens to messages from Telegram.
2. **If Node** – Checks if the message is voice or text.
3. **Get File + HTTP Request** – Downloads voice and converts it to text.
4. **Edit Fields** – Prepares the input for the AI agent.
5. **AI Agent (LangChain)** – Generates a response based on user input and context.
6. **If Node (Output)** – Determines whether to send response as text only or text + voice.
7. **Telegram Send Message / Audio** – Sends response back to the user.

