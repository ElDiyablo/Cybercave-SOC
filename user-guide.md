# Cybercave SOC — Site User Guide

**For SOC staff and analysts who need to update the site without coding experience.**

---

## How the Site Works

The Cybercave SOC site is hosted on GitHub Pages. Every file you see in the repository is a page on the live site. When you edit a file and commit (save) it, GitHub automatically rebuilds and publishes the change within 60 seconds.

You do not need to know how to code to make most updates. This guide covers everything you'll need.

---

## Accessing the Repository

1. Go to `https://github.com/ElDiyablo/Cybercave-SOC`
2. Log in with your GitHub account
3. Ask the SOC Lead to add you as a collaborator if you don't have write access
4. Once added, you can edit any file directly in the browser

---

## How to Edit an Existing Page

**Example: Updating the threat level on the home page**

1. Go to the repo and click `index.html`
2. Click the **pencil icon** (top right of the file view)
3. Find the text you want to change — use **Ctrl+F** to search within the editor
4. Make your edit
5. Scroll down to **Commit changes**
6. Write a short commit message describing what you changed (e.g. "Update threat level to HIGH")
7. Select **Commit directly to the main branch**
8. Click **Commit changes**

The live site updates within 60 seconds.

---

## Updating the Threat Intelligence Widget

The threat widget is on the **home page** (`index.html`). Update it at the start of each shift.

Find these four lines and update the values:

```html
<!-- PHISHING ATTEMPTS -->
<div class="ti-value" style="color: var(--amber);">Update Each Shift</div>

<!-- BLOCKED THREATS -->
<div class="ti-value" style="color: var(--green);">Update Each Shift</div>

<!-- ACTIVE INVESTIGATIONS -->
<div class="ti-value" style="color: var(--accent);">Update Each Shift</div>

<!-- COMMON LURE THIS WEEK -->
<div class="ti-value" style="color: var(--red); font-size: 0.9rem;">Financial Aid Phish</div>
```

Replace the placeholder text with real numbers from your Kibana shift dashboard.

**Also update the threat level** — find this line:

```html
<div style="font-size: 1.5rem; font-weight: 700; color: var(--amber);">MODERATE</div>
```

Change `MODERATE` to `LOW`, `MODERATE`, `HIGH`, or `CRITICAL` depending on current activity.
Change `var(--amber)` to:
- `var(--green)` for LOW
- `var(--amber)` for MODERATE
- `var(--red)` for HIGH or CRITICAL

---

## Adding a New Blog Post / Advisory

This is the most common update SOC analysts will make.

### Step 1 — Create the post file

1. Go to the `blog/` folder in the repo
2. Click **+ → Create new file**
3. Name it: `blog/post-your-topic.html` (use hyphens, no spaces)
4. Copy the entire contents of an existing post (e.g. `post-soc-intro.html`) as your starting template
5. Edit the following fields:
   - **Title tag** at the top: `<title>Your Title — Cybercave SOC</title>`
   - **Badge type**: change `badge-blue` to `badge-red` (advisory), `badge-amber` (threat report), or `badge-blue` (SOC update)
   - **Date and author**: find `April 2026 &mdash; ElDiyablo` and update it
   - **H1 title**: the big heading at the top of the post
   - **Body content**: replace the paragraphs with your content
6. Commit the file

### Step 2 — Add a card to the blog index

1. Go to `blog/index.html` and click the pencil to edit
2. Find the `<!-- POSTS -->` section
3. Copy one of the existing `<a href="..." class="blog-card">` blocks
4. Paste it above the others (newest post goes first)
5. Update the href, date, badge, title, and summary text
6. Commit

### Badge color guide

| Badge | Color class | Use for |
|-------|-------------|---------|
| 🔴 Advisory | `badge-red` | Active threats, urgent warnings |
| 🟡 Threat Report | `badge-amber` | Completed investigations, threat summaries |
| 🔵 SOC Update | `badge-blue` | Program news, site updates, general info |

---

## Updating the Team Page

To add or update a team member on `about/index.html`:

1. Open `about/index.html` and click the pencil to edit
2. Find the `Meet the Team` section
3. Each team card looks like this:

```html
<div class="team-card">
  <div class="team-avatar">🧑‍💻</div>
  <h3>Name Here</h3>
  <div class="role">Role Title</div>
  <p>Short bio description here.</p>
</div>
```

4. Replace the placeholder emoji, name, role, and bio
5. To add a new card, copy the block above and paste it after the last card
6. Commit

---

## Updating the Google Form Link

The incident ticket form link appears in `ticketing/index.html`.

1. Open `ticketing/index.html` and click the pencil to edit
2. Find this line:

```html
<a href="#" style="...">Open Ticket Form ↗</a>
```

3. Replace `#` with your actual Google Form URL:

```html
<a href="https://forms.google.com/your-form-id" style="...">Open Ticket Form ↗</a>
```

4. Commit

---

## Updating the Incident Report Button

The red "Report Incident Now" button on the home page links to `#` by default.

1. Open `index.html` and click the pencil to edit
2. Find:

```html
<a href="#" class="red-button" style="white-space: nowrap;">🚨 Report Incident Now</a>
```

3. Replace `#` with the university's official incident report form URL
4. Commit

---

## What NOT to Edit

Avoid editing these unless you know what you're doing:

- `style.css` — controls the entire site's appearance; one mistake breaks all pages
- The `<nav>` block at the top of any page — nav links must stay consistent across all pages
- The `<head>` section of any page — font and stylesheet links live here

If you need changes to any of the above, contact the SOC Lead.

---

## Commit Message Guide

Keep commit messages short and descriptive:

| What you did | Good commit message |
|---|---|
| Updated threat level | `Update threat level to HIGH` |
| Added new blog post | `Add advisory: credential stuffing campaign` |
| Fixed broken link | `Fix broken Google Form link in ticketing` |
| Added team member | `Add analyst profile: [name]` |
| Updated phishing lure | `Update threat widget: financial aid lure` |

---

## Getting Help

- **Broken site / something looks wrong:** Contact SOC Lead (ElDiyablo on GitHub)
- **Can't access the repo:** Ask SOC Lead to check your collaborator permissions
- **Need a new page added:** Open a GitHub Issue describing what you need, or contact the SOC Lead directly

---

*This guide is maintained by the SOC Lead. If something is outdated, open a GitHub Issue.*
