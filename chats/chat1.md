# Design system core guide

_Started 2026-09-10 22:38 UTC_

---

## User

Create the design guide that includes the UI components, illustration, app design ... est this will be used as the core version for any future need in any ai model

## Assistant

I'll start by exploring the design system and reading the brand book.

_[tool: list_files]_

_[tool: read_file]_

The brand book is thorough. Before building, a few scope calls — note one thing up front: **I can't generate images**, so "illustration" here means a defined SVG/geometric illustration language (drawn from the mark's stroke logic) plus placeholder slots for photography, not rendered artwork.

_[tool: ask_user]_

## Assistant

Building it in chunks so nothing times out. Starting with the shell plus foundations.

_[tool: dc_write]_

_[tool: dc_html_str_replace]_

_[tool: dc_html_str_replace]_

_[tool: dc_html_str_replace]_

## Assistant

_[tool: dc_html_str_replace]_

## Assistant

_[tool: update_todos]_

## Assistant

_[tool: grep]_

_[tool: grep]_

Sections 01–04 are in place. Adding components now.

_[tool: dc_html_str_replace]_

## Assistant

## Assistant

## Assistant

## User

Contuine

## Assistant

_[tool: dc_html_str_replace]_

_[tool: dc_html_str_replace]_

_[tool: dc_html_str_replace]_

Components done. Illustration language next.

_[tool: dc_html_str_replace]_

## Assistant

_[tool: update_todos]_

_[tool: dc_html_str_replace]_

## Assistant

## Assistant

## Assistant

## Assistant

_[tool: run_script]_

## Assistant

_[tool: dc_html_str_replace]_

_[tool: dc_html_str_replace]_

_[tool: update_todos]_

_[tool: dc_html_str_replace]_

Now the mobile and Arabic screens.

_[tool: dc_html_str_replace]_

## Assistant

Large edits keep timing out — switching to smaller chunks.

_[tool: dc_html_str_replace]_

_[tool: dc_html_str_replace]_

## User

Re-running the check

## Assistant

_[tool: dc_html_str_replace]_

## Assistant

_[tool: grep]_

_[tool: grep]_

_[tool: read_file]_

_[tool: read_file]_

_[tool: read_file]_

_[tool: read_file]_

_[tool: run_script]_

_[tool: read_file]_

_[tool: update_todos]_

_[tool: ready_for_verification]_

The guide is complete — twelve sections in one file: how to brief an AI model, colour with measured contrast ratios, type specimens in both scripts, space/shape/elevation, the component library (buttons, forms, pills, cards, alerts, tables, empty/loading/error), the illustration and icon language, charts, three reference app screens including a mirrored Arabic one, RTL rules, accessibility checks, voice examples, and the token block.

Two things to flag:

**Fonts.** The file now calls STC from `fonts/STC-*.ttf`, which isn't in the project — so headings currently fall back to IBM Plex Sans. Either drop the font files in a `fonts/` folder, or I can revert display type to a licensed face. Worth noting the brand book itself argues against adopting STC (another company's commissioned face, missing weights and tabular figures).

**Illustration.** These are geometric SVG diagrams I drew, not generated artwork — I can't produce images. Photography still needs real assets.

## User

الترابي وليس الطرابي

## Assistant

_[tool: grep]_

_[tool: run_script]_

Fixed — الطربي القابضة → الترابي القابضة in all three type specimens.

## User

Add the logo and the logo variants

## Assistant

_[tool: image_metadata]_

_[tool: image_metadata]_

_[tool: image_metadata]_

_[tool: copy_files]_

_[tool: dc_html_str_replace]_

_[tool: run_script]_

_[tool: grep]_

The Voice eyebrow reads 11 (duplicate of Accessibility) — heading is "Voice in the interface".

_[tool: dc_html_str_replace]_

_[tool: ready_for_verification]_

Added §02 The logo — the five approved variants, the negative pair on grey, one-colour on saturated grounds, plus clear space, minimum sizes, placement (including that it never mirrors in Arabic) and misuse rules. Sections renumbered to 13 and the nav rebuilt.

