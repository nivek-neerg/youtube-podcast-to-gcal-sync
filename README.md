# 🎧 YouTube Podcast to Google Calendar Sync

Automatically schedules new YouTube podcast episodes into your Google Calendar — fitted around your existing events, within the hours and days that work for you.

Built as a POC GitHub project. No coding background. Just a problem I wanted to solve.

---

## The Problem

I follow a handful of podcast creators on YouTube. Every time they post something new, I'd either forget about it, watch it at a bad time, or lose it entirely. I wanted a way to automatically carve out time in my calendar to actually watch them — without clashing with meetings, and only during hours I choose.

## The Solution

A single-page web app that:

- Checks your chosen YouTube channels for new episodes
- Reads your Google Calendar to find real gaps in your schedule
- Books each episode in at the correct length, in the next available slot
- Respects your working hours and chosen days — nothing gets booked outside them
- Skips anything already in your calendar, so it never double-books

---

## How to Use It

### What you'll need
- A Google account
- A free Google Cloud project (takes about 10 minutes to set up)

### Step 1 — Get a YouTube API Key
1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Create a new project
3. Go to **APIs & Services → Library** → search for **YouTube Data API v3** → Enable it
4. Go to **APIs & Services → Credentials** → **+ Create Credentials → API Key**
5. Copy the key

### Step 2 — Set up Google Calendar Access
1. In the same Google Cloud project, go to **APIs & Services → Library**
2. Search for **Google Calendar API** → Enable it
3. Go to **APIs & Services → OAuth consent screen** → External → fill in your app name and email → Save
4. Go to **APIs & Services → Credentials** → **+ Create Credentials → OAuth Client ID**
5. Choose **Web application**
6. Under **Authorised redirect URIs**, add the URL where you're running the app (e.g. `https://yourusername.github.io/youtube-podcast-to-gcal-sync`)
7. Copy the **Client ID** and **Client Secret**

### Step 3 — Open the app and fill in your details
- Paste your YouTube API key, OAuth Client ID, and Client Secret into the app
- Turn on **Remember my settings** — you'll only ever have to do this once
- Add your YouTube channels using the Look up button
- Choose your days and time window
- Hit **Sync to Google Calendar**

---

## Features

- **Channel cards** — each channel shows its profile picture, name, and a toggle to pause/resume it without removing it
- **Remember my settings** — everything is saved to your browser locally, never stored online
- **Smart scheduling** — finds the next real gap in your calendar, not just an empty time slot
- **Correct durations** — each episode is booked for exactly as long as it is
- **No double booking** — checks your calendar before adding anything
- **Your hours, your days** — you choose which days and what time window to book into

---

## Important Notes

**This tool only runs when you open it and click Sync.** Nothing happens automatically in the background. If you don't open it, nothing gets added to your calendar. You are always in control.

**Your API keys never leave your browser.** They are stored locally using your browser's storage and are only ever sent directly to Google's own servers.

---

## Built With

- Vanilla HTML, CSS, and JavaScript — no frameworks, no dependencies
- YouTube Data API v3
- Google Calendar API
- Google OAuth 2.0 (PKCE flow)

---

## Why I Built This

This is my first ever GitHub contribution. I'm not a developer — I used AI to help me build something that solves a real problem I had. The goal was to test the idea via a simple POC. 

If this is useful to you, feel free to use it, fork it, or improve it.
