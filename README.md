# I don't trust willpower. So I built a system that makes quitting impossible.

I'm Maajith, and I build systems designed to reduce reliance on motivation through friction, accountability, and real-world consequences.
Most productivity tools remind you. CommitT *forces* you.

---

## CommitT

An accountability platform that enforces real consequences for inaction.

---

**Example — You want to actually stick to the gym this time.**

You configure CommitT once:

> **Schedule:** Monday, Wednesday, Friday — 6 AM to 7 AM
> **Location:** Your gym
> **Penalty:** ₹500 deducted or an embarrassing photo automatically sent
> **Waiver:** You chose upfront that escaping costs 400 captchas. No captchas, no waiver.
> **App Block:** Instagram, YouTube, anything you pick — locked the moment your phone detects you've entered the gym
> **Strict Mode:** Your choice at setup. Turn it ON and the task is untouchable — no deletion, no uninstall, no tampering — until the commitment ends

Monday 6 AM hits.

You physically walk into the gym to begin the session.
Instagram disappears. YouTube disappears. Every distraction is gone.

At 6:34 AM, a random verification alarm fires.
You have 60 seconds to prove you're still there.

You try to delete the commitment because you're tired.
The system rejects it.

You leave at 6:45 AM.
₹500 gone before you reach your car.

That's not a reminder app. That's a consequence engine.

---

## How It's Built

CommitT is a fail-closed behavioral enforcement platform. The system assumes failure unless the user provides explicit, timestamped, verifiable proof of presence.

- **Native Android enforcement** — a Kotlin Accessibility Service blocks restricted apps at the OS level, halts uninstall attempts by returning the user to the lock screen, and runs 1Hz GPS verification to prevent location spoofing
- **Triple-Write Saga (Cloud → Disk → Hardware)** — every state change is written atomically across Convex, local SQLite, and Android alarms. If any layer fails, the system heals forward rather than rolling back a confirmed cloud write
- **Offline-first SQLite mirror** — all active commitments are mirrored locally so enforcement continues with zero network dependency
- **Immutable rule snapshots** — the moment a commitment is created, the backend locks the penalty rules. Editing the parent task cannot lower the stakes of an active session
- **Hardware Execution Shield** — detects root access, mock location providers, and developer options at runtime. If triggered, the app halts execution before enforcement can be bypassed
- **Chaos engineering suite** — an in-app fault injection panel with granular failure points across Cloud, Disk, and Hardware layers for resilience testing in production conditions
- **Hardened waiver pipeline** — even the forgiveness system has a hard chronological deadline. Any verification attempt after the session's end time is rejected, even if a waiver is active

[→ Read the full architecture breakdown](https://committ.mintlify.app)

[→ Watch the demo](your-demo-link-here)

---

## Why I Built It

Willpower failed me every time. So I stopped relying on it.

I cobbled together app blockers to force myself to the library and it worked —
not because I got more disciplined, but because I made quitting harder than continuing.
CommitT is that idea, fully built out.

I use it every day. For the gym. For shipping code. It's the reason this project exists.

I've documented every single day of building this — you can check it at [committ.mintlify.app](https://committ.mintlify.app)

---

## Stack

<p align="left">
  <img src="https://skillicons.dev/icons?i=aws,react,nextjs,nodejs,express,mongodb,mysql,redis,ts,js,tailwind,redux,graphql,laravel,kotlin" />
</p>
<p align="left">
  <img src="https://img.shields.io/badge/BullMQ-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Zustand-181717?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Convex-EE342F?style=for-the-badge&logo=convex&logoColor=white" />
  <img src="https://img.shields.io/badge/Expo-000020?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Expo_SQLite-003B57?style=for-the-badge" />
</p>
