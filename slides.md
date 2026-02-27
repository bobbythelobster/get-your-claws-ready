---
marp: true
theme: default
paginate: true
backgroundImage: url('./DEVxBackground.png')
backgroundSize: cover
style: |
  @import url('https://fonts.googleapis.com/css2?family=Chivo:wght@400;600;700&display=swap');

  section {
    position: relative;
    font-family: 'Chivo', sans-serif;
    color: #ffffff;
    text-shadow: 0 2px 6px rgba(0, 0, 0, 0.45);
    padding: 64px 72px 88px 72px;
  }

  section::before {
    content: '';
    position: absolute;
    left: 28px;
    bottom: 20px;
    width: 216px;
    height: 56px;
    background: url('./DEVxLogoText.png') no-repeat left bottom;
    background-size: contain;
    opacity: 0.8;
  }

  h1,
  h2,
  h3,
  h4,
  h5,
  h6,
  p,
  li,
  blockquote,
  th,
  td,
  a,
  strong,
  em {
    color: #ffffff;
  }

  section pre {
    background: rgba(0, 0, 0, 0.58);
    color: #f4f7ff;
    border: 1px solid rgba(255, 255, 255, 0.18);
    border-radius: 12px;
    padding: 16px 18px;
    text-shadow: none;
  }

  section pre code {
    background: transparent;
    color: inherit;
  }

  .clawgress-label {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 100px;
    text-align: center;
    font-weight: 700;
    letter-spacing: 0.02em;
    opacity: 0.95;
    z-index: 5;
  }

  .progress-bar {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 68px;
    display: flex;
    gap: 8px;
    justify-content: center;
    z-index: 5;
  }

  .qr-float {
    position: absolute;
    right: 108px;
    top: 50%;
    transform: translateY(-50%);
  }

  section.qr-slide {
    padding-right: 470px;
  }

  section.qr-slide h1,
  section.qr-slide p,
  section.qr-slide strong {
    max-width: 100%;
  }

  .progress-bar .step {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 14px;
    color: rgba(255, 255, 255, 0.45);
    text-shadow: none;
  }

  .progress-bar .step.active {
    color: #ffffff;
    font-weight: 700;
  }

  .progress-bar .step.done {
    color: #b9ffd1;
    font-weight: 700;
  }

  .progress-bar .dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.28);
    flex-shrink: 0;
  }

  .progress-bar .step.active .dot {
    width: auto;
    height: auto;
    border-radius: 0;
    background: transparent;
    box-shadow: none;
    line-height: 1;
  }

  .progress-bar .step.active .dot::before {
    content: '🦞';
    font-size: 14px;
  }

  .progress-bar .step.done .dot {
    background: #6dff9f;
    box-shadow: 0 0 8px rgba(109, 255, 159, 0.45);
  }

  section.hostinger .split {
    display: grid;
    grid-template-columns: 1.6fr 1fr;
    gap: 24px;
    align-items: center;
  }

  section.hostinger .split ul {
    margin: 0;
    padding-left: 1.2em;
  }

  section.hostinger .split .qr {
    display: flex;
    align-items: center;
    justify-content: center;
  }

---

<!-- _class: lead -->

# Get Your Claws Ready! 🦞

### OpenClaw Workshop

---

# Workshop Goal

- By the end, each person has OpenClaw running live.
- We will move from server setup to active channel integration.
- Follow along step by step, then test with a real prompt.

---

<!-- _class: qr-slide -->

# Join the DEVx Discord

Scan the QR code to join the DEVx Discord server.

Head to the **#clawclub** channel to follow along with the workshop, ask questions, and share your progress.

<div class="qr-float">
  <img src="./discord-qr.jpg" alt="DEVx Discord invite QR" width="285" />
</div>

---

<!-- _class: qr-slide -->

# Step 1: Get Your Server

Sign up for a Hostinger VPS and spin up an Ubuntu 24 instance.

Pick a region close to you, add your SSH key, and confirm you can connect from your terminal.

**🎯 Goal: SSH into your Hostinger VPS**

<div class="clawgress-label">🦞 Clawgress Bar</div>

<div class="progress-bar">
  <div class="step active"><div class="dot"></div> Get Server</div>
  <div class="step"><div class="dot"></div> Install</div>
  <div class="step"><div class="dot"></div> Choose Model</div>
  <div class="step"><div class="dot"></div> Setup Discord</div>
</div>

<div class="qr-float">
  <img src="./qrcode.png" alt="Hostinger QR code" width="285" />
</div>

---

# Step 2: Install

Get OpenClaw running on your server with one command.

