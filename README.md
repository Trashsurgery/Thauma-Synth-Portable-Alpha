# Thauma Synth — Portable Alpha

Thauma Synth is a live visual synthesizer for Windows. It makes moving pictures from four shape
generators, mixes them, feeds the result back on itself to make trails and echoes, runs it
through an effects rack, and sends the picture to a screen, a projector or other programs. You
play it with the mouse, the keyboard and MIDI controllers.

This is an **alpha**: an early build shared with a few friends to try out. Expect rough edges,
and please tell Athron what you find (see [Reporting problems](#reporting-problems)).

> **Photosensitivity warning.** Thauma makes moving, colourful, sometimes fast-changing
> pictures. Thauma is built not to strobe (see [No strobing](#no-strobing)), but custom shaders
> from elsewhere and extreme settings can still flash. If you or anyone watching is sensitive to
> flashing light, take care.

---

## What's new in this alpha

**28 October feedback timing update:** feedback movement is steadier with the frame rate limit
off and while the control panel updates. The main loop and loops 2–4 on the full engine share
the corrected clock, which smooths uneven frames while keeping the loop's elapsed-time speed.
The Frame budget display is also corrected, and measuring no longer waits for the graphics
card. Existing look files and control assignments remain compatible.

[Source change](https://github.com/Trashsurgery/Thauma-Synth/commit/3f2751be).

This is a big update since the first alpha (17 October). In short:

- more shapes, effects and feedback styles;
- recording is back, with sound and presets for YouTube, Discord, Messenger and Instagram;
- XY pads you can play and record;
- Thauma can find the tempo by listening;
- the panel has been rebuilt so that every control stays on screen and explains itself.

> **Updating from an earlier alpha?** Unzip this version into a **new folder**. Then copy your
> own `presets` folder (and `thauma-settings.txt` if you like) across. Looks saved in the first
> alpha still load.

### New names on screen

Several pages and controls have new names. Looks, rigs and MIDI maps saved with the old names
load as before, and Ctrl+F finds a control by either name.

- **Trails** is now **Feedback**, and its page (F3) is **Feedbacks**.
- **Movers** are now **modulators**, and the Motion page (F5) is the **Modulation** page. A knob's
  card is the **Modulation card**.
- The spin and drift boxes on the Shapes and Feedbacks pages are called **Movement**.
- **Setup** (F7) is now **Settings**.
- **Yin-Yang** is now **Calm / Wild**.
- Many shapes and effects use plainer names on screen, such as Sine, Square, Circle, Rose,
  Kaleidoscope, Pixelate and Grain.

### New shapes and pictures

- **9 new shape types (26 in all):** Mandala, Horizon (a grid floor running to the horizon),
  Globe (a turning wireframe sphere), Rain, Radar, Filigree (fine curling threads), Magnet,
  Tangent (bands that rise slowly, hold bright, then drop at a razor edge), and **Shader**, which
  plays an ISF shader that draws its own picture. Seven shaders for it come in the
  `shape-shaders` folder.
- **Three new controls on every shape:**
  - **Mirror turn** turns the fold lines while the picture inside keeps its own spin.
  - **Drift Y** slides the shape up or down and brings it back in as a mirror image.
  - **Aspect** stretches the shape wide or tall.
- **Step fold**, a new mirror mode. Each tenth of the mirror knob folds the picture smaller and
  more symmetrical, in steps instead of a smooth slide.
- **Shapes can bend each other.** One shape can push, scale, turn, pixelate, repeat, scroll or
  tint another, and a shape can be bent by the mix.
- **20 blends** in the mixer (10 new), and an **Inv** button that turns any blend into its
  inverted version.
- **Cut controls are together.** Dark cut, bright cut, key and crop now sit under one **Cut**
  heading.

### Video

- **Clip browser** (Ctrl+O) shows your video folder as pictures. Drag a clip onto a shape to play
  it there, or use the pad actions for the next and previous clip.
- **Choose your video folder** with "Choose folder..." at the top of the clip browser, or drag a
  folder onto it. You can also **drag a video straight from File Explorer** onto a shape.
- **Looks find their clips on another computer** when the clips sit in the same place inside its
  video folder.
- **Spout in.** A Video shape can play another program's Spout picture, and you choose which
  program from a list.
- **Hue depth** decides whether a video takes the shape's hue (every colour in the clip turns
  together) or keeps its own colours.
- **HAP clips are unpacked on the graphics card**, so they cost almost nothing on the processor.
- **New ways to play a clip:**
  - **Smooth** slow motion blends between frames.
  - **Webcam delay** shows you up to 4 seconds late, to dance with your own echo.
  - **Stutter** repeats a beat, 2 beats or a bar, then slips back like a DJ.
  - **Scrub glide** lets you scratch through a clip smoothly.
- **Views:** Picture, Motion (only what moves), or Outlines. There is also a **colour key** for
  green screen.

### Feedback loops

- **3 new feedback styles (12 in all):** Ember, Prism (coloured ribbons) and Static.
- **6 new loop stages (24 in all):**
  - Dapple (Turing spots);
  - Liquid (paint stirred on a slow liquid);
  - Monitor (the loop filmed off a screen);
  - Ring (every change rings like a bell);
  - Current (the picture drifts on a slow current);
  - Delay (copies from up to two seconds ago).
- **Every stage has a third knob and four flavours.** For example, Smoke can also be Steam,
  Flame or Incense. A **Where** setting keeps a stage to the bright parts, the dark parts, the
  edges or one shape.
- **Loops 2 to 4 are now full loops**, with every control the main loop has. A loop can also
  sit *before* the main feedback, as a second feedback on the mix.
- **Spin** now turns the whole pattern of echoes over time, like turning the camera, without
  scrambling the copies.

### Effects

- **23 new effects (43 in all)**, among them:
  - blurs: Veil (soft focus), Tilt (tilt-shift) and Swish (spin and slide blur);
  - worn screens: Phosphor (old picture tube), Nitrate (old film) and Dropout (worn video tape);
  - glitches: Judder, Scramble and Mire (datamosh);
  - light: Lance (anamorphic streaks), Shafts (sun rays) and Hone (sharpen);
  - Inkwash, Shear, Tincture (seven colour maps), Pebble (ripple rings), Cascade (echo taps),
    Crease, Fracture, Glyph (characters), Drift and Cycle.
- **Every effect explains itself** in plain words. The text shows in the Add list, on its name
  and on each of its knobs.
- **Timeslice has more to it:** a ribbon, rings and three colour patterns.
- **Memory echo** and **Echo of shape** can lock to the tempo, in bars.
- **The FX page is the whole rack.**
  - Every effect and the 8 custom shader slots are each a column, in the order they run, with
    all their knobs on screen.
  - You can shrink any column to a half-width strip, and it keeps running.
  - **In use** shows only the effects this look uses.
  - Switching an effect off never takes its column away.
- **Every effect has a blend mode.** A **Depth** knob shows when the blend is not "mix".
- **Dry** brings back the clean picture at any point in the chain. **FX mix** fades the whole
  rack in or out.
- **Master colour** is the very last stop before the screen and Spout. It has brightness,
  contrast, black level, gamma, saturation, vibrance, hue, warmth, tint and sharpen, plus a "keep
  colour" switch for bright lights.

### Recording

- **Recording is back**, on its own **Record** page and with Record in the show bar.
- **Five quality presets**, from Doppelganger (full size, every frame) down to Light. Each one
  shows how big the file gets and how long your disk will last.
- **Choose the length** (free, or 1 to 16 bars) and when it starts (now or on the next bar).
- **Sound** comes from an input you pick, and stays in step with the picture.
- **"Made for" modes:**
  - YouTube (up to 2160);
  - Discord and Messenger (stays under the upload size limit);
  - Instagram (upright 9:16, 4:5 or square, with the wide picture fitted over a blurred copy,
    cropped, or turned).
- **The live picture never waits for a recording.** If the PC falls behind, the recording leaves
  out a frame and counts it.

### Playing

- **XY pads** (F10).
  - Add as many pads as you like and link any controls to each pad's X, Y, speed, distance,
    angle or touch. Each link has its own range, invert and curve.
  - Pads have puck modes: Direct, Hold, Inertia, Spring, Bounce, Gravity, Orbit, Attractors,
    Path and Push.
  - **Arm recording** records your hand and loops it in time with the tempo: forwards,
    backwards or ping-pong. You can overdub on top.
  - Any pair of X and Y knobs can also be shown as one pad (right-click > Show as).
- **Listen.** A button beside Tap finds the music's tempo by ear, and the kicks keep the beat in
  line. /2 and x2 fix half or double time.
- **Snare and Hats** join Kick as sound modulators. A **Sharp kick** setting catches kicks over
  a loud bass. A **Quick response** setting makes the sound levels jump up four times sooner on
  a hit. Both settings are off at first.
- **MIDI settings:**
  - each device can listen on one channel;
  - every learned control has Low, High, Invert, Curve and Mute;
  - a **MIDI monitor** shows what comes in.
- **Perform page.**
  - Pads can be **Tap**, **Hold** (on only while held, good for a downbeat) or **Step**.
  - Look pads page through your whole library.
  - **Stage view** (F9) shows the Perform page alone, full window, with a switch between macros and look
    pictures.
- **Store A and Store B** work the same everywhere. A click on a stored snapshot morphs to it,
  and Ctrl+click stores it again.
- **Looks:**
  - **Load now** cuts to a look with no fade;
  - a look's own fade runs up to 60 seconds;
  - fades start without a hitch;
  - a new **Afterglow** fade keeps the old look's feedback running under the fade.

### Controls and the panel

- **Thauma opens on the Shapes page.** It shows all four shapes side by side, with every control
  in sections that open and close.
- **The Feedbacks page** shows each loop in tabs, with Paint and the Mix and Output knobs beside
  it.
- **Mixer bar:** click a shape, FEEDBACK, MIX or OUT to jump to it. Right-click a thumbnail for a
  quick sheet of its most-used knobs. Store A/B, Morph, Mutate and Evolve live on OUT.
- **No more limit on modulators.** A look can have as many LFOs, step sequencers, drunk walks,
  envelopes, followers and maths modulators as you like.
- **The knob right-click menu** sets each modulator's depth, invert, wrap, curve or mute. It also
  has **Random value** and **Show on its page**. Its choices are colour-coded.
- **Every control's hover box says what it does** in one plain sentence. The hover box is now
  called the **mouse flyover window**, and you can turn it off in Settings.
- **Knobs show what moves them:** a violet arc shows the range its modulators sweep, a dot shows
  MIDI, and the number under the knob is the live value. The numbers hold still as they move.
- **Controls that do nothing right now are faded.** They still turn, and their hover box says
  when they act.
- **Right-click > Show as** turns a knob into a fader, a slider or a number box.
- **Your own colours:** recolour a part of the panel or a single knob, and save colour presets.
- **Settings (F7)** has seven topics: Picture, MIDI, Sound and video, Panel, Knobs, Looks and
  Keys.
  - Find any setting by name.
  - Each topic has **Back to defaults**.
  - Rigs are saved by name and loaded from a list.
  - The key table lists every key.
- **F8** opens the Looks page.
- **FIRST-TEN-MINUTES.txt** in the folder is a short tour for your first start.

### Looks

- **30 looks** ship with this download: Athron's own looks and the starter looks he kept. Looks that need a video clip are left out.

### Stability

- **On laptops with two graphics chips, Thauma asks for the fast one**, so it runs on your
  gaming card and not the built-in one.
- **Logs:**
  - Thauma keeps logs in a `logs` folder next to `Thauma.exe`;
  - if it crashes, it keeps a crash report there too;
  - if the picture freezes for 15 seconds, it saves a snapshot of the freeze.

  Please send that folder along with any problem report.
- **After a crash, Thauma comes back on the look that was playing.**
- **`last-exit.txt`** says when and how Thauma last closed, which helps trace an unexpected quit.
- **Updating keeps your files.** Your looks and settings are never in the new folder, so copying a
  new version over an old one never replaces them.
- **An earlier build this week passed a two-hour run** on the build PC with no crash and no
  freeze.
- **Tested on a second PC** (Intel graphics), with clips, for 40 minutes.

### Fixes

- **Big screens:** a big window or screen shows the picture sharp instead of soft.
- **Controls stay where they are** when a list grows.
- **Short faders** are no longer twitchy.
- **The Phosphor effect** no longer flickers.
- **Fill the screen:** F11 now updates the "Fill the screen" setting, so the next start matches.
- **Escape** closes an open blend list.
- **The video picker** no longer stalls the panel while it reads a big folder.

### Still to try

Real MIDI controllers, and real HAP and DXV files exported from Resolume, have still not been
tried with the real thing. Please tell Athron how yours behave.

---

## Download and run

1. Go to **Releases** on the right of this page and download
   `Thauma-Synth-Portable-Alpha-2026-10-28.zip`.
2. Unzip it anywhere you can write to: Desktop, Documents or a USB stick.
   **Not** `Program Files`: Thauma saves your looks and settings next to `Thauma.exe`.
3. Open the `Thauma Synth` folder and double-click **`Thauma.exe`**.

There is nothing to install and nothing is written outside that folder.

### "Windows protected your PC"

Thauma is not signed with a paid code-signing certificate, so Windows SmartScreen may warn you
the first time. Click **More info**, then **Run anyway**. That's normal for small apps shared
like this one. Only do it for a zip you got from this page.

### What you need

- Windows 10 or 11, 64-bit.
- A graphics card with OpenGL 3.3 or newer (any gaming card from the last ten years is fine).
- Two screens is ideal; one works too.

### Where things open

The picture and the control panel open on your **second screen**, so starting Thauma never
takes your main screen or keyboard away from other programs. With one screen, both open on it.
You can change this in Settings (F7): *monitor* for the picture, *panel_monitor* for
the panel.

---

## What it does

### Shapes

Four shape generators, A to D, each with its own colour, movement and mix level. There are
26 shape types, among them Sine, Square, Circle, Cube, Rose, Lissajous, Voronoi, Truchet, Flow,
Starfield, Waves, Flame, Metaballs, Noise, Mandala, Globe, Horizon, Rain, Radar, Tangent, Scope,
Video and Shader. Shapes can bend, colour or mask each other, and twenty blends mix them.

- **Video** plays a video, a still picture or the webcam inside a shape. Any file FFmpeg reads
  plays: DXV, HAP, ProRes, H.264, H.265 and more, plus PNG, JPG, BMP, GIF, TIFF and WebP
  pictures. DXV, HAP and ProRes play backwards and bounce smoothly. H.264 and H.265 can stutter
  backwards.
- **Scope** draws the sound coming into your PC as a line.

### Feedback loops (Feedbacks page)

The mixed picture is fed back on itself to make trails. You set how long they last, how they zoom,
turn, drift and spin, and what comes back in from the edges (black, fold, tile or smear).

- **12 feedback styles**, among them Classic, Iris, Glint, Mirror, Ouroboros, Ember, Prism and
  Static.
- **24 stages** that shape the feedback as it goes round: smoke, ink, tunnels, neon edges,
  kaleidoscope folds, melting, erosion, breathing, liquid, delay and more. Up to three run at
  once, each with four flavours.
- **Loops 2 to 4**: three more feedback loops, each with every control the main loop has. Each
  loop can sit on a single shape, before or after the main feedback, or after the effects.
- **Copy rate**: how many copies the feedback makes a second. It stays even whatever your
  frame rate does.
- **Paint**: draw into the feedback with the mouse (P).

### Effects (FX page)

- **43 built-in effects**, from kaleidoscope, pixelate, glow and grain to old film, worn tape,
  datamosh, sun rays and characters. Each one says in plain words what it does.
- **The FX page shows the whole rack.** Every effect is a column, in the order it runs, with all
  its knobs on screen. Drag a column's name onto another to change the order.
- **In use** shows only the effects this look uses. Off never takes a column away.
- **Every effect has a blend.** **Dry** and **FX mix** bring back the clean picture. **Master
  colour** is the last colour stage before the screen.
- **MIDI focus knobs**: one set of knobs that moves whichever effect is in focus, so a few MIDI
  knobs reach every effect.
- **8 custom shader slots** for ISF shaders (the `.fs` format VDMX and Resolume use). Every
  number, list and switch the shader has gets its own knob (up to 24 per slot). Colours and
  points get pickers, and events get buttons.
- **Shader browser** with categories, search and credits. About 40 shaders by other authors
  come with Thauma (credits in each folder's `CREDITS.txt`).

### Modulation (Modulation page)

LFOs, drunk walks, step sequencers, envelopes, sound followers (level, bass, mids, highs, kick,
snare and hats), maths modulators and XY pads can move any control, as many as you like. **Eight macros** each move several controls
at once. Movement can follow tap tempo or a MIDI clock. Thauma limits how fast anything can
change, so modulators never strobe.

### Looks

A **look** is a saved picture setup. Thauma comes with 30 looks: Athron's own and the starter looks he kept.

- Save (Ctrl+S), save as new (Ctrl+Shift+S), and step through looks (Page Up / Page Down).
- Looks fade into each other. Right-click a look on the Looks page to give it a
  **Fade picture**, a transition drawn from the old look into the new one (13 come with Thauma).
- Snapshots A and B, morphing between them, **Mutate** (M) and **Evolve** (E) for happy
  accidents.
- Undo and redo for everything (Ctrl+Z / Ctrl+Y).

### Output

- **Spout**: other programs (OBS, Resolume, TouchDesigner, …) can take Thauma's picture.
  Pick the Spout source called **Thauma** (or **Thauma_1** if another program already uses
  the name). The picture stays on the graphics card, so this costs almost nothing.
- **Fullscreen** on whichever screen the picture is on: F11 or Alt+Enter.
- **Recording** (Record page): record the picture with sound, with quality presets and modes
  made for YouTube, Discord, Messenger and Instagram.
- **Stage view** (F9): the Perform page alone, a simple gig screen with your Perform controls and looks.

### Panel and Settings

- Pages: Perform (F1), Shapes (F2), Feedbacks (F3), FX (F4), Modulation (F5), Looks (F6),
  Record, XY pads (F10) and Settings (F7). Thauma opens on Shapes.
- **Settings (F7)**: every setting with a plain name, grouped by topic. Each change works at once
  and is saved.
- The show bar along the top has tempo, sound meters, Undo/Redo, Record, Clear feedback, Freeze,
  Blackout and PANIC. The frames-a-second counter sits in the top-right corner. It turns red when
  Thauma runs slower than 90% of your frame cap.
- Ctrl+F finds any control by name.

---

## First steps

1. Start Thauma, press **F6** (Looks) and click a look.
2. Press **F2** (Shapes) and drag a few knobs. Drag **up and down** to turn a knob, and hold
   **Shift** for fine moves.
3. **Double-click** a knob to put it back. **Right-click** it for its menu: type a value, lock
   it, MIDI learn, see what moves it, or add it to the Perform page.
4. The **mouse wheel never changes a knob**. It only scrolls, so you can't bump a value by
   accident.
5. Press **F3** (Feedbacks) and play with Amount, Zoom and Rotate. That's where most of the
   magic is.
6. Like what you see? **Ctrl+Shift+S** saves it as a new look.

### Handy keys

| Key | What it does |
|---|---|
| F1 – F7 | Panel pages |
| F8 / F9 | Looks page / Stage view (the Perform page alone) |
| F10 | XY pads |
| F11 or Alt+Enter | Fullscreen |
| B / F / C | Blackout / Freeze / Clear feedback |
| Pause or Shift+Esc | Panic: calms everything down |
| T / Shift+T | Tap tempo / start a bar now |
| Ctrl+Z / Ctrl+Y | Undo / Redo |
| Ctrl+S / Ctrl+Shift+S | Save look / save as new look |
| Page Up / Page Down | Previous / next look |
| M / E | Mutate / Evolve on or off |
| Ctrl+F | Find a control |
| Ctrl + / Ctrl − / Ctrl+0 | Panel size |

---

## MIDI controllers

MIDI is **off** at first. To turn it on, press F7 for Settings, open **MIDI** and tick **Use MIDI
devices**. Then switch your controller's input on (and its output, for lights).

- Thauma has ready-made maps for the **Novation Launch Control XL** and **Akai APC40** (mk1 and
  mk2). Any other controller gets a generic map. `CONTROLLERS.md` in the folder lists what every
  knob does.
- To put any control on any knob: right-click the control, choose **MIDI learn**, then move a
  knob.
- Tempo can follow a MIDI clock (Settings → MIDI), or the music itself (Listen, beside Tap).

The ready-made maps were checked with made-up MIDI messages. Real hardware may hold surprises.
Please report how yours behaves.

---

## Smooth motion: frame cap and Vsync

In Settings (F7):

- **Frame cap**: the most frames a second Thauma draws (60 at first). Set it to your screen's
  refresh rate, for example 120 on a 120 Hz screen.
- **Vsync**: turn it **on** for the smoothest motion. Without it, Thauma's frames and the
  screen's refreshes drift against each other, and every now and then a frame shows twice.
- If your graphics card can't keep up, the fps counter turns red. Lower the frame cap, or set
  *draw_scale* to 2, which draws at half size.

---

## No strobing

Thauma is built not to flash. A built-in check plays every shape type, trail style, stage,
effect, starter look and modulator at its fastest. Anything that flashes more than three times a
second (the photosensitivity guideline) fails. The one style that flickers by nature,
**Flipbook**, has a **steady** switch that stops it.

Shaders from elsewhere were not made with that rule in mind. Try them at a few amounts before
showing them to anyone. Also, a shader that loops forever can stall your graphics card until
Windows resets it, so try new shaders before a show, not during one.

---

## Known limits of this alpha

- **Tested on two PCs only.** Your graphics card, screens or Windows may behave differently.
- **Not tried with real files or hardware yet**: real HAP files and real DXV files exported from
  Resolume, a second webcam, and MIDI controllers plugged in for real.
- `README.txt` inside the zip is the long technical manual. Where it disagrees with this page,
  this page is right.

---

## Your files

Everything lives in the `Thauma Synth` folder:

| | |
|---|---|
| `Thauma.exe` | The program |
| `thauma-settings.txt` | Your settings (easiest to change in Settings, F7) |
| `presets\` | Your looks, the library and your controller setup |
| `custom-shaders\` | ISF shaders for the custom slots, with credits |
| `shape-shaders\` | ISF shaders for the Shader shape type, with credits |
| `transitions\` | Fade pictures for look fades, with credits |
| `logs\` | Thauma's logs and crash reports (send this folder with a problem report) |
| `FIRST-TEN-MINUTES.txt` | A short tour for your first start |
| `CONTROLLERS.md` | What every MIDI knob does |
| `README.txt` | The long technical manual |
| `THIRD-PARTY-LICENSES.txt` | Licences of every part Thauma uses |

Every save writes a new file and keeps the previous one as `.bak`. If Thauma ever crashes,
`crash.txt` next to `Thauma.exe` holds its last log lines. Problems at start are in
`startup-errors.txt`.

To move to a new version, unzip it into a new folder, then copy your `presets` folder (and
`thauma-settings.txt` if you like) into it.

---

## Reporting problems

Tell Athron directly. Useful things to send:

- what you did and what happened (a phone video helps a lot with visual glitches);
- your graphics card and Windows version;
- the `logs` folder, and `crash.txt` or `startup-errors.txt` from the Thauma folder if there is one.

---

## Licences

Thauma Synth is open source under the **MIT licence**, Copyright (c) 2026 Athron. See
[LICENSE](LICENSE).

Parts made by others are listed with their full licences in
[THIRD-PARTY-LICENSES.txt](THIRD-PARTY-LICENSES.txt): GLFW, GLEW, Spout2, nlohmann/json,
RtMidi, Dear ImGui, the MinGW-w64 and GCC runtime parts, the Quicksand font (SIL Open Font
Licence), and **FFmpeg** (LGPL 2.1 or later, built without any GPL parts). FFmpeg's complete
source code and the script that built it are in the zip under `FFmpeg\source`, and the FFmpeg
DLLs may be replaced with your own build of the same major version. The bundled custom shaders
and transitions belong to their authors. See the `CREDITS.txt` file in each folder.
