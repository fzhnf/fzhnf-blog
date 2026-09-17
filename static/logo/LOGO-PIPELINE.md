# Tima Gutmensch — VTuber Logo Pipeline (Inkscape + Mochiy Pop One)

A fully hand-held guide to make a **bubbly sticker** style VTuber logo.
Follow it top to bottom. Nothing is assumed — every click and menu path is written out.

**What we're making:** bubble-shaped letters with two colors, a thick white "sticker" outline,
sparkles and stars around the name, and one small character accent. Final files live in
this folder and are served by your blog at `/logo/logo.svg`.

---

## Step 0 — Set up the canvas and save the file

1. Open **Inkscape**.
2. In the *Welcome* dialog, click **New document: default** (or press `Ctrl+N` on an empty window).
3. Press **`Ctrl+Shift+D`** (File → Document Properties…).
4. In the dialog:
   - Set **Display units** to `px`.
   - Under **Custom page size**, set **Width: `800`**, **Height: `400`**.
   - Close the dialog.
5. Press **`Ctrl+Shift+S`** (File → Save As…).
6. Navigate to this folder (`fzhnf-blog/static/logo/`), set the filename to `logo.svg`, click **Save**.
   - If asked about the file format, keep **Inkscape SVG** (or plain **SVG** — either works).
   - This replaces the empty placeholder `logo.svg` that was created here — that's intended.
7. Zoom to fit: press **`3`** (View → Zoom → Fit Page in Window). If the empty page grid bothers you,
   press **`#`** (View → Page Grid) to toggle it off.

✅ Check: the window title says `logo.svg — Inkscape`, and the white page is wide (800×400).

## Step 1 — Verify the font is installed

1. Open a terminal and run:

   ```bash
   fc-list | grep -i mochiy
   ```

2. You should see a line mentioning `Mochiy Pop One`.
3. If nothing appears: close Inkscape, install the font (copy the `.ttf`/`.otf` into
   `~/.local/share/fonts/`, then run `fc-cache -f -v`), then reopen Inkscape.

✅ Check: `fc-list` prints at least one Mochiy Pop One line.

## Step 2 — Type the name

1. Press **`T`** to select the Text tool (toolbar icon: letter **A**).
2. Click once in the middle of the page and type exactly:

   ```
   Tima Gutmensch
   ```

3. Select all of it: press **`Ctrl+A`** (this selects the text you just typed while the text
   tool is active).
4. In the **Tool Controls bar** (the bar at the top, visible when the Text tool is active):
   - **Font family**: type or choose `Mochiy Pop One`.
   - **Font size**: set to `120` (type it in the px size box).
   - Leave alignment centered (the middle-align icon).
5. Press **`S`** to switch back to the Selector tool (arrow).
6. Click the text once to select it. Drag it so it sits roughly in the middle of the page
   (fine centering comes later in Step 8).
7. If the text overflows the page width: select it, and in the tool controls bar lower the font
   size to `100` and re-center.

✅ Check: big bubbly `Tima Gutmensch` in Mochiy Pop One sits on the page.

## Step 3 — Convert text to vector (do not skip)

Converting makes the logo independent of the font — it opens identically on any machine and
you can edit letter shapes like drawings.

1. Click the text with the Selector tool (`S`) so it's selected.
2. **Path → Object to Path…** (`Ctrl+Shift+C`).
3. In the status bar (bottom left) the object type now reads "Path" instead of "Text".

⚠️ After this, you can't retype the name — it's now shapes. If you need to change the text,
press `Ctrl+Z` until you're back to text, fix it, and convert again.

✅ Check: status bar shows a path, not a text object.

## Step 4 — The color wave across the letters

Instead of per-letter colors, the classic VTuber look is **one continuous gradient flowing
across the whole name** — the color "wave" that connects every letter.

Palette — **Rosé Pine, Main variant** (one variant only — the logo is schemed, not color-picked).
Roles follow the scheme's hierarchy: base/surface/overlay for structure, text for foreground,
muted/subtle for quiet elements, accents sparing. Copy hexes into the color picker's hex field:

**Accents (the wave + rare pops):**
- Rose (wave start): `#EBBCBA`
- Love (wave middle): `#EB6F92`
- Iris (wave end): `#C4A7E7`
- Gold (tiny glint + one or two sparkles — accents are rare in this scheme): `#F6C177`

