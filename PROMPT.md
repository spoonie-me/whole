# Using Claude with Whole

Once your records are in Whole, you can use Claude to help you make sense of them. Copy the prompt below into any Claude conversation, fill in the bracketed parts, and go.

---

## The prompt

```
I'm using Whole (https://github.com/spoonie-me/whole) to manage my personal health records. All my records are stored locally — nothing goes to any server.

Here's my situation:
[Describe your health context in a sentence or two. E.g. "I have POTS and fibromyalgia. I see a cardiologist, a rheumatologist, and a GP."]

I'm going to paste some of my records or notes below. Help me with this:
[Say what you need. Examples below.]

---
[Paste your records, lab results, or notes here]
```

---

## What to ask for

**Before an appointment:**
> "I have a cardiology appointment in two days. Based on these records, what has changed since my last visit, and what are the three most important questions I should ask?"

**Making sense of a lab result:**
> "My ferritin came back at 11. My previous results are pasted below. What does the trend look like, and what should I mention to my doctor?"

**Before an ER visit or urgent care:**
> "I need to give a doctor a quick summary of my history. Write me a one-page summary of my conditions, medications, and allergies from these records."

**When you've just been diagnosed:**
> "I was just told I have [condition]. Based on my existing records, what questions should I be asking, and what should I track going forward?"

**When you're exhausted and don't know where to start:**
> "I haven't looked at my records in a while and I have an appointment next week. I have limited energy. Help me figure out the most important thing to do in the next 20 minutes."

---

## What Claude won't do (and shouldn't)

Claude will not diagnose you. It will not tell you to change your medications. It will not replace your doctor.

What it will do: help you find patterns, prepare questions, translate medical language, and walk into your next appointment already knowing your own story.

That's the floor you deserve. Everything else is between you and your doctor.

---

## If you have a GPU box (the AI layer)

If you followed [AI.md](AI.md) and have the full local AI layer running, you can use Open WebUI at http://localhost:8080 with `medgemma:27b` — a model purpose-built for medical text — and ask these same questions directly over your records without pasting anything. Everything stays on your machine.
