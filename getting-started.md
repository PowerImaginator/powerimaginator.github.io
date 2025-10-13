---
title: Getting Started
layout: default
permalink: /getting-started
---

# Getting Started

PowerImaginator adopts existing image generation and depth estimation models as a foundation for its 3D generative capabilities. These models require modern, powerful GPUs to run efficiently.

- If you have a recent NVIDIA GPU or Apple Silicon device, you can set up a **local server** for free using the hardware you already own.
- Otherwise, you'll likely want a **cloud-hosted server**. This setup guide uses Modal, since it provides a generous $30 worth of credits for free every month. If you prefer to use Vast.ai, RunPod, or any other service, simply follow the local setup instructions inside your cloud instance, and use the IP address of the cloud instance as the Server URL in the client.

## Set up your server

- Install [Git](https://git-scm.com/downloads) and [uv](https://docs.astral.sh/uv/getting-started/installation/).
- Open Command Prompt (Windows) or Terminal (macOS).
- `git clone https://github.com/PowerImaginator/powerimaginatorserver.git`
- `cd powerimaginatorserver`
- `uv sync`

### Running a local server

*Note: Ignore these steps if you prefer to [run a cloud server](#running-a-cloud-server).*

If you want to run the PowerImaginator server locally on your computer with a PyTorch-compatible GPU:

- `export POWERIMAGINATOR_API_TOKENS=password123` (or any password you prefer)
- `uv run fastapi run main_module/main.py`

### Running a cloud server

*Note: Ignore these steps if you prefer to [run a local server](#running-a-local-server).*

If you want to run PowerImaginator on Modal, follow these instructions:

- Create an account: [https://modal.com/signup](https://modal.com/signup)
- Click on the **Secrets** tab in the top navigation bar.
- Click the **Create new secret** button.
- Select the **Custom** type.
- In the **Name** field, enter `powerimaginatorserver-secrets`
- In the **Environment variables** table, set **Key** to `POWERIMAGINATOR_API_TOKENS` and **Value** to a password, or comma-separated list of passwords. We recommend choosing a strong password to protect your server from unauthorized access.
- Click **Done**
- Go back to Command Prompt (Windows) or Terminal (macOS). Optionally `cd powerimaginatorserver` if you closed it after the previous setups.
- `uv run modal setup` and follow instructions to authenticate your device with Modal.
- `uv run modal deploy modal_wrapper.py`
- Go back to your browser and click on the **Apps** tab on the Modal dashboard.
- Click on `entry` in the **Live Apps** section.
- Make a note of the endpoint URL. It should follow this format: `https://your_username--powerimaginatorserver-entry.modal.run`

## Install the client app

Whew! You're almost finished 😄

Go to the [powerimaginatorclient GitHub Releases page](https://github.com/PowerImaginator/powerimaginatorclient/releases) and download the top `.zip` archive (Windows) or `.dmg` bundle (macOS). Simply extract the ZIP file (Windows) or double-click the DMG (macOS) and drag PowerImaginator to the Applications folder.

### A note for macOS users

When opening the client app, you'll see a warning that the app has not been reviewed by Apple. This is normal (we don't pay $99 every year to join their developer program) - simply follow [these instructions](https://support.apple.com/guide/mac-help/open-a-mac-app-from-an-unknown-developer-mh40616/mac) to allow it to run. ***Important**: please make sure you only download PowerImaginator from its [official GitHub Releases page](https://github.com/PowerImaginator/powerimaginatorclient/releases) to avoid malware on other sites.*

# Congratulations!

You're now ready to create 3D scenes with PowerImaginator! Simply launch the client app on your device, enter your server credentials, and click **Connect**.

- If you set up a local server, leave the Server URL as `http://localhost:8000`, and then enter the API token you assigned to the `POWERIMAGINATOR_API_TOKENS` variable.
- If you set up a cloud server, set the Server URL to the URL you noted in the final step (e.g. `https://your_username--powerimaginatorserver-entry.modal.run`) and enter the API token you assigned to the `POWERIMAGINATOR_API_TOKENS` variable when creating the secret.

Enjoy, and please chat with us on [Discord](https://discord.gg/Vk3Wh5ZQYD) or try hacking the source code from [GitHub](https://github.com/PowerImaginator)! If this is your first time using PowerImaginator, check out the video on our [home page](/) for a quick tutorial.
