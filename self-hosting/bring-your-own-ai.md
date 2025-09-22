---
description: How to add your AI keys to self-hosted Quadratic
---

# Bring your own AI

## Enabling AI

If you want to enable AI in self-hosting you'll need to add your own AI provider API keys to the .env file located in the root directory.&#x20;

You can find the .env by navigating to the quadratic-selfhost folder and opening the .env file within the root directory. In the AI section you'll find a place for OpenAI and Anthropic keys. The easiest way to find and edit this file is through your terminal. Example: on Mac use `nano .env`  from the root directory, then scroll down until you find the AI environment variables; enter your AI key here.&#x20;

Once you've edited your .env you can stop and start the Docker containers from the quadratic-selfhost folder using the commands `./stop.sh` and `./start.sh`
