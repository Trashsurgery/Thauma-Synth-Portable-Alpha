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

## What's new in v2026.10.20-alpha

This is a big update since the first alpha (17 October). In short, there are more shapes, more effects and more trail styles. The panel has been rebuilt around one idea: every control stays on screen. Thauma also comes with Athron's own looks now.

> **Updating from the 17 Oct alpha?** Unzip this version into a **new folder**. Then copy your
> own `presets` folder (and `thauma-settings.txt` if you like) across. Looks saved in the first
> alpha still load.

### New shapes and pictures

- **9 new shape types (26 in all):** Mandala, Horizon (a grid floor running to the horizon),
  Globe (a turning wireframe sphere), Rain, Radar, Filigree (fine curling threads), Magnet,
  Tangent (bands that rise slowly, hold bright, then drop at a razor edge) and **Shader**. Shader
  plays an ISF shader that draws a picture of its own; 7 come in the `shape-shaders` folder.
- **Every shape** gets **Mirror turn**, which turns the fold lines while the picture inside keeps
  its own spin. It also gets **Drift Y**, which slides the shape up or down and brings it back in
  as a mirror image, and **Aspect**, which stretches it wide or tall.
- **Step fold**, a new mirror mode. Each tenth of the mirror knob folds the picture smaller and
  more symmetrical, in steps instead of a smooth slide.
- **Shapes can bend each other:** one shape can push, scale, turn, pixelate, repeat, scroll or
  tint another. A shape can also be bent by the mix.
- **20 blends** in the mixer (10 new), and an **Inv** button that turns any blend into its
  inverted version.
- **Many controls have new, plainer names on screen**, for example Sine, Square, Circle, Rose,
  Kaleidoscope, Pixelate and Grain. Looks and MIDI maps saved with the earlier names load as
  before, and Ctrl+F finds a control by either name.

### Video

- **Clip browser** (Ctrl+O) shows your video folder as pictures. Drag a clip onto a shape to play
  it there. There are also pad actions for the next and previous clip.
- **Choose your video folder** with "Choose folder..." at the top of the clip browser, or drag a
  folder onto it. **Drag a video straight from File Explorer** onto a shape to play it there.
- **Looks find their clips on another computer** when the clips sit in the same place inside its
  video folder.
- **Spout in:** a Video shape can play another program's Spout picture.
- **HAP clips are now unpacked on the graphics card**, so they cost almost nothing on the
  processor.
- **Smooth slow motion** (blends between frames), **webcam delay** (up to 4 seconds, to dance with
  your own echo), **Stutter** (repeats a beat, 2 beats or a bar, then slips back like a DJ) and
  **Scrub glide** (scratch through a clip smoothly).
- **Views:** Picture, Motion (only what moves), or Outlines. There is also a **colour key** for
  green screen.

### Trails and feedback loops

- **3 new trail styles (12 in all):** Ember, Prism (coloured ribbons) and Static.
- **6 new loop stages (24 in all):** Dapple (Turing spots), Liquid (paint stirred on a slow
  liquid), Monitor (the loop filmed off a screen), Ring (every change rings like a bell), Current
  (drifts on a slow current) and Delay (copies from up to two seconds ago).
- **Every stage has a third knob and four flavours.** For example, Smoke can be Steam, Flame or
  Incense. There is also a **Where** setting that keeps a stage to the bright parts, the dark
  parts, the edges or one shape.
- **Loops 2 to 4 are now full loops**, with every control the main loop has. A loop can also
  sit *before* the trails, as a second trail on the mix.
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
- **Timeslice has more to it:** a ribbon, rings and three colour patterns.
- **Memory echo** and **Echo of shape** can lock to the tempo, in bars.
- **The FX page is the whole rack.** Every effect and the 8 custom shader slots are each a column,
  in the order they run, with all their knobs on screen. You can shrink any column to a
  half-width strip, and it keeps running. **In use** shows only the effects this look uses.
  Switching an effect off never takes its column away.
- **Every effect has a blend mode and a Depth knob.**
- **Dry** brings back the clean picture at any point in the chain. **FX mix** fades the whole
  rack in or out.
- **Master colour**, the very last stop before the screen and Spout: brightness, contrast, black
  level, gamma, saturation, vibrance, hue, warmth, tint, sharpen and a "keep colour" switch for
  bright lights.

### Controls and the panel

- **Thauma opens on the Shapes page**, which shows all four shapes side by side with every control
  in open-and-close sections.
