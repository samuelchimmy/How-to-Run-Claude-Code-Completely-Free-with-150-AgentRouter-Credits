## Learn how to set up Anthropic's powerful CLI tool (Claude Code) for free using AgentRouter. Get $200 in registration credits.


![Image description](https://dev-to-uploads.s3.us-east-2.amazonaws.com/uploads/articles/qxoq5ppscg4colxr3obk.png)

Claude Code is Anthropic's official CLI-based AI coding assistant. It can read your entire codebase, refactor files, run tests, and execute terminal commands. Normally, running it requires a paid Anthropic API key, but there is a way to run it entirely on free developer credits.

By routing your Claude Code sessions through **AgentRouter** a non-profit AI gateway provider you can access high-tier reasoning models like `claude-opus-4-8` completely free.

Here is a simple, step-by-step setup guide to claim **$150 in free API credits** and integrate it with Claude Code.

---

### Full Disclosure
This guide contains a referral link. By signing up via this link:
* **You (the referee)** will receive **$200** in free API credits.
* **I (the referer)** will receive **$100** in credits. 

You must sign up using a **GitHub account that is at least 3 years old with activities** to claim the promo.

👉 **[Register on AgentRouter and claim your $150 credits here](https://agentrouter.org/register?aff=ug11)**

**No Credit Card Required**

---

### Step 1: Install Claude Code CLI

First, ensure you have Node.js (v18 or higher) installed. Then, open your terminal and run the following command to install the official Claude Code CLI globally:

```bash

```
npm install -g @anthropic-ai/claude-code@latest
```shell
Verify the installation by running:
code

```bash
claude --version
```

### Step 2: Configure the Global Settings File

Instead of dealing with temporary terminal environment variables that get wiped out when you close your window, the cleanest way to configure Claude Code is by utilizing its global settings file. Claude Code automatically monitors this file and reloads your settings live, meaning you can swap API keys and endpoints without ever interrupting your active chat sessions.

#### 1. Open the Claude settings file
Open your terminal or Command Prompt and launch the settings file in your preferred text editor:

* **On Windows (using Notepad):**
  ```cmd
  notepad %USERPROFILE%\.claude\settings.json
  ```
* **On macOS / Linux (using Nano):**
  ```bash
  nano ~/.claude/settings.json
  ```

#### 2. Edit the configuration
Paste the following configuration block into the file. Make sure to replace `your_agent_router_api_key` with the API key you generated on the AgentRouter Token Console:

```json
{
  "autoUpdatesChannel": "latest",
  "theme": "light",
  "model": "opus",
  "env": {
    "ANTHROPIC_BASE_URL": "https://agentrouter.org",
    "ANTHROPIC_AUTH_TOKEN": "your_agent_router_api_key",
    "ANTHROPIC_API_KEY": "",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "claude-opus-4-8",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "claude-opus-4-8",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "claude-opus-4-8",
    "CLAUDE_CODE_SUBAGENT_MODEL": "claude-opus-4-8"
  }
}
```

> **Note:** The model mappings inside the `"env"` object tell Claude Code to route all reasoning, sub-agents, and simple checks directly through AgentRouter's `claude-opus-4-8` model.

Save and close the file.

### Step 3: Launch and Verify

Now, navigate to your active coding project directory inside your terminal and launch Claude:

```bash
claude
```

Once inside the active CLI prompt, check your connection state:

```bash
/status
```

```
/status
```
Verify that:
Anthropic base URL points to https://agentrouter.org
Model is showing opus (claude-opus-4-8)

Press Esc to exit the status menu. You are now fully connected and can begin coding your projects completely free using your $150 credit pool!
Quick Troubleshooting
Model Not Found / Auth Error: If you previously logged into an official Anthropic account, Claude Code might have cached your older session. Type /logout inside the Claude Code chat window, close your terminal, and restart it.
Credits Check: You can monitor your real-time token consumption directly inside the AgentRouter Dashboard. 
First appeared on Dev.to: [How to Run Claude Code Completely Free with $150 AgentRouter Credits](https://dev.to/jadeofwallstreet/how-to-run-claude-code-completely-free-with-150-agentrouter-credits-5cpp)