One caveat: the artwork shown is your screenshots of the brand guideline, so it carries that document's own captions and is raster. For production you'll want vector SVG/EPS exports of each variant — drop them in and I'll swap the images for clean specimens.

## User

How can I push this to loveable ?

## Assistant

This is a Design Component file (.dc.html) that renders live in the preview — it's already saved in the project. To push to Loveable (their design-to-code platform):

**Export as standalone HTML:** Call the "Save as standalone HTML" skill, which bundles it into one self-contained offline file. Then upload that to Loveable's importer.

**Or bundle for a partner service:** Use `bundle_project` to create a shareable URL for their import-from-URL tool.

Which path works better for your workflow?

## User

bundle_project

## Assistant

_[tool: bundle_project]_

Adding a thumbnail splash so it can bundle.

_[tool: dc_html_str_replace]_

_[tool: bundle_project]_

_[tool: snip]_

Bundle ready. Copy this URL to Loveable's import tool:

```
https://3e148310-83fb-40fb-8865-a9290b00966f.claudeusercontent.com/v1/design/projects/3e148310-83fb-40fb-8865-a9290b00966f/serve/.bundles/494fa5c3-46ed-46f3-8a79-23c60f92d653.html?t=01ef717203df7e00f2aa574f4a6225ef1501eeadd0a05f4068ecd7e27cdd272f.fc77ae29-a4f4-48cc-9b99-d519f7262013.66e37d14-0b26-4035-9b66-cdff93934be6.1789177299.3.dca86a812d64b0c8&direct=1&raw=1
```

1.4 MB, expires in ~10 minutes. Use it once and immediately — the URL is single-use for security.

## User

Send this design to Lovable: `Altorabi Design Guide.dc.html`

## Assistant

I don't have a direct integration to push files to Lovable. Your options:

1. **Use the bundle URL** (from the previous message) — paste it into Lovable's import-from-URL tool right now (it expires in ~10 minutes).

2. **Export as standalone HTML** — I can bundle it into a self-contained file you download and upload to Lovable manually.

3. **Download the .dc.html directly** — use the file browser to grab `Altorabi Design Guide.dc.html` and upload it to Lovable.

Which works for you?

## User

create a google meet backgroud for a video chate

## Assistant

_[tool: list_files]_

_[tool: list_files]_

_[tool: copy_starter_component]_

_[tool: dc_write]_

_[tool: ready_for_verification]_

I made two 1920×1080 Google Meet backgrounds in `Meet Background.dc.html`: 1a is light and 1b is dark. Both use the brand green and keep the centre clear so your head and shoulders don't cover anything.

- **Logo:** The logo images I have are screenshots that still carry the brand book's captions, so each background has an empty spot top-left. Drop in a clean logo file: the primary logo on 1a, the white (negative) version on 1b.
- **Web address:** I made up "altorabi.com". Send me the real address or tell me to remove it.
- **Mirroring:** In your own preview Meet shows the background mirrored, so the logo will look like it's on the right. Everyone else on the call sees it the right way round.

Once the logos are in, I can save each background as a PNG for you to upload to Meet.

## User

waite backgroud

## Assistant

_[tool: grep]_

_[tool: dc_html_str_replace]_

The light background (1a) is now pure white. Everything else on it, and the dark version (1b), is unchanged.

## User

www.waelaltorabi.me is the link

## Assistant

_[tool: dc_html_str_replace]_

## User



## User

<attached_files>
- uploads/Screenshot 2026-10-04 at 1.26.17 PM.png
</attached_files>

## User

flip it and fix it

## Assistant

_[tool: read_file]_

_[tool: run_script]_

_[tool: ready_for_verification]_

I flipped both backgrounds, so the logo and text read correctly in your own Meet preview. I also made the logo bigger and moved the tagline and web address up under it, away from your shoulders.