**Cool counterweight (the scheme's mist):**
- Foam (dots + overlap patch): `#9CCFD8`
- Pine (star motif — the one deep-cool element): `#31748F`

**Neutrals (structure, by depth):**
- Overlay (outer sticker edge): `#26233A`
- Surface (optional letter backing / dark backdrop): `#1F1D2E`
- Text (sticker halo — the foreground white): `#E0DEF4`
- Subtle (quiet sparkles): `#908CAA`
- Muted (quietest decorations): `#6E6A86`
- Base (canvas / dark-theme ground): `#191724`

A second variant pair lives in **Step 9b** — same drawing, Dawn hexes, served automatically
on light theme. Never mix variants in one file.

Don't use the whole set at once: a schemed logo touches ~6 roles (wave accents, Foam, Pine,
Text, Overlay), not all 15.

1. Select all letters: with the Selector tool (`S`), drag a rubber-band box around the name.
2. **Path → Union…** (`Ctrl++` — hold Ctrl and press the `+`/equals key). All letters merge into
   one shape. Don't worry — they look identical, and this is what makes the color flow
   continuously instead of restarting on each letter.
3. Press **`Ctrl+Shift+F`** (Object → Fill and Stroke…). On the **Fill** tab, click the
   **Linear gradient** button (the bar-shaped icon). The name turns into a default
   white→black gradient.
4. Press **`G`** to select the **Gradient tool**. Click the name once — you'll see two
   handles connected by a line: a **square** (start) and a **round** (end) handle.
5. Drag the square handle to the **lower-left of the first letter (T)** and the round handle
   to the **upper-right of the last letter (h)**. This sets the wave's direction — diagonal
   is the usual look. (You can re-drag these handles any time to adjust the angle.)
6. Set the colors, stop by stop:
   - With the Gradient tool, click the **square handle** → in Fill & Stroke's color area,
     paste `EBBCBA` (Rose — light blush starts the wave) into the RGBA hex box, Enter.
   - Click the **round handle** → paste `C4A7E7` (Iris — dusky violet ends it), Enter.
   - Warm middle: **double-click on the line between the two handles** — a third stop
     appears in the middle. Click it, set its color to `EB6F92` (Love).
   - Optional gold glint: double-click the line again between Love and Iris, set that stop
     to `F6C177` (Gold), and drag it close to the Iris end — a small warm flash, not a
     full gold zone. Rosé Pine uses gold sparingly.
7. Click the **Stroke paint** tab, click the **X** (No paint) button — letters get their outline
   from the sticker layer next, not a stroke.
8. Click empty canvas to deselect, then look at the result. Re-drag the gradient handles (`G`)
   until the wave feels right.

💡 Want to tweak a stop color later? `G` (Gradient tool) → click the name → click a stop
handle → change color in Fill & Stroke.

✅ Check: color flows smoothly across all letters as one wave — no per-letter restarts,
no stroke on them yet.

## Step 4b — Optional: real color wave (fake mesh) + overlap effect

A linear gradient is a straight ramp — for 2D flowing color, use blurred blobs behind the
letters instead of a mesh gradient (**mesh doesn't render in browsers**, and the logo lives
on the web; blur does render everywhere).

1. Press `E` (Ellipse tool), draw 3–5 big ellipses over the name area, one color each
   (`#EBBCBA`, `#EB6F92`, `#C4A7E7`, `#9CCFD8` — the Foam one is what keeps the wash from
   going all-warm). Let them overlap freely.
2. Select the ellipses → `Ctrl+Shift+F` → drag the **Blur** slider (bottom of dialog) up
   until the edges fully melt into soft color wash (no visible ellipse edges).
3. Select all blobs → `Ctrl+G` (group). Then Shift+click the letter shapes too and do
   **Object → Clip → Set Clip Path** — the wash now only shows inside the letters.
   (Tip: duplicate the letters and **Path → Union** the duplicate first, so you have a
   single silhouette to clip against — and keep the separate translucent letters for later.)
4. Press `Page Down` until the blob group sits **below** the translucent letters layer.
5. Your low-opacity letters stay on top, unchanged — overlaps still stack darker.
6. Rearranging letters? Just move the ellipses too — the wave follows, no redo needed.

✅ Check: color flows and curves across the name in 2D, contained inside the letter
shapes, and letter overlaps still show their denser combined color.

## Step 5 — The thick sticker outline (two layers)

1. Select the text (`S` tool, single click), press **`Ctrl+D`** (Edit → Duplicate). A duplicate
   sits exactly on top.
2. Press **`Page Down`** (Object → Lower) twice so the duplicate drops **below** the colored text.
3. With the duplicate still selected, in Fill & Stroke (`Ctrl+Shift+F`):
   - **Fill** tab: set fill to `E0DEF4` (Text).
   - **Stroke paint** tab: Flat color.
   - **Stroke style** tab: **Width: `14` px**. Set stroke color (Fill & Stroke → **Stroke paint** →
     flat color) to `26233A` for now — the next step bakes it in.
