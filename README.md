# Health Reference Library

Personal knowledge base of HTML reference guides built from podcast transcripts.

Live at: https://mross8383.github.io/Health/

---

## How to add a new guide to the index

When Claude builds a new guide, follow these 4 steps to add it to the index page.

You'll be editing **`index.html`** — that's the only file you need to change. The new guide HTML file (e.g. `newguest-topic.html`) just needs to be uploaded to the repo separately; it doesn't need to be edited.

---

### Step 1 — Pick a colour name

Pick a short one-word name for your new colour. Use the guest's surname or the colour itself.

Examples already used:
`rhonda`, `gut`, `bikman`, `bikman2`, `jamnadas`, `mills`, `goldhamer`, `brecka`, `wimhof`, `tatem`, `ferriss`

For these instructions, we'll use **`NEWNAME`** as the placeholder. Replace it everywhere with your actual name.

You'll also need:
- The **hex colour** of your guide (e.g. `#c4541c` for orange) — Claude will tell you this
- The **RGB values** of that hex (e.g. `196,84,28`) — convert at https://www.google.com/search?q=hex+to+rgb
- A **lighter version** of the hex for hover effects (e.g. `#e07a3c`) — Claude will tell you this
- A **dark background hex** (e.g. `#1a1108`) — Claude will tell you this

---

### Step 2 — Add 3 lines to the top of `index.html`

Open `index.html` and scroll to the top. Find the block that starts with `:root {` near the top of the `<style>` section.

You'll see lines like this:
```
--orange: #c4541c;
--orange-light: #e07a3c;
--orange-glow: rgba(196,84,28,0.1);
```

**Add 3 new lines just like these, but with your colour:**
```
--NEWNAME: #YOUR_HEX;
--NEWNAME-light: #YOUR_LIGHTER_HEX;
--NEWNAME-glow: rgba(YOUR_RGB,0.1);
```

Place them with the other colour variables. Order doesn't matter.

---

### Step 3 — Add 7 CSS rules further down

Stay in `index.html`, scroll down past the `:root` block. Find the section where you see card colour rules grouped together. They look like this (the Ferriss/orange example):

```
.card-ferriss { border-color: rgba(196,84,28,.25); background: #1a1108; }
.card-ferriss:hover { border-color: var(--orange-light); box-shadow: 0 5px 20px rgba(196,84,28,.15); }
.card-ferriss::before { background: var(--orange-glow); }
.icon-orange { background: var(--orange-glow); border: 1px solid rgba(196,84,28,.3); }
.text-orange { color: var(--orange-light); }
.tag-orange { background: rgba(196,84,28,.12); color: var(--orange-light); border: 1px solid rgba(196,84,28,.25); }
.arrow-orange { background: rgba(196,84,28,.12); }
```

**Copy this entire 7-line block, paste it just below the existing ones, and find-and-replace inside your new block:**

| Find | Replace with |
|---|---|
| `ferriss` | your `NEWNAME` |
| `orange` | your `NEWNAME` |
| `196,84,28` | your RGB values |
| `#1a1108` | your dark background hex |

Don't touch the existing Ferriss block — just edit your new copy.

---

### Step 4 — Add the card to the visible list

Stay in `index.html`. Scroll further down to find `<div class="cards">`.

Inside it, you'll see a list of `<a class="card card-...">` blocks — one per existing guide.

**Copy any existing card block (entirety: `<a>` to `</a>`) and paste it where you want your new guide to appear in the list.**

Then in your pasted copy, change these things:

| Find | Replace with |
|---|---|
| `card-ferriss` (or whichever you copied) | `card-NEWNAME` |
| `ferriss-mindset.html` | your filename, e.g. `newguest-topic.html` |
| `icon-orange` | `icon-NEWNAME` |
| `text-orange` | `text-NEWNAME` |
| `tag-orange` | `tag-NEWNAME` (×4 — there are 4 tags) |
| `arrow-orange` | `arrow-NEWNAME` |
| `stroke="#e07a3c"` | `stroke="#YOUR_LIGHTER_HEX"` |
| The emoji icon | A new emoji that fits the topic |
| The guest name | Your guest's name |
| The title text | Your guide's title |
| The description | One sentence covering 5-8 topics in the guide |
| The 4 tag labels | 4 short tags from the guide |

---

### Step 5 — Save and commit

Save `index.html`. Upload it to GitHub along with the new guide HTML file. GitHub Pages will rebuild within a minute or two.

Visit https://mross8383.github.io/Health/ to confirm the new card appears and links correctly.

---

## Worked example

If your new guide is for **Dr. Jane Smith** on **sleep science**, with a deep blue colour theme:

**Step 1:** Choose `smith` as your name. Hex: `#1a3a6e`. RGB: `26,58,110`. Lighter: `#5a7ab8`. Dark bg: `#0a121e`.

**Step 2:** Add to `:root`:
```
--smith: #1a3a6e;
--smith-light: #5a7ab8;
--smith-glow: rgba(26,58,110,0.1);
```

**Step 3:** Add the 7 CSS rules:
```
.card-smith { border-color: rgba(26,58,110,.25); background: #0a121e; }
.card-smith:hover { border-color: var(--smith-light); box-shadow: 0 5px 20px rgba(26,58,110,.15); }
.card-smith::before { background: var(--smith-glow); }
.icon-smith { background: var(--smith-glow); border: 1px solid rgba(26,58,110,.3); }
.text-smith { color: var(--smith-light); }
.tag-smith { background: rgba(26,58,110,.12); color: var(--smith-light); border: 1px solid rgba(26,58,110,.25); }
.arrow-smith { background: rgba(26,58,110,.12); }
```

**Step 4:** Inside the cards div, add:
```
<a class="card card-smith" href="smith-sleep.html">
  <div class="card-inner">
    <div class="card-icon icon-smith">😴</div>
    <div class="card-text">
      <div class="card-guest text-smith">Dr. Jane Smith</div>
      <div class="card-title">Sleep Science Reference</div>
      <div class="card-desc">Sleep architecture, circadian rhythm, melatonin, sleep apnea, deep vs REM sleep, the 90-minute cycle, and protocols for shift workers.</div>
      <div class="card-tags">
        <span class="card-tag tag-smith">Circadian</span>
        <span class="card-tag tag-smith">Melatonin</span>
        <span class="card-tag tag-smith">Sleep Apnea</span>
        <span class="card-tag tag-smith">Protocols</span>
      </div>
    </div>
    <div class="card-arrow arrow-smith">
      <svg viewBox="0 0 24 24" fill="none" stroke="#5a7ab8" stroke-width="2.5">
        <path d="M5 12h14M12 5l7 7-7 7"/>
      </svg>
    </div>
  </div>
</a>
```

Save, upload, done.

---

## Troubleshooting

**Colour not showing up?**
You probably missed one find-and-replace in Step 3 or Step 4. Search the file for the original colour name (e.g. `orange`) inside your new block — anything you missed will still be there.

**Card looks unstyled?**
Check that all 7 CSS rules from Step 3 are present and spelled the same as the class names in your card block. The class name has to match exactly.

**Guide page won't open from card?**
The `href` value in your card must exactly match the filename of your guide HTML file (case-sensitive). Check both.

**Rebuild not showing?**
GitHub Pages takes 1-2 minutes after upload. Hard-refresh your browser (Ctrl/Cmd+Shift+R).
