# Geek releases

<!--
  DRAFT for the public nigelose10/geek-releases repo (its README.md). Not published.
  Written 2026-10-16 for the free public beta; it must stay true of the build on the
  latest release. Publish it together with the first beta release, and only after the
  multi-school sign-in (any Moodle address, plus the calendar-link option) has landed,
  because the text below describes that build. Source of the facts: geek-os.site
  (apps/site), docs/runbooks/release.md (install steps and the release notes template).
  The issue form for this repo is docs/runbooks/geek-releases-issue-form.yml, to be
  committed there as .github/ISSUE_TEMPLATE/bug-report.yml. Delete this comment when publishing.
-->

Installers for **Geek**, a free desktop app for university students. Connect your school's Moodle and Geek opens on your courses and what's due, with a bot for each course. Not on Moodle? Paste your calendar link and your due dates show up on Home.

**Free public beta, for Mac and Windows.** No Geek account, no payment, nothing locked. More at [geek-os.site](https://geek-os.site).

## Download

These links always give the newest beta:

| Your computer | File |
|---|---|
| Mac with Apple silicon (M1 or later), macOS 13 or later | [Geek-mac-arm64.dmg](https://github.com/nigelose10/geek-releases/releases/latest/download/Geek-mac-arm64.dmg) |
| Mac with an Intel processor, macOS 13 or later | [Geek-mac-x64.dmg](https://github.com/nigelose10/geek-releases/releases/latest/download/Geek-mac-x64.dmg) |
| Windows 11, 64-bit (x64) | [Geek-win-x64.exe](https://github.com/nigelose10/geek-releases/releases/latest/download/Geek-win-x64.exe) |

Which Mac? Apple menu > About This Mac: a "Chip" line means Apple silicon; a "Processor" line that says Intel means Intel.
Windows 10, Windows on Arm and Linux are not supported.

Each release lists the SHA-256 of every file in its notes and in `SHA256SUMS.txt`. Installers are published only here and on geek-os.site/download, never sent as chat or email attachments.

## What you need

- **Your school.** Any school whose Moodle allows the official Moodle app: enter your Moodle address in Geek and sign in on your school's own page, inside Geek's window. Geek never sees your password; the sign-in token is stored encrypted on your laptop and used only to read. What shows up depends on which mobile-app functions your school's Moodle has turned on. On Canvas, Brightspace, Blackboard or anything else, or if your school turned off Moodle app access, paste your calendar (iCal) link instead: your due dates show up on Home.
- **An AI, if you want chat.** Bring your own key (free models on OpenRouter or Gemini work) or local Ollama: a key from [OpenRouter](https://openrouter.ai/keys) or [Google AI Studio](https://aistudio.google.com/apikey), or [Ollama](https://ollama.com/download) on your laptop. You pay that provider directly, or nothing. Home works with no AI at all.

## What's in the beta

- **Home:** your courses and what's due, from Moodle or from a calendar link, synced to your laptop.
- **Bots:** a bot for each course you pick, plus your own (for example an essay coach), with memory you can see, edit and undo.
- **The Computer:** Geek's own browser, already signed in to your Moodle. On your Moodle a bot reads pages and takes screenshots by itself. Before it clicks, scrolls, chooses an option or types on a page, and before it opens a site outside your Moodle, it shows a card: Allow once, Always allow for that kind of action, or Deny. Typing never gets Always allow. Take over at any time.
- **Off limits, always:** quiz attempt pages and password fields, even if you approve a click. Geek can't submit, post, send or delete anything on your school site on its own: its Moodle connection only reads, and in the Computer it acts only through clicks and typing you allowed.
- **AI-use log:** every chat turn and Computer step, per assignment, ready to export for the acknowledgement your course asks for.
- **Your data stays on your laptop.** No Geek account, no analytics, no crash reports. What a bot needs to answer you goes to the AI provider you picked (with Ollama it stays on your laptop).

## Install (unsigned builds)

These builds are not signed by Apple or Microsoft yet, so your computer asks you to confirm once for each new version. Full steps: [geek-os.site/download](https://geek-os.site/download).

**Mac, macOS 15 or later**

1. Open the `.dmg`, drag Geek into Applications, eject the disk image, and open Geek from Applications.
2. macOS says it can't verify Geek. Click Done (don't move it to the Trash).
3. Open System Settings > Privacy & Security, scroll to Security, and click Open Anyway next to the note about Geek. It shows for about an hour after you try to open the app.
4. Enter your Mac login password. Geek opens, and opens normally from then on, until the next version.

**Mac, macOS 13 or 14:** in Finder > Applications, Control-click Geek, choose Open, then click Open.

**If macOS says Geek is damaged:** download the `.dmg` again in your browser, then copy Geek from the disk image into Applications and open it from there. Last resort, only if it still says damaged, in Terminal:

```bash
xattr -dr com.apple.quarantine /Applications/Geek.app
```

That removes the "downloaded from the internet" mark from Geek only. It changes nothing for your other apps. Never turn off Gatekeeper for your whole Mac.

**Keychain question on a Mac:** after you install a new version, macOS may ask whether Geek can use "Geek Safe Storage" in your keychain. That item holds the key Geek encrypts your saved school sign-in and AI keys with. Enter your login password and choose Always Allow to stay signed in. If you choose Deny, Geek can't read what it saved, and you have to sign in to your school and add your AI key again.

**Windows 11**

1. Run `Geek-win-x64.exe`. If your browser warns that the file isn't commonly downloaded, choose to keep it.
2. When "Windows protected your PC" appears, click More info, then Run anyway.
3. Geek installs for your Windows account, with no admin prompt, and opens. It's in the Start menu and on your desktop.

If Windows says Smart App Control blocked Geek, there is no Run anyway: Geek can't be installed on that PC while Smart App Control is on. Signed builds are planned; please don't turn your PC's protection down for Geek.

## Updating

Geek doesn't update itself yet. Download the new version from the links above and install it over the old one (on a Mac, drag it to Applications and choose Replace). Your courses, bots, chats and keys stay on your laptop. Expect the first-open steps, and on a Mac the Keychain question, again.

To hear about new versions: click **Watch** at the top of this page, then **Custom**, tick **Releases** and apply.

## Known limits in this beta

- **Not signed yet.** The first open of each version needs the steps above.
- **No automatic updates.** Download each new version here.
- **No overlay or Integrity Lock yet.** The glass overlay for asking about your screen, and the lock that pauses Geek during assessments, come in a later release.
- **No remote pause switch yet.** Geek can't yet be paused from afar if a school asks or something breaks. A fix comes as a new download.
- **The AI is the one you choose.** How good, fast and private chat is depends on the key or local model you pick. AI answers can be wrong; check them against your course materials.
- **No Geek account,** so nothing syncs between computers.
- While a bot is using the Computer, Geek stops page requests you didn't approve, so parts of a page may show an error until you take over.

## Report a bug

[Open a bug report](https://github.com/nigelose10/geek-releases/issues/new/choose). The form asks for:

- your computer (macOS version or Windows 11) and, on a Mac, Apple silicon or Intel;
- the Geek version: Settings > General > About shows a line like "Geek 0.1.0-beta.1, beta channel, on darwin arm64"; paste it;
- what you did, what you expected, and what happened instead.

**Issues are public. Never include:**

- an AI key (OpenRouter keys start with `sk-or-`, Gemini keys with `AIza`);
- a Moodle token, or any web address with `token=` or `wstoken` in it;
- a password, or a Duo or two-step code;
- your calendar link (anyone with it can read your calendar);
- a screenshot that shows any of these. Crop it, or describe what you saw instead.

If you posted one by mistake: edit or delete the comment or issue, then revoke the key with its provider (OpenRouter or Google AI Studio), sign out of the mobile apps from your school's Moodle (your Moodle has its own page for that), and check whether your school's calendar page can give you a new calendar link.

## Geek Pro Max (not built yet)

The free beta is free for everyone, and nothing in it is locked behind paying. Geek Pro Max is the planned paid tier: the same app and interface, plus a more powerful work agent for long multi-step jobs, background and scheduled bots, and later a Geek CLI. None of it is built yet and there is no ship date. The $49 founding price buys Pro Max when it ships, plus onboarding help by hand now: [geek-os.site/pro-max](https://geek-os.site/pro-max).

---

Geek is independent and not affiliated with or endorsed by Moodle, Duo, Crowdmark, Canvas, Brightspace, Blackboard, OpenRouter, Google, Ollama or any school.
