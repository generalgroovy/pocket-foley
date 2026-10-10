# Pocket Foley

Build sound effects from tone, noise and click layers. Preview and WAV export use the same samples.

## Run and use

Run `python -m http.server 8000`, then open http://localhost:8000. There are no dependencies or build steps. Choose a clearly marked **▶ Pop**, **▶ Whoosh**, **▶ Zap**, **▶ Knock**, **▶ Shimmer** or **▶ Thud** starting sound to select and hear it in one action. **Play sound** replays your current edited result. Preset selection is undoable; Undo and project imports never start audio. Adjust Length and Softness. **Save WAV** downloads a usable sound without opening deeper settings.

**Sound ingredients** contains the Tone/Noise/Click mix, starting pitch and pitch movement in semitones. The noise texture is deterministic; **New noise texture** changes only its seed. Zeroing all ingredients shows a persistent **This sound is silent** message with **Restore tone**. Recovery preserves length, texture and pitch settings, supports Undo, returns focus to Play and stays muted until you play. Edits stop audio, as do Stop and hiding the tab. Playback never starts on load or import.

Undo restores up to 30 edits in the current session. Settings save in this browser when available; JSON download/open supplies a portable editable project. Invalid imports preserve current work. WAV output is mono, 44.1 kHz, 16-bit PCM, 0.08–2 seconds. Preview converts the exact exported integer samples to the browser audio buffer. The device may resample playback and determines actual loudness; rendering identity is not a physical sound guarantee.

## Verify

Run `npm test` with Node 18+. Tests cover all presets, silent endpoints, deterministic noise, all-zero silence, every serialized WAV sample and header, maximum settings, validated bounds and independent imported state. Actual-handler tests with minimal DOM/audio doubles cover explicit one-click preset playback, no autoplay, cancellation of a pending audition by an edit and one-step silent recovery. These doubles do not establish browser output or audible quality. Audio quality still needs listening. There is no recording, sampler upload, MIDI, sequencing, external media import or multi-file batch export.

## Originality and possible depth

Original synthesis code, inspired by KO II Sampler's sample-making workflow. This is a small sound-effect instrument rather than another DAW. Future possibilities, not shipped: editable envelopes, multi-effect recipes, sample packs and stereo motion.