4. With that duplicate still selected: **Path → Stroke to Path…** (`Ctrl+Alt+C`).
   This turns the stroke into a real shape so outline thickness never changes when scaling.
5. The outline shape may now cover the colored text — it's below it, so it should only peek out
   around the edges. If it covers everything, press `Page Down` until the letters show.
6. **Double outline (the classic sticker look):** select the outline shape, `Ctrl+D`, then press
   `Page Down` twice so the new copy sits below the soft-white one. Give it fill `26233A`
   (Overlay — purple-black, not pure black; Rosé Pine's darks always lean violet) and
   **no stroke**. From top to bottom you should now see: colored letters → Text (soft-white)
   outline → Overlay (purple-black) outline → page.
7. No further unioning needed — per-letter outlines already read correctly.

✅ Check: letters have a thick soft-white halo and a darker edge behind it.

## Step 6 — Sparkles and stars

1. Press **`*`** (the star/asterisk key) to select the **Star tool**.
2. In the Tool Controls bar:
   - Click the **star** icon (left of the two shape icons).
   - **Corners: `4`**, **Spoke ratio: `0.22`**, **Rounding: `0.6`** — this makes a 4-point
     sparkle with soft curves. (If your toolbar shows "Rounded" and "Randomized" numeric
     fields, put `0.6` into Rounded.)
3. On the canvas, **click and drag** to draw a sparkle. While dragging, hold **`Ctrl`** to keep
   it upright.
4. Make 4–5 sparkles of different sizes. After each, use `S` (selector) to move it — drag with
   the mouse, or use arrow keys to nudge.
5. Color them: one or two in `#F6C177` (Gold — accent, sparing), the rest in `#908CAA`
   (Subtle) and `#6E6A86` (Muted) — quiet tier sparkles, they should whisper, not shout.
6. Also press **`E`** (Ellipse tool) and drag out 3–4 tiny circles (hold `Ctrl` while dragging for
   perfect circles) — dot them near the sparkles in `#9CCFD8` (Foam — the cool mist).
7. Place everything *around* the name: sparkles near the top-left of `T` and bottom-right of `h`,
   dots scattered between. Avoid covering letters.
8. Select all decorations (`Ctrl+A` is too much — drag a rubber-band selection around them with
   the Selector, or Shift+click each one), then **Object → Group** (`Ctrl+G`).

✅ Check: 4–5 sparkles + small dots decorate the space around the name, grouped.

## Step 7 — One character motif

One simple accent tucked behind a letter keeps it personal without clutter.

1. With the Star tool (`*`), draw one **5-point star** (Corners: `5`, Spoke ratio: `0.382`,
   Rounding: `0.1`), sized about 60 px.
2. Fill it `#31748F` (Pine — the one deep-cool accent, it should read as deliberate), no
   stroke.
3. Position it peeking from behind the last letter of "Gutmensch": select it, press
   **`Page Down`** (Object → Lower) until it slides just behind the text outlines
   (it should end up below the letter stack in z-order).
4. Optionally duplicate it (`Ctrl+D`) and place a second smaller one at the top-left.

✅ Check: a star (or two) peeks out from behind the name.

## Step 7b — Optional: combined-color overlap

If a decoration overlaps a letter and you want the overlapping patch to have its own
"combined" color (keep the letter AND the star whole, only the overlap recolored):

1. **Shift+click both** shapes — the letter and the overlapping decoration.
2. Press **`Ctrl+D`** once — duplicates of both are made exactly on top of themselves, and
   the duplicates are now the selection.
3. **Path → Intersection…** (`Ctrl+*`). The two duplicates merge into the overlap shape;
   the two originals underneath are untouched.
4. `Ctrl+Shift+F` → Fill → give the patch a combined color (e.g. `#9CCFD8`, Foam — the
   cool patch against warm letters reads instantly).
5. Press `Page Up` until the patch is visible above the originals.

⚠️ Intersection without the duplicate (Step 2) deletes both originals and leaves only the
sliver — that's the mistake to avoid. The patch is a frozen snapshot: if you later move the
letter or star, redo steps 1–5 for the new position.

✅ Check: letter and star are both whole, and the overlap area shows its own color.

## Step 8 — Group and center everything

1. Drag a rubber-band box around **everything** on the page (Selector tool, click empty space,
   drag over all).
2. **Object → Group** (`Ctrl+G`) — one logo object now.
3. Press **`Ctrl+Shift+A`** (Object → Align and Distribute…).
4. In the dialog, set **Relative to: Page**, then click:
   - **Center on vertical axis**
   - **Center on horizontal axis**
5. Close the dialog. Press `Ctrl+S` to save.

✅ Check: the logo sits dead-center on the page, saved (`Ctrl+S` shows no modified-star in title).

## Step 9 — Export

**SVG (keep this — it's the master file):**
1. `Ctrl+S` saves `static/logo/logo.svg`. Your blog serves it at `https://blog.fzhnf.my.id/logo/logo.svg`.

**PNG (for avatars/thumbnails where SVG isn't accepted):**
1. **File → Export…** (`Ctrl+Shift+E`).
2. In the Export dialog:
   - Export area: **Page** (dropdown).
   - Filename: click the filename box → navigate to this folder → `logo.png`.
   - At the bottom, set **Width: `1600`** (height auto-follows at 2×).
   - Click **Export**, then **Close**.

✅ Check: `logo.png` appears in this folder and looks right in an image viewer.

## Step 9b — The Dawn twin (theme-aware serving)

The site has dark *and* light themes, so the logo gets two variant skins of one drawing.
Same roles → swap hexes mechanically (that's the scheme doing the work):

| Role | Main (dark) | Dawn (light) |
|---|---|---|
| wave start (Rose) | `#EBBCBA` | `#D7827E` |
| wave middle (Love) | `#EB6F92` | `#B4637A` |
| wave end (Iris) | `#C4A7E7` | `#907AA9` |
| glint (Gold) | `#F6C177` | `#EA9D34` |
| dots + patch (Foam) | `#9CCFD8` | `#56949F` |
| star motif (Pine) | `#31748F` | `#286983` |
| sticker halo (Text) | `#E0DEF4` | `#FFFAF3` (Surface) |
| outer edge (Overlay) | `#26233A` | `#464261` (Text — on light, the edge is the dark role) |

Wait — note the two last rows: on light backgrounds the hierarchy flips. The halo becomes
Surface (cream) and the edge becomes Dawn's Text. Accents map 1:1, neutrals flip roles.

1. Select the whole logo group → `Ctrl+D` (duplicate).
2. Drag the duplicate to the side, then work through **every fill** with the mapping above
   (click each piece, `Ctrl+Shift+F`, paste the Dawn hex).
3. Name the files `logo-dark.svg` (Main) and `logo-light.svg` (Dawn).
4. Serve both in Zola — in a template/shortcode, use the `<picture>` swap:

   ```html
   <picture>
     <source srcset="/logo/logo-light.svg" media="(prefers-color-scheme: light)">
     <img src="/logo/logo-dark.svg" alt="Tima Gutmensch" class="site-logo">
   </picture>
   ```

   (If your blog toggles theme with a class instead of the OS setting, swap the media
   query for the class your theme uses.)

✅ Check: open `logo-dark.svg` on a dark background and `logo-light.svg` on a light one —
both read cleanly, neither is the other recolored badly.

## Step 10 — Use it in Zola

- Anywhere in a post/page:

  ```markdown
  ![Tima Gutmensch logo](/logo/logo.svg)
  ```

- As a site icon: convert the PNG (1600×800) to a square crop, then check your Zola theme's docs
  for the exact config key (themes differ; the SVG/PNG under `static/` is already server-ready
  either way).

---

## Done checklist

- [ ] Canvas 800×400, file saved as `logo.svg`
- [ ] Text converted to paths (status bar says "Path")
- [ ] One gradient wave flowing across the letters, soft-white outline, dark edge behind
- [ ] 4–5 sparkles + dots, grouped
- [ ] Star motif behind a letter
- [ ] Whole logo grouped and centered
- [ ] `logo.svg` + `logo.png` in `static/logo/`

## Common mistakes

| Symptom | Cause | Fix |
|---|---|---|
| Logo loses its font on another computer | Text wasn't converted | Redo Step 3 (`Ctrl+Shift+C`) |
| Outline eats the letters | Outline copy is above text | Select it, `Page Down` until letters show |
| Outline gets thin when scaling | Stroke wasn't converted to path | Step 4: `Ctrl+Alt+C` on the outline |
| Sparkle is jagged/sharp | Rounding left at 0 | Star tool → set Rounding ~0.6 |
| Everything moves together oddly | Items not grouped before centering | `Ctrl+A` → `Ctrl+G`, then align again |
| Gradient restarts on every letter | Letters weren't unioned before gradient | `Ctrl+Z`, redo Step 2 (Path → Union) |
| Intersection deleted both shapes | The op is destructive — you intersected the originals | `Ctrl+Z`, then redo with the Step 7b duplicate-first method |
| Inkscape says the svg is invalid when reopening | You double-clicked the 0-byte placeholder before Step 0 | Just follow Step 0 — Save As overwrites it |