- **The Trails page** shows each loop in tabs, with Paint and the Mix and Output knobs beside it.
- **Mixer bar:** click a shape, TRAILS, MIX or OUT to jump to it. Right-click a thumbnail for a
  quick sheet of its most-used knobs.
- **No more limit on movers.** A look can have as many LFOs, step sequencers, random sources,
  drunk walks, envelopes, followers and maths movers as you like. Right-click a knob to see its
  movers and set each one's depth, invert, wrap, curve or mute.
- **Knobs show what is moving them:** a violet arc for the range its movers sweep, a dot for
  MIDI, and the live value under the knob.
- **Numbers hold still.** Every digit takes the same width, each knob shows a fixed number of
  decimals, and value boxes and hover boxes keep one size, so a value that a mover is changing
  no longer jumps around.
- **The knob right-click menu** has **Random value** (throws one knob somewhere new), **Mute all**
  for its movers, and **Show on its page**. Its choices are colour-coded by kind.
- **Right-click > Show as** turns a knob into a fader, a slider or a number box.
- **Your own colours:** recolour a part of the panel or a single knob, and save colour presets.
  There are also three themes: Graphite, Midnight and Paper.
- **Setup (F7):** find a setting by name, a **Controls** topic (how far a drag goes, how fine
  Shift is, tooltips, double-click reset), **Back to defaults** for each topic, and a searchable
  key table. Its **Speed** topic shows what each part of a frame costs.
- **Perform page:** pads can be **Tap**, **Hold** (on only while held, good for a downbeat) or
  **Step**. Look pads page through your whole library. **Re-light controllers** sends every
  controller light again.
- **Look fades:** fades start without a hitch, because fade pictures are prepared ahead of time.
  There is also a new **Afterglow** fade, which keeps the old look's trails running under the
  fade.
- **FIRST-TEN-MINUTES.txt** in the folder is a short tour for your first start.

### Looks

- **Athron's own looks now ship with the starter looks:** 32 looks in all. Where his version of
  a starter look exists (Four Blends, Timeslice), his is the one you get. Looks that need a video
  clip are left out of this download.
- **Load now:** a look's right-click menu can load it with no fade, for a hard cut on a beat.

### Stability

- **On laptops with two graphics chips, Thauma asks for the fast one**, so it runs on your
  gaming card and not the built-in one.
- **Thauma keeps logs** in a `logs` folder next to `Thauma.exe`. If it crashes, it also keeps a
  crash report there. If the picture freezes for 15 seconds, it saves a snapshot of the freeze.
  Please send that folder along with any problem report.
- **After a crash, Thauma comes back on the look that was playing.**
- **`last-exit.txt`** says when and how Thauma last closed, which helps trace an unexpected quit.
- **Updating keeps your files.** Your looks and settings are never in the new folder, so copying a
  new version over an old one never replaces them.
- **An earlier build this week passed a two-hour run** on the build PC with no crash and no freeze.
- **Tested on a second PC** (Intel graphics), with clips, for 40 minutes.

### Fixes

- **A big window or screen shows the picture sharp** instead of soft.
- **Controls stay where they are** when a list grows.
- **Short faders** are no longer twitchy.
- **The Phosphor effect** no longer flickers.
- **Escape** closes an open blend list.
- **The video picker** no longer stalls the panel while it reads a big folder.
- **Setup's footer** wraps instead of being cut off on a narrow window.

### Still the same

- **Recording is still switched off.** To record the picture, take it into OBS over Spout.
- **Still not tried with the real thing:** real MIDI controllers, real HAP files and DXV files
  exported from Resolume. Please tell Athron how yours behave.

---

## Download and run

1. Go to **Releases** on the right of this page and download
   `Thauma-Synth-Portable-Alpha-2026-10-20.zip`.
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
You can change this in the Setup window (F7): *monitor* for the picture, *panel_monitor* for
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

### Trails and feedback loops

The mixed picture is fed back on itself to make trails. You set how long they last, how they zoom,
turn, drift and spin, and what comes back in from the edges (black, fold, tile or smear).

- **12 trail styles**, among them Classic, Iris, Glint, Mirror, Ouroboros, Ember, Prism and
  Static.
- **24 stages** that shape the feedback as it goes round: smoke, ink, tunnels, neon edges,
  kaleidoscope folds, melting, erosion, breathing, liquid, delay and more. Up to three run at
  once, each with four flavours.
- **Loops 2 to 4**: three more feedback loops, each with every control the main loop has. Each
  loop can sit on a single shape, before or after the trails, or after the effects.
