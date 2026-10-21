# Thauma Synth — Portable Alpha

Thauma Synth is a live visual synthesizer for Windows. Mix four shape generators and video, build feedback and effects, and play the picture with your mouse, keyboard or MIDI controller. Send the result to a screen, projector or another program through Spout.

**[Download the latest portable alpha](https://github.com/Trashsurgery/Thauma-Synth-Portable-Alpha/releases/latest)**

This repository distributes the portable app and documentation. It is an alpha: expect rough edges and report problems to Athron.

> **Photosensitivity warning:** moving pictures, extreme settings and custom shaders can flash. Automated checks do not guarantee every possible input or setting is safe for every viewer.

## Start and update

1. Download the ZIP attached to the latest release.
2. Extract the entire ZIP into a **new writable folder**, outside Program Files.
3. Run `Thauma.exe`. Keep its DLLs and other files beside it.
4. Read `FIRST-TEN-MINUTES.txt` for a tour, `README.txt` for the reference and `CONTROLLERS.md` for MIDI setup.

Requires Windows 10/11, 64-bit, and OpenGL 3.3 or newer. There is no installer.

Back up an old copy before updating. Extracting into a fresh folder gives you the current bundled looks. You can then copy your own `presets` folder and `thauma-settings.txt` across; replacing presets also replaces the fresh library, so retain a clean copy if you want both. The updater preserves existing settings/presets and does not automatically add new default looks to an existing library. Older looks and stored keys remain supported.

## New in the 21 October alpha

- **XY:** a dedicated page, recorded trajectories, shared range/curve behavior with MIDI, and independent Snare/Hats triggers.
- **Recording enabled:** record the picture with optional sound, output choices and file-size limits. Synthetic file/timing/audio-video checks passed on the test PC.
- **Follow Krotala:** opt-in levels, hits, tempo and scene following, stale-input fallback and controller ownership. Tempo priority: running MIDI clock, fresh enabled Krotala, enabled Listen, internal tempo.
- **Sound and Hue:** hit/response options, consistent sound Followers and video Hue depth.
- **Settings and rigs:** grouped searchable Settings, named rig save/load, fullscreen persistence and per-look fades.
- **Panel:** consistent A/B snapshots, Spout sender persistence, navigation/scrolling repairs, grouped Cut controls, dimmed inactive controls, clearer help and MIDI behavior.
- **Terminology and guidance:** consistent Feedbacks/Modulation labels, compatibility with stored keys and legacy aliases, updated performer guidance and screenshots.

| Key | Action |
| --- | --- |
| F7 | Settings |
| F8 | Looks |
| F9 | Stage view of Perform |
| F10 | XY |
| F11 | Picture fullscreen |
| Ctrl+F | Find a control |
| Ctrl+O | Clip browser |

Record has its own tab. MIDI is opt-in: Settings > MIDI > Use MIDI devices.

## Validation and limitations

The final code passed **2,013 automated checks**, the control audit and comparisons for **25 baseline looks**. The public package also passed shipped-look and extracted-update checks. Public packaging excludes personal clips, drive paths and the specified clip-dependent looks/pictures.

**The final two-hour soak was cancelled at the user's request and has not been completed.** Physical MIDI/LED, external Spout/Krotala coexistence, real audio/recording synchronization, projector use and subjective checks remain pending. Some baseline comparisons used fallback pictures because personal media was unavailable. An existing capture-off waveform-retention limitation remains noted. These results do not establish behavior on every PC or device.

## Reporting problems

Tell Athron what you did, what happened, your Windows version and graphics card. A short video can help. Include relevant `logs`, `crash.txt` or `startup-errors.txt` when present; check for personal paths before posting logs publicly.

## Licences

Thauma is distributed under the [MIT licence](LICENSE). Components and notices are listed in [THIRD-PARTY-LICENSES.txt](THIRD-PARTY-LICENSES.txt) and the package credits. FFmpeg is supplied as replaceable DLLs with corresponding source/build material under `FFmpeg/source`; see its included LGPL terms. Keep the complete portable folder and notices together when redistributing it.

## Support development

Want to support me developing this? Want more updates and features faster? Consider donating to help me afford a higher AI subscription.

[Support Vionysus Visuals](https://paypal.me/VionysusVisuals)

If you decide to alter the project yourself, please share what you do with me! I'd love to see the direction you take it.
