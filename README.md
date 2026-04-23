# Health
https://mross8383.github.io/Health/


HOW TO USE:
When a new guide is built, paste a copy of the card block below
into your index.html (inside the <div class="cards">...</div> block).
Place it in the order you want it to appear.

YOU MUST:
1. Add the CSS variables for the new colour in the :root block at
   the top of index.html (both the solid and the glow)
2. Add the 5 CSS rules for the new colour class (.card-NAME, icon-NAME,
   text-NAME, tag-NAME, arrow-NAME) — see existing ones as reference
3. Paste the card block in the right position within the cards div
4. Update href, guest name, title, description, tags, icon emoji, stroke colour

COLOUR CLASS NAMES ALREADY USED:
rhonda, gut, bikman, bikman2, jamnadas, mills, goldhamer, brecka,
wimhof, tatem, ferriss

For new guides, pick a short class name (usually the guest's surname).

============================================================
STEP 1 — ADD COLOUR VARIABLES TO :root (at top of <style>)
============================================================

--NEWCOLOUR: #HEX;
--NEWCOLOUR-light: #HEX;
--NEWCOLOUR-glow: rgba(R,G,B,0.1);

============================================================
STEP 2 — ADD THESE CSS RULES TO THE STYLE BLOCK
Replace NAME with the class name, and HEX values with your colour.
============================================================

.card-NAME { border-color: rgba(R,G,B,.25); background: #HEX_dark; }
.card-NAME:hover { border-color: var(--NEWCOLOUR-light); box-shadow: 0 5px 20px rgba(R,G,B,.15); }
.card-NAME::before { background: var(--NEWCOLOUR-glow); }

.icon-NEWCOLOUR { background: var(--NEWCOLOUR-glow); border: 1px solid rgba(R,G,B,.3); }

.text-NEWCOLOUR { color: var(--NEWCOLOUR-light); }

.tag-NEWCOLOUR {
  background: rgba(R,G,B,.12);
  color: var(--NEWCOLOUR-light);
  border: 1px solid rgba(R,G,B,.25);
}

.arrow-NEWCOLOUR { background: rgba(R,G,B,.12); }

============================================================
STEP 3 — PASTE THIS CARD BLOCK INSIDE <div class="cards">
============================================================
-->

<a class="card card-NAME" href="FILENAME.html">
  <div class="card-inner">
    <div class="card-icon icon-NEWCOLOUR">{{ICON_EMOJI}}</div>
    <div class="card-text">
      <div class="card-guest text-NEWCOLOUR">{{GUEST NAME — optional podcast/episode label}}</div>
      <div class="card-title">{{GUIDE TITLE}}</div>
      <div class="card-desc">{{ONE-SENTENCE DESCRIPTION — list 5–8 topics covered, comma-separated}}</div>
      <div class="card-tags">
        <span class="card-tag tag-NEWCOLOUR">{{TAG 1}}</span>
        <span class="card-tag tag-NEWCOLOUR">{{TAG 2}}</span>
        <span class="card-tag tag-NEWCOLOUR">{{TAG 3}}</span>
        <span class="card-tag tag-NEWCOLOUR">{{TAG 4}}</span>
      </div>
    </div>
    <div class="card-arrow arrow-NEWCOLOUR">
      <svg viewBox="0 0 24 24" fill="none" stroke="#HEX_LIGHT" stroke-width="2.5">
        <path d="M5 12h14M12 5l7 7-7 7"/>
      </svg>
    </div>
  </div>
</a>

<!--
============================================================
WORKED EXAMPLE — Tim Ferriss guide (orange)
============================================================

In :root:
  --orange: #c4541c;
  --orange-light: #e07a3c;
  --orange-glow: rgba(196,84,28,0.1);

CSS rules:
  .card-ferriss { border-color: rgba(196,84,28,.25); background: #1a1108; }
  .card-ferriss:hover { border-color: var(--orange-light); box-shadow: 0 5px 20px rgba(196,84,28,.15); }
  .card-ferriss::before { background: var(--orange-glow); }
  .icon-orange { background: var(--orange-glow); border: 1px solid rgba(196,84,28,.3); }
  .text-orange { color: var(--orange-light); }
  .tag-orange { background: rgba(196,84,28,.12); color: var(--orange-light); border: 1px solid rgba(196,84,28,.25); }
  .arrow-orange { background: rgba(196,84,28,.12); }

Card block:
  <a class="card card-ferriss" href="ferriss-mindset.html">
    <div class="card-inner">
      <div class="card-icon icon-orange">🎯</div>
      <div class="card-text">
        <div class="card-guest text-orange">Tim Ferriss · On Purpose</div>
        <div class="card-title">Mindset, Fuel & Focus Reference</div>
        <div class="card-desc">Cognitive fuel and the Norwegian 4x4, bioelectric medicine, achievement vs. acceptance, hunting antelope, the 17 questions, non-violent communication, the self-help trap and cosmic insignificance therapy.</div>
        <div class="card-tags">
          <span class="card-tag tag-orange">Acceptance</span>
          <span class="card-tag tag-orange">Focus</span>
          <span class="card-tag tag-orange">Bioelectric</span>
          <span class="card-tag tag-orange">Key Questions</span>
        </div>
      </div>
      <div class="card-arrow arrow-orange">
        <svg viewBox="0 0 24 24" fill="none" stroke="#e07a3c" stroke-width="2.5">
          <path d="M5 12h14M12 5l7 7-7 7"/>
        </svg>
      </div>
    </div>
  </a>
============================================================
-->
