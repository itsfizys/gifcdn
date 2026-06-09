# Contributing

Thanks for wanting to contribute. This repo is a curated set of high-quality anime GIFs meant for roleplay bots and apps — things like Discord bots where users do `/hug @someone` and a GIF fires back. Every GIF here should feel intentional, clean, and actually good.

---

## What belongs here

This collection is specifically for **roleplay-style actions and reactions** — things people express toward each other in a bot context. A GIF belongs here if you can picture it being the response to a bot command.

Good fits: `hug`, `pat`, `slap`, `kiss`, `poke`, `wave`, `cry`, `blush`, `laugh`

Bad fits: random memes, reaction images with text overlaid, clips from a specific show that are out of context, anything that would confuse someone who doesn't know the source

If you are unsure whether something fits, open a category request issue before adding it.

---

## Quality standards

This repo prioritizes quality over quantity. Before adding any GIF:

- Must be `.gif` format — no MP4, WEBP, APNG, or anything else
- Minimum resolution of **480px** on the shortest side — blurry or pixelated GIFs will be rejected
- File size should be **under 8MB** where possible. Large files load slower for end users
- **No watermarks** of any kind — no TikTok logos, no Tenor/Giphy branding, nothing burned into the frame
- **No subtitles or text overlaid** on the GIF
- No black bars, no letterboxing
- The GIF should loop cleanly — a hard cut at the end is acceptable, a flash or jump is not
- Anime art style only — this is not a general GIF collection

---

## File structure

Every GIF lives in a category folder and is named with a plain sequential number:

```
hug/
  1.gif
  2.gif
  3.gif
pat/
  1.gif
  2.gif
```

No prefixes. No zero-padding. No underscores. Just the number and `.gif`.

---

## Adding GIFs to an existing category

1. Fork the repo and clone your fork
2. Check [index.json](./index.json) for the current count of that category
3. Name your files continuing from that count
   - If `hug` has 17 GIFs, your first new file is `hug/18.gif`
4. Update `index.json`:
   - Increment the category count
   - Increment `total_gifs`
5. Open a pull request — describe what you added and where you sourced the GIFs from

---

## Adding a new category

1. Fork the repo and clone your fork
2. Create a new folder with a clear, lowercase, single-word (or joined-word) name — e.g. `handhold`, `evillaugh`, not `hand-hold` or `evil_laugh`
3. Add at least **5 GIFs** to the folder, named `1.gif`, `2.gif`, and so on
4. Update `index.json`:
   - Add the new category and its count to the `categories` object (keep it alphabetical)
   - Increment `total_categories` and `total_gifs`
5. Add a row for the new category to the table in `README.md` in alphabetical order, using this format:

```md
| `categoryname` | N | `.../categoryname/{1..N}.gif` | ![categoryname](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/categoryname/1.gif) |
```

6. Open a pull request — explain the category and why it's a good addition

New categories with fewer than 5 GIFs or with GIFs that don't meet the quality bar will not be merged.

---

## Removing or replacing a GIF

If a GIF is broken, wrong, or low quality, open a **Broken or incorrect GIF** issue rather than directly removing it. This keeps the index counts accurate and gives context for the change.

If you want to submit a replacement, you can include it in the same PR as the removal — just renumber any GIFs after the removed one to keep the sequence clean, and update `index.json` accordingly.

---

## Keeping index.json accurate

`index.json` is what bots and apps use to know how many GIFs exist per category. If it's wrong, users will get 404s or miss GIFs entirely.

Every PR that adds, removes, or moves GIFs must update `index.json`. PRs with an outdated index will not be merged.

The structure is straightforward:

```json
{
  "base_url": "https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main",
  "total_categories": 61,
  "total_gifs": 682,
  "categories": {
    "hug": 17,
    "pat": 18
  }
}
```

---

## Pull request checklist

- [ ] All GIFs are `.gif` format, minimum 480px, under 8MB, no watermarks or text
- [ ] Files are named `{n}.gif` — sequential, no prefix, no zero-padding
- [ ] `index.json` counts are correct
- [ ] `README.md` is updated if a new category was added (alphabetical order, with preview)
- [ ] No unrelated files are in the PR