- **Copy rate**: how many copies the feedback makes a second. It stays even whatever your
  frame rate does.
- **Paint**: draw into the trails with the mouse (P).

### Effects (FX page)

- **43 built-in effects**, from kaleidoscope, pixelate, glow and grain to old film, worn tape,
  datamosh, sun rays and characters. The FX page shows the whole rack: every effect a column, in
  the order it runs, all knobs on screen. Drag a column's name onto another to change the order.
- **In use** shows only the effects this look uses. Off never takes a column away.
- Every effect has a **blend** and a **Depth** knob. **Dry** and **FX mix** bring back the clean
  picture. **Master colour** is the last colour stage before the screen.
- **MIDI focus knobs**: one set of knobs that moves whichever effect is in focus, so a few MIDI
  knobs reach every effect.
- **8 custom shader slots** for ISF shaders (the `.fs` format VDMX and Resolume use). Every
  number, list and switch the shader has gets its own knob (up to 24 per slot). Colours and
  points get pickers, and events get buttons.
- **Shader browser** with categories, search and credits. About 40 shaders by other authors
  come with Thauma (credits in each folder's `CREDITS.txt`).

### Movement (Motion page)

Four LFOs, a drunk walk, two 16-step sequencers, a random source and sound followers (level,
bass, mids, highs and kick) can move any control. **Eight macros** each move several controls
at once. Movement can follow tap tempo or a MIDI clock. Thauma limits how fast anything can
change, so movers never strobe.

### Looks

A **look** is a saved picture setup. Thauma comes with 32 looks: the starter looks and Athron's own.

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
- **Stage view** (F9): a simple gig screen with your Perform controls and looks.

### Panel and Setup

- Seven pages: Perform (F1), Shapes (F2), Trails (F3), FX (F4), Motion (F5), Looks (F6),
  Setup (F7). Thauma opens on Shapes.
- **Setup (F7)**: every setting with a plain name, grouped by topic. Each change works at once
  and is saved.
- The show bar along the top has tempo, sound meters, Undo/Redo, Clear trails, Freeze,
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
5. Press **F3** (Trails) and play with Amount, Zoom and Rotate. That's where most of the
   magic is.
6. Like what you see? **Ctrl+Shift+S** saves it as a new look.

### Handy keys

| Key | What it does |
|---|---|
| F1 – F7 | Panel pages |
| F8 / F9 | Presets drawer / Stage view |
| F11 or Alt+Enter | Fullscreen |
| B / F / C | Blackout / Freeze / Clear trails |
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

MIDI is **off** at first. To turn it on, press F7 for Setup, open **MIDI** and tick **Use MIDI
devices**. Then switch your controller's input on (and its output, for lights).

- Thauma has ready-made maps for the **Novation Launch Control XL** and **Akai APC40** (mk1 and
  mk2). Any other controller gets a generic map. `CONTROLLERS.md` in the folder lists what every
  knob does.
- To put any control on any knob: right-click the control, choose **MIDI learn**, then move a
  knob.
- Tempo can follow a MIDI clock (Setup → MIDI).

The ready-made maps were checked with made-up MIDI messages. Real hardware may hold surprises.
Please report how yours behaves.

---

## Smooth motion: frame cap and Vsync

In Setup (F7):

- **Frame cap**: the most frames a second Thauma draws (60 at first). Set it to your screen's
  refresh rate, for example 120 on a 120 Hz screen.
- **Vsync**: turn it **on** for the smoothest motion. Without it, Thauma's frames and the
  screen's refreshes drift against each other, and every now and then a frame shows twice.
- If your graphics card can't keep up, the fps counter turns red. Lower the frame cap, or set
  *draw_scale* to 2, which draws at half size.

---

## No strobing

Thauma is built not to flash. A built-in check plays every shape type, trail style, stage,
effect, starter look and mover at its fastest. Anything that flashes more than three times a
second (the photosensitivity guideline) fails. The one style that flickers by nature,
**Flipbook**, has a **steady** switch that stops it.

Shaders from elsewhere were not made with that rule in mind. Try them at a few amounts before
showing them to anyone. Also, a shader that loops forever can stall your graphics card until
Windows resets it, so try new shaders before a show, not during one.

---

## Known limits of this alpha

- **Tested on two PCs only.** Your graphics card, screens or Windows may behave differently.
- **Recording is switched off** in this build. Use OBS over Spout if you want to record.
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
| `thauma-settings.txt` | Your settings (easiest to change in Setup, F7) |
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
