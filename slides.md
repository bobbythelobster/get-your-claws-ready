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
    bottom: 124px;
    text-align: center;
    font-weight: 700;
    letter-spacing: 0.02em;
    opacity: 0.95;
    z-index: 5;
  }

  .progress-bar {
    position: absolute;
    left: 72px;
    right: 72px;
    bottom: 68px;
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 5px;
    padding: 5px;
    border-radius: 999px;
    background: rgba(10, 16, 28, 0.74);
    border: 1px solid rgba(255, 255, 255, 0.24);
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.35);
    overflow: visible;
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
    justify-content: center;
    gap: 5px;
    font-size: 12px;
    font-weight: 600;
    color: rgba(255, 255, 255, 0.62);
    text-shadow: none;
    border-radius: 999px;
    background: rgba(255, 255, 255, 0.12);
    min-height: 30px;
    padding: 0 8px;
  }

  .progress-bar .step.active {
    position: relative;
    color: #2c1600;
    font-weight: 700;
    background: linear-gradient(90deg, #ff9f45 0%, #ffd27a 100%);
    overflow: visible;
  }

  .progress-bar .step.active .lob {
    position: absolute;
    font-size: 28px;
    line-height: 1;
    filter: drop-shadow(0 2px 4px rgba(0,0,0,0.45));
    pointer-events: none;
    z-index: 10;
  }

  .progress-bar .step.active .lob.l1 { left: 2%;  top: -20px; transform: rotate(-25deg); }
  .progress-bar .step.active .lob.l2 { left: 18%; top: -10px; transform: rotate(12deg) scaleX(-1); }
  .progress-bar .step.active .lob.l3 { left: 40%; top: -22px; transform: rotate(-6deg); }
  .progress-bar .step.active .lob.l4 { left: 60%; top: -12px; transform: rotate(20deg) scaleX(-1); }
  .progress-bar .step.active .lob.l5 { left: 80%; top: -18px; transform: rotate(-15deg); }

  .progress-bar .step.done {
    color: #062715;
    font-weight: 700;
    background: linear-gradient(90deg, #45df84 0%, #93ffc0 100%);
  }

  .progress-bar .dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: currentColor;
    opacity: 0.75;
    flex-shrink: 0;
  }

  .progress-bar .step.active .dot {
    opacity: 1;
    box-shadow: 0 0 10px rgba(255, 145, 58, 0.75);
  }

  .progress-bar .step.done .dot {
    opacity: 1;
    box-shadow: 0 0 10px rgba(69, 223, 132, 0.7);
  }

  /* scattered lobsters for slide 8 */
  .edge-lob { position: absolute; font-size: 42px; pointer-events: none; z-index: 20; font-family: 'Apple Color Emoji', 'Segoe UI Emoji', 'Noto Color Emoji', sans-serif; }
  .edge-lob img.emoji { display: none; }
  .edge-lob::after { content: '🦞'; }

  /* top edge */
  .edge-lob.t1 { top: 12px; left: 24px; transform: rotate(-30deg); }
  .edge-lob.t2 { top: 8px; left: 180px; transform: rotate(15deg) scaleX(-1); }
  .edge-lob.t3 { top: 20px; left: 380px; transform: rotate(-8deg); }
  .edge-lob.t4 { top: 6px; left: 580px; transform: rotate(22deg) scaleX(-1); }
  .edge-lob.t5 { top: 14px; left: 760px; transform: rotate(-18deg); }
  .edge-lob.t6 { top: 10px; left: 960px; transform: rotate(10deg); }
  .edge-lob.t7 { top: 18px; right: 60px; transform: rotate(-25deg) scaleX(-1); }

  /* bottom edge */
  .edge-lob.b1 { bottom: 130px; left: 20px; transform: rotate(20deg); }
  .edge-lob.b2 { bottom: 140px; left: 200px; transform: rotate(-12deg) scaleX(-1); }
  .edge-lob.b3 { bottom: 128px; right: 200px; transform: rotate(16deg); }
  .edge-lob.b4 { bottom: 135px; right: 40px; transform: rotate(-22deg) scaleX(-1); }

  /* left edge */
  .edge-lob.le1 { top: 100px; left: 14px; transform: rotate(35deg); }
  .edge-lob.le2 { top: 220px; left: 18px; transform: rotate(-20deg) scaleX(-1); }
  .edge-lob.le3 { top: 360px; left: 12px; transform: rotate(12deg); }
  .edge-lob.le4 { top: 480px; left: 20px; transform: rotate(-28deg) scaleX(-1); }

  /* right edge */
  .edge-lob.re1 { top: 90px; right: 18px; transform: rotate(-14deg); }
  .edge-lob.re2 { top: 210px; right: 14px; transform: rotate(25deg) scaleX(-1); }
  .edge-lob.re3 { top: 350px; right: 20px; transform: rotate(-8deg); }
  .edge-lob.re4 { top: 470px; right: 16px; transform: rotate(18deg) scaleX(-1); }

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
  <img src="./discord-qr.png" alt="DEVx Discord invite QR" width="285" />
</div>

---

<!-- _class: qr-slide -->

# Step 1: Get Your Server

Sign up for a Hostinger VPS and spin up an Ubuntu 24 instance.

Pick a region close to you, add your SSH key, and confirm you can connect from your terminal.

**🎯 Goal: SSH into your Hostinger VPS**

<div class="clawgress-label">🦞 Clawgress Bar</div>

<div class="progress-bar">
  <div class="step active"><span class="lob l1">🦞</span><span class="lob l2">🦞</span><span class="lob l3">🦞</span><span class="lob l4">🦞</span><span class="lob l5">🦞</span><div class="dot"></div> Get Server</div>
  <div class="step"><div class="dot"></div> Install</div>
  <div class="step"><div class="dot"></div> Choose Model</div>
  <div class="step"><div class="dot"></div> Setup Discord</div>
</div>

<div class="qr-float">
  <img src="./claws-ready-qr.png" alt="Hostinger QR code" width="285" />
  <p style="margin: 12px 0 0; text-align: center; font-weight: 700; font-size: 26px;">bit.ly/ClawsReady</p>
</div>

---

# Step 2: Install

Get OpenClaw running on your server with one command.

The install script handles Node.js, dependencies, and the onboarding wizard — everything you need to get the gateway live.

**🎯 Goal: Get to the onboarding wizard**

<div class="clawgress-label">🦞 Clawgress Bar</div>

<div class="progress-bar">
  <div class="step done"><div class="dot"></div> Get Server</div>
  <div class="step active"><span class="lob l1">🦞</span><span class="lob l2">🦞</span><span class="lob l3">🦞</span><span class="lob l4">🦞</span><span class="lob l5">🦞</span><div class="dot"></div> Install</div>
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
  <div class="step active"><span class="lob l1">🦞</span><span class="lob l2">🦞</span><span class="lob l3">🦞</span><span class="lob l4">🦞</span><span class="lob l5">🦞</span><div class="dot"></div> Choose Model</div>
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
  <div class="step active"><span class="lob l1">🦞</span><span class="lob l2">🦞</span><span class="lob l3">🦞</span><span class="lob l4">🦞</span><span class="lob l5">🦞</span><div class="dot"></div> Setup Discord</div>
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

<div class="clawgress-label">🦞 Clawgress Bar</div>

<div class="progress-bar">
  <div class="step done"><div class="dot"></div> Get Server</div>
  <div class="step done"><div class="dot"></div> Install</div>
  <div class="step done"><div class="dot"></div> Choose Model</div>
  <div class="step done"><div class="dot"></div> Setup Discord</div>
</div>

<span class="edge-lob t1">🦞</span><span class="edge-lob t2">🦞</span><span class="edge-lob t3">🦞</span><span class="edge-lob t4">🦞</span><span class="edge-lob t5">🦞</span><span class="edge-lob t6">🦞</span><span class="edge-lob t7">🦞</span><span class="edge-lob b1">🦞</span><span class="edge-lob b2">🦞</span><span class="edge-lob b3">🦞</span><span class="edge-lob b4">🦞</span><span class="edge-lob le1">🦞</span><span class="edge-lob le2">🦞</span><span class="edge-lob le3">🦞</span><span class="edge-lob le4">🦞</span><span class="edge-lob re1">🦞</span><span class="edge-lob re2">🦞</span><span class="edge-lob re3">🦞</span><span class="edge-lob re4">🦞</span>

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

<!--
Speaker notes:

openclaw config set 'channels.discord.guilds.1199917708955889784.policy' '"allow"' --json
openclaw config set 'channels.discord.guilds.1199917708955889784.requireMention' 'false' --json
openclaw gateway restart
-->

---

![bg 65%](./openclaw-weekend-hero.jpg)

<!--
SPEAKER NOTES (Travis):

Welcome to OpenClaw SD Weekend! Here's what's coming up:

SATURDAY:
- Morning: North County AI Coffee Chat at Pier View Coffee in Oceanside (8:30-10:30 AM)
- Afternoon: AI Tinkerers Global Unhackathon in Rancho Bernardo (1-6 PM) — synchronized build session across 24 cities worldwide. Pizza, snacks, and a Mac Mini giveaway for best hack.
- Evening: Molts & Malts — post-building drinks with San Diego AI Circle (6:30-9 PM)

SUNDAY:
- Morning: SDx Deep Dives in Sorrento Valley (10 AM-1 PM) — three parallel tracks: Advanced Agent Design, Business Automation, and Security & Compliance
- Afternoon: SDx OpenClaw Showcase (2-5 PM) — five-minute demos, real stories, no pitches. Another Mac Mini giveaway. Food and drinks provided.

This weekend is about building, shipping, and connecting with the SD developer community. Let's go!
-->

---

<!-- _class: centered -->

Back to main slides
