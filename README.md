# Midnight Rose — A Royal Love Story 🌹🖤

A handcrafted, static, multipage love-letter website. No backend, no
database — just HTML, CSS, and vanilla JavaScript, so you can host it
anywhere (or just open `index.html` locally / drag the folder into
Netlify, GitHub Pages, Vercel, etc.).

## How to view it

Open `index.html` in a browser, or serve the folder with any static
server (recommended, since some browsers restrict local file access):

```bash
cd midnight-rose
python3 -m http.server 8000
# then visit http://localhost:8000
```

## The experience

```
index.html (Our Little World, home hub) → Love Letter / Notes /
Gallery / Memories / Digital Gifts / Video
```

The old memory-date lock sequence (`lock1.html` → `lock2.html` →
`lock3.html` → `happybirthday.html` → `welcome.html` →
`letter-intro.html`) has been removed. `index.html` now opens straight
into the hub — the same content as `home.html` — so there's no
password gate to click through anymore.

### Digital Gifts (coupon book)

`digital-gifts.html` is a flip-card coupon book. Click a card to flip
it and read the back. One coupon, **Yes Day**, is special: flipping it
reveals a "Choose My Yes Day" button that opens a calendar + time
picker. She picks any date and time, presses Confirm, and gets a
ready-to-copy message to send back letting you know when it is.

While she's on this page, the site navigation (top nav, hamburger,
mobile menu) is disabled until she's chosen her Yes Day — she'll see a
small note about it under the page title. Once she confirms a date,
the nav unlocks for the rest of the session.

Edit the coupons (add, remove, or rewrite the flavor-text ones) in
`js/digital-gifts.js` — look for the `coupons` array at the top.

### The finale

`the-last-lock.html` is the closing surprise — a single, self-contained
page (no separate steps or extra pages to click through). She opens on
a black screen ("There's one more thing"), taps into a quiet starfield
with four gold memory stars, taps each one to reveal a moment, then
watches them pull together and write out one final line in your own
handwriting-style script before the whole screen ignites and a still
frame appears with a button to hear your recorded voice.

Personalize it by editing the `memories` array, `finalLine`,
`finalDate`, and `finalNames` near the bottom of the `<script>` in
`the-last-lock.html`, and add your own `song.mp3` (background music,
already used elsewhere) and `voice.mp3` (your ~20–30 second recorded
message) next to the other files — both are marked with `✏️ EDIT ME`.

This page isn't linked from the site's nav on purpose, so it doesn't
spoil itself. Decide how she reaches it — a hidden trigger once she's
seen everything else, a final button at the end of the video page, or
just a private link you send her directly — and wire that in whenever
you're ready.

### Video page

`video.html` embeds a single video with playback controls. Add your
own file at `video/for-you.mp4` (create the `/video` folder) and
update the `<source src="...">` in the page — search for
`✏️ EDIT ME`. Background music automatically pauses while the video
plays.

## Where to personalize everything

| What | File | What to edit |
|---|---|---|
| Love letter text | `love-letter.html` | the `data-full-text` attribute on `#letter-text` (paragraphs separated by `%%`) |
| Little notes | `js/notes.js` | the `notes` array at the top |
| Gallery photos | `js/gallery.js` | the `photos` array — replace captions, or point `src` at your own images |
| Photos themselves | `images/photo1.jpg` … `images/photo50.jpg` | swap these placeholder files for real photos, **keeping the same file names** (or update the paths in `js/gallery.js`) |
| Reasons I love you | `js/memories.js` | the `reasons` array |
| Timeline | `js/memories.js` | the `timeline` array |
| Special memories | `js/memories.js` | the `specialMemories` array |
| Background music | any page's `<audio id="bg-music">` tag | set `src="your-song.mp3"` (add the file to the project first) |
| Easter egg message | `index.html` / `home.html` | the `.easter-egg-overlay` text |
| Happy Birthday message | `happybirthday.html` | the `<h1 class="birthday-title">` text |
| Coupon book cards | `js/digital-gifts.js` | the `coupons` array at the top |
| Video | `video.html` | the `<source src="...">` in `.video-frame`, plus the caption below it |

Every editable section above is marked in the code with an
`✏️ EDIT ME` comment.

## Notes on the placeholder photos

The 50 images in `/images` are generated placeholders in the site's
own midnight/burgundy/gold palette, just so the gallery looks and
behaves correctly out of the box. Replace them with real photos
whenever you're ready — the gallery, lightbox, and lazy-loading will
all keep working exactly the same.

## Structure

```
/
├── index.html             Landing / main hub ("Our Little World")
├── home.html              Same hub content, also reachable directly
├── love-letter.html
├── notes.html
├── gallery.html
├── memories.html
├── digital-gifts.html     Coupon book (incl. the "Yes Day" redeem flow)
├── video.html
├── the-last-lock.html     The grand finale (self-contained, not in the nav)
├── style.css
├── js/
│   ├── main.js            particles, transitions, nav, music, easter egg
│   ├── password.js        lock validation logic
│   ├── notes.js
│   ├── gallery.js
│   ├── memories.js
│   └── digital-gifts.js   coupon data + Yes Day calendar/time picker
├── images/photo1.jpg … photo50.jpg
└── video/for-you.mp4      (add your own file here)
```

Made to feel like a private little world — for one person. ♡