One problem: everyone else on the call sees the background the other way round from you, so they'll now see it backwards. If people seeing it correctly matters more, keep the original version and accept that it looks reversed in your own preview. You can also turn off "Mirror my video" in Meet's video settings to see it the way they do.

## User

how

## Assistant

Here's how to put the background into Google Meet:

1. **Get the image.** I can export either background as a 1920×1080 PNG for you. Tell me 1a (white) or 1b (dark).
2. **Upload it in Meet.** Before or during a call, click the three dots (⋮) at the bottom, then **Apply visual effects** → **Backgrounds**.
3. **Add your image.** Click the **+** tile at the start of the backgrounds list and choose the PNG.

**Which way round to use:**
- Your own preview in Meet is mirrored like a selfie, but everyone else sees the background the right way round.
- So the original, unflipped version is the one that reads correctly for everyone else on the call.
- The flipped version only looks right to you, and others will see the text backwards.

I'd go with the unflipped version and ignore how it looks in your own preview. Want me to switch it back and export the PNG?

## User

create my linkedin Profile header as well as public picture with the best sizes use the pics in the folder if the design needs it

## Assistant

_[tool: local_ls]_

_[tool: local_copy_to_project]_

_[tool: local_ls]_

_[tool: run_script]_

_[tool: view_image]_

_[tool: run_script]_

_[tool: view_image]_

_[tool: dc_write]_

_[tool: show_html]_

_[tool: ready_for_verification]_

I made your LinkedIn header and profile photo in `LinkedIn Kit.dc.html`, at the sizes LinkedIn recommends.

- **Header (1584 × 396):** 1a is dark and 1b is white. Both use your panel-speaking photo on the right, with the tagline, a headline and your website on the left. The dashed circle shows where your profile photo covers the header on desktop, and it's left out of the exported image.
- **Profile photo (400 × 400):** 2a is your studio headshot as it is, and 2b adds a brand-green ring. Next to them is a preview of how each looks in LinkedIn's circle.

Things to check:
- **Headline:** I wrote "Building startup ecosystems across the GCC" myself. Send me the line you want if it's different.
- **Headshot quality:** I cut the headshot out of a phone screenshot, so it's only just big enough at 400px. If you have the original file, send it and I'll swap it in.

Tell me which header and photo you want and I'll save them as PNGs for you to upload.

## User

Create a slideshow becuz my account is  Premium. Make a strong first impression with up to 5 images to become the header and confirm the dark therm for the header

## Assistant

_[tool: read_file]_

_[tool: list_files]_

_[tool: run_script]_

_[tool: view_image]_

_[tool: run_script]_

_[tool: ready_for_verification]_

I made a five-slide header slideshow on the dark theme and removed the white version. Each slide is 1584 × 396. The text, the green bar and the dots that show which slide is on stay the same on every slide, so only the photo changes:

1. Keynotes: you on stage in front of a full audience
2. Panels: you speaking on the panel
3. Ecosystem dialogues: a wide shot of the panel on stage
4. Community: you with a guest at the event
5. FII · HERizon Summit: your selfie at the summit

The five captions are my wording, so tell me if you want them changed. The summit selfie is lower quality than the others, so you might want a sharper photo for slide 5. Your profile photo options (2a and 2b) are unchanged.

Once you approve, I can save all five slides as PNGs for you to upload in that order.

## User

1a · Slide 1 of 5
by itself

## Assistant

Do you mean one of these?

1. **Export slide 1 on its own** as a 1584 × 396 PNG, ready to upload.
2. **Keep only slide 1** and remove slides 2–5 (a single header, no slideshow).
3. **Show slide 1 without the text**, so the photo stands alone.

## User

Export slide 1 on its own as a 1584 × 396 PNG, ready to upload.

## Assistant

_[tool: show_to_user]_

_[tool: eval_js_user_view]_

_[tool: snapshot_element]_

Slide 1 is ready to download as a 1584 × 396 PNG. Click Download in the dialog. I hid the dashed profile-photo circle so it isn't in the image.

