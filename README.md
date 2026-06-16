# Whole

**Your medical life, in one place, on your own machine.**

Every doctor you've ever seen keeps a piece of you. The lab company has your bloodwork. The hospital has your discharge notes. The specialist has the scan. The pharmacy has the list. You have twelve logins and no overview.

Whole pulls all of it into one private record that lives on *your* computer. No company in the middle. No subscription. No one reading it but you.

This is the layperson version — Tier 1. You don't need to write code, and you don't need a fancy machine. If you can install an app and copy-paste one line, you can do this in an afternoon.

> If you have a GPU box (I built mine on a Dell GB10), there's a Tier 2 that adds a private AI you can ask questions of. That lives in [`AI.md`](AI.md). Start here first.

---

## What you get

- One **timeline** of your whole medical history instead of twelve portals.
- Lab results that **line up over time** — your ferritin, your heart rate, your thyroid — across years and across different labs, on one chart.
- Conditions, medications, allergies, immunizations, and visit notes, all in one searchable place.
- A complete copy **you own** — to hand to a new specialist, or to take to the ER.

## What this is not

Whole organizes your records. It does not diagnose, interpret, or replace your doctor. It makes you a better-prepared patient, not your own physician. (The AI layer in Tier 2 doesn't change that — read its disclaimer too.)

---

## What you need

- A computer that stays on — Mac, Windows, or Linux. Anything.
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed. This is a normal app with a download button. Install it, open it once, leave it running.
- Your patient-portal logins (MyChart, your lab company, your hospital, your specialists).

No GPU. No coding. No cloud account. No monthly fee.

---

## Do it in five steps

### 1. Install Docker Desktop
Download it from [docker.com](https://www.docker.com/products/docker-desktop/), install it, and open it once so it's running in the background.

### 2. Start the app — two lines
Open **Terminal** (Mac) or **PowerShell** (Windows) and paste this:

```bash
git clone https://github.com/spoonie-me/whole.git && cd whole
docker compose up -d
```

That's the whole install. The engine underneath is [Fasten OnPrem](https://github.com/fastenhealth/fasten-onprem) — free, open-source, and self-hosted.

Your records land in a `db/` folder inside the project: **that folder is where your records live.** It never goes anywhere else. Back it up like you'd back up photos.

### 3. Open it in your browser
Go to **http://localhost:9090** and create an account. "Account" here just means a password that protects the app on your own machine. There's no server, no signup, no one on the other end.

### 4. Connect your providers
Click **Add Source**, search for your provider ("Kaiser", "Quest Diagnostics", "Mount Sinai", etc.), and it sends you to *that provider's own login page*. You log in to them; they hand your records back to the app. Repeat for each one — primary care, labs, hospital, every specialist.

### 5. Add the paper stuff
For older records, faxes, or a clinic that won't connect, drag the PDFs straight in so they live next to everything else.

Done. Everything is now in one place, on your machine.

---

## Honest limits

- US coverage is very good but not universal. Smaller clinics may not connect — that's what step 5 is for.
- It pulls what the portal *exposes*, which is sometimes less than the full chart.
- Tier 1 has **no AI**. It organizes; it doesn't interpret. That's the next file.

---

## Why I built this

I spent years being a stack of files no one had ever read in one sitting — including me. The fragmentation isn't a side effect of being chronically ill. It *is* part of the illness's weight: the logins, the re-explaining, the records that never sit in the same room.

The same data is already aggregated about you — by hospitals, by insurers — optimized for their goals. This just puts the whole picture where it belongs: with you, on a folder on your own machine, with no one in the middle.

Take it. Fork it. Make it yours.

---

## License

MIT. It's yours.
