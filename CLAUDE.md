# Lulu & Bagel: A Day at Home — Project Documentation

## Project Overview
This is a personal webtoon reader web app built as a
gift. It is a single index.html file that runs locally
in any browser with no server or internet required. It
tells the story of Irvin and Leah and their two dogs
Lulu and Bagel across 12 illustrated panels.

## Characters
- Leah: petite girl, long dark brown hair, cream
  oversized sweater, light blue jeans, pearl stud
  earrings. The heart of the story. Warm, whimsical,
  loves animals.
- Irvin: tall broad-shouldered boy, short messy dark
  brown hair, dark navy hoodie, khaki jogger pants,
  white sneakers. Enthusiastic, protective, goofy,
  deeply loving.
- Lulu: female West Highland White Terrier. Fluffy
  pure white coat, poofy head, small black eyes and
  nose, perky ears. Fearless, curious, gets into
  everything — the instigator.
- Bagel: male tricolor Pembroke Welsh Corgi. Black
  saddle, white chest and paws, red-orange face and
  legs, large upright ears, wide round eyes, stubby
  legs, round fluffy butt. Food-obsessed, surprisingly
  fast, dramatic reactions.

## Story Structure
- Act 1 (Panels 1-4): The Great Kitchen Disaster.
  Bagel steals dropped food. Tone: warm, cozy, comedic.
- Act 2 (Panels 5-7): The Mystery Bark. A distant bark,
  Lulu is missing, the search begins. Tone: gentle
  mystery, building anxiety.
- Act 3 (Panels 8-10): Hero on the Roof. Lulu found on
  rooftop, Irvin's terrified rescue, tender moment.
  Tone: dramatic, heroic, tender.
- Ending (Panels 11-12): Everyone safe, Bagel still
  sniffing for food, a tiny fairy appears on the
  windowsill watching. Tone: warm, magical, wonder.

## Panel Dialogue Reference
- Panel 1: Leah: "Should we add more garlic?" /
  Irvin: "Always more garlic."
- Panel 2: No dialogue
- Panel 3: Bagel thought bubble: "MINE."
- Panel 4: Leah: "BAGEL—" / Irvin: "He was SO FAST—"
- Panel 5: Leah: "...Did you hear that?" /
  Irvin: "Was that Lulu?"
- Panel 6: Leah: "Lulu? Lulu!!" /
  Irvin: "She's not down here—"
- Panel 7: Irvin: "...Leah."
- Panel 8: Lulu thought bubble: "I can see everything
  from up here." / Leah: "LULU!!!"
- Panel 9: Leah: "THEY'RE THE SAME LEFT!!" /
  Irvin: "Go LEFT! No! YOUR left!!"
- Panel 10: Irvin: "You absolute little—
  ...I love you so much."
- Panel 11: Leah: "I can't believe that just happened."
  / Irvin: "Bagel... she's been down for ten minutes."
- Panel 12: No dialogue. Soft shimmer effect only.

## File Structure
adventures-of-lulu-and-bagel/
├── index.html
├── CLAUDE.md
├── README.txt
└── panels/
    ├── cover.png
    ├── panel_01.png
    ├── panel_02.png
    ├── panel_03.png
    ├── panel_04.png
    ├── panel_05.png
    ├── panel_06.png
    ├── panel_07.png
    ├── panel_08.png
    ├── panel_09.png
    ├── panel_10.png
    ├── panel_11.png
    └── panel_12.png

## How to Add Panel Images
1. Generate all 13 images (cover + 12 panels) in
   ChatGPT using your character prompts
2. Save them with the exact filenames listed above
3. Drop them into the /panels folder
4. Open index.html in any browser

## How to Run
Open index.html in any browser. No server needed.
No internet needed. No installation needed.

## How to Deploy Online
1. Go to netlify.com
2. Click Deploy Manually
3. Drag the entire lulu-bagel-webtoon folder onto
   the page
4. Netlify gives you a live URL in 30 seconds

## Future Chapters
This is Chapter 1. Future chapters can be added by:
1. Creating /chapter-02/panels/ folder
2. Adding a new section in index.html for chapter 2
3. Adding a chapter select screen at the opening

## Multi-Chapter Infrastructure

### URL structure
index.html              — series landing page
reader.html?chapter=01  — chapter 1 reader
reader.html?chapter=02  — chapter 2 reader

### How the reader engine works
reader.html is a reusable engine. It reads the
chapter URL parameter, fetches the corresponding
meta.json, and dynamically renders all panels,
dialogue, and effects. No changes to reader.html
are ever needed to add new chapters.

### How to add a new chapter
1. Create folder: chapters/chapter-XX/
2. Create folder: chapters/chapter-XX/panels/
3. Add cover: chapters/chapter-XX/cover.png
4. Add panels: panel_01.png through panel_XX.png
5. Create chapters/chapter-XX/meta.json with:
   - chapterNumber, title, subtitle, description
   - panelCount
   - dialogue object with all bubble data
6. Add one new object to CHAPTERS array in index.html
7. Push to GitHub — Netlify auto-deploys

### meta.json dialogue bubble types
- "speech"  — organic oval with pointed manga tail
- "thought" — cloud shape with three dot trail
- modifier "dramatic" — 12-point starburst shape
- modifier "quiet"    — smaller, faded, thin tail

### Bubble position class values
pos-top-left    pos-top-center    pos-top-right
pos-mid-left    pos-mid-center    pos-mid-right
pos-bot-left    pos-bot-center    pos-bot-right

### Tail direction values
left | right | top | bottom

### Updated file structure
adventure-of-lulu-and-bagel/
├── index.html      — series landing page
├── reader.html     — reusable reader engine
├── CLAUDE.md
├── README.txt
└── chapters/
    └── chapter-01/
        ├── cover.png
        ├── meta.json
        └── panels/
            ├── panel_01.png
            └── ... through panel_12.png

## Customization Notes
- Background color: #0d0d0d
  (in CSS :root variables)
- Max panel width: 720px
  (in CSS :root variables)
- Speech bubble style: rounded white with soft shadow
  (in .bubble CSS class)
- Sparkle particle count: 50
  (in CONFIG object in JavaScript)
- All key settings stored in CONFIG object at top
  of JavaScript for easy editing

## Troubleshooting
- Images not showing: check filenames match exactly
  including underscore and two digit number
  (panel_01 not panel_1)
- Speech bubbles misaligned: tell Claude Code which
  panel and where to move it
- Works on desktop but not phone: open browser
  console, copy the error, tell Claude Code
- To change dialogue: find DIALOGUE_DATA object in
  index.html and edit the text strings directly

## Credits
Story concept and characters: Irvin
Art generated with: ChatGPT DALL-E / Midjourney
Webtoon reader built with: Claude Code
Made with love for: Leah