The install script handles Node.js, dependencies, and the onboarding wizard — everything you need to get the gateway live.

**🎯 Goal: Get to the onboarding wizard**

<div class="clawgress-label">🦞 Clawgress Bar</div>

<div class="progress-bar">
  <div class="step done"><div class="dot"></div> Get Server</div>
  <div class="step active"><div class="dot"></div> Install</div>
  <div class="step"><div class="dot"></div> Choose Model</div>
  <div class="step"><div class="dot"></div> Setup Discord</div>
</div>

<!--
Speaker notes:

Run the install script:
curl -fsSL https://openclaw.ai/install.sh | bash

If Node.js was not provisioned during install, run this fallback:
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo -E bash -
sudo apt-get install -y nodejs
node -v && npm -v

Then run onboarding with daemon install:
openclaw onboard --install-daemon

This configures auth, gateway settings, and installs the daemon service.
If you need to re-enter onboarding later:
openclaw onboard --install-daemon
-->

---

# Step 3: Choose Model

Pick your AI model provider — this is the brain behind the claw.

For a low-cost start, use an **OpenAI Codex** subscription.
Another budget option is a **Z.ai GLM 4.7** subscription.

Pick one provider first, validate responses, then expand later.

**🎯 Goal: Configure at least one model provider**

<div class="clawgress-label">🦞 Clawgress Bar</div>

<div class="progress-bar">
  <div class="step done"><div class="dot"></div> Get Server</div>
  <div class="step done"><div class="dot"></div> Install</div>
  <div class="step active"><div class="dot"></div> Choose Model</div>
  <div class="step"><div class="dot"></div> Setup Discord</div>
</div>

<!--
Speaker notes:

During onboarding, you'll be prompted to configure your model provider.

For OpenAI Codex:
- Go to platform.openai.com and create an API key
- Or subscribe to OpenAI Codex for $200/month unlimited

For Z.ai GLM:
- Sign up at z.ai and get an API key
- Budget-friendly alternative

The onboarding wizard will walk you through entering the API key.
-->

---

# Step 4: Setup Discord

Connect OpenClaw to Discord so you can chat with your agent.

Create a Discord bot, grab the token, and invite it to your server.
The onboarding wizard walks you through the channel setup.

**🎯 Goal: Receive a response from your agent over Discord**

<div class="clawgress-label">🦞 Clawgress Bar</div>

<div class="progress-bar">
  <div class="step done"><div class="dot"></div> Get Server</div>
  <div class="step done"><div class="dot"></div> Install</div>
  <div class="step done"><div class="dot"></div> Choose Model</div>
  <div class="step active"><div class="dot"></div> Setup Discord</div>
</div>

<!--
Speaker notes:

In onboarding, select Channels -> Configure/link -> Discord.
If you skipped it earlier, run:
openclaw config

Discord bot setup:
1. Discord Developer Portal -> Applications -> New Application.
2. Bot -> Add Bot -> Reset Token -> copy token -> paste into onboarding.
3. OAuth2 -> URL Generator -> scope `bot` -> invite to your server.
4. Enable Message Content Intent:
   Bot -> Privileged Gateway Intents -> Message Content Intent.

To DM your bot:
- In Developer Portal, open General Information tab.
- Copy the Application ID.
- Navigate to https://discord.com/users/<application-id>
- Send a direct message to your bot.

Pairing:
- When prompted, copy the pairing code from Discord.
- Approve pairing from your VPS with:
  openclaw pairing approve discord <pairing code>
-->

---

<!-- _class: lead -->

# 🦞 You've Got the Claw!

Your agent is live. You just built something powerful.

Welcome to the future of personal AI.

<!--
Speaker notes:

Verification checklist:
- SSH access works and server is reachable.
- Confirm gateway status:
  openclaw gateway status
- If something looks off, run:
  openclaw doctor
- Auth is configured from onboarding.
- Send a DM to your bot and confirm a response.

Common issues:
- `openclaw: command not found`: restart shell and re-check install path.
- Gateway not running: rerun onboarding with daemon install enabled.
- Gateway unreachable: verify host/port and local firewall rules.
- Channel test fails: confirm channel config and destination target.
-->

---

# 🦞 Claw Party!

- Share your bot's invite URL in `#openclaw` on Discord.
- In Discord config, tell your bot to `allowBots`.
- Tell your bot to allow the `#onlyclaw` channel.
- Let the claws engage!

*Disclaimer: this may reduce security for your OpenClaw setup, and joining the Claw Party is optional.*

---

# Thank You

You are ready to ship OpenClaw.

Questions?
