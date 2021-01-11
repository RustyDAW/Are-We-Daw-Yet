# Are We DAW Yet?
A checklist of features needed to create a fully-featured Digital Audio Workstation (DAW) in the Rust programming language.

Join our community at the [`Rust Audio Discord`]!

## Algorithms
- [ ] scene graph
- [ ] panning
- [ ] dithering
- [ ] resampling
- [ ] time stretch
- [ ] sample-accurate timer
- [ ] multithreading
- [ ] swing-tempo

## UI
- Best UI library candidates
  - [`tuix`] - Built from the ground up with audio in mind. Still in early development.
  - [`iced`] - A popular Rust UI library, but currently has performance issues and lacks some features.
  - [`egui`] - Simple to use library with a lot of features, but performance may be an issue.
- [ ] peak/rms meters
- [ ] oscilloscope
- [ ] spectrometer
- [ ] waveform rendering
- [ ] piano roll
  - [ ] display midi notes
  - [ ] slice/copy/paste midi notes
  - [ ] quantizer
  - [ ] edit velocity/pan
  - [ ] grid sizes/snapping
  - [ ] time signatures
  - [ ] edit automation?
  - [ ] edit multiple tracks at same time
  - [ ] chord helpers
  - [ ] midi slicer with presets
  - [ ] groove templates
- [ ] automation editor
  - [ ] automation curves
  - [ ] automation steps (e.g. velocity)
- [ ] mixer strip
  - [ ] fader controls
  - [ ] pan controls
  - [ ] width controls
  - [ ] phase offset controls
  - [ ] peak/rms meters
  - [ ] routing
  - [ ] busses
  - [ ] mix groups
  - [ ] sends
  - [ ] view and select plugins and tracks
- [ ] timeline
  - [ ] display midi patterns
  - [ ] display automation
  - [ ] display waveforms
  - [ ] display chords
  - [ ] slice patterns
  - [ ] copy/loop patterns
  - [ ] grid sizes/snapping
  - [ ] time signatures
  - [ ] waveform editing
    - [ ] fade
    - [ ] reverse
    - [ ] stretch
    - [ ] pitch
- [ ] step-sequencer
  - [ ] P Steps
  - [ ] Song Mode
- [ ] pattern sequencer
- [ ] recording
  - [ ] arm/disarm track
  - [ ] record targets (audio, midi, automation)
  - [ ] loop recording
  - [ ] multi-take management
- [ ] waveform editor
  - [ ] zoom in/out
  - [ ] fade
  - [ ] slice, cut, paste
  - [ ] effects (reverse/stretch/pitch)
  - [ ] convolution effects
  - [ ] edit individual samples
  - [ ] pitch correction?
- [ ] generic plugin UI
- [ ] file browser
  - [ ] sound file browser
    - [ ] play sound file on click
    - [ ] loop/one-shot
    - [ ] volume control
    - [ ] search
    - [ ] favorites
  - [ ] plugin browser
    - [ ] browse by type
    - [ ] browse by format
    - [ ] favorites
    - [ ] search
  - [ ] preset browser
    - [ ] browse by tags
    - [ ] favorites
    - [ ] search
- [ ] settings
  - [ ] select audio devices
  - [ ] select midi devices
  - [ ] sound file sources
  - [ ] plugin file sources
  - [ ] keyboard shortcuts
  - [ ] jack settings?
- [ ] overall application design
- [ ] theming
- [ ] multi-language support

## Plugin hosting
- [ ] lv2 plugin hosting
- [ ] vst2 plugin hosting
- [ ] vst3 plugin hosting
- [ ] auv2 plugin hosting
- [ ] auv3 plugin hosting
- [ ] our own custom plugin format?
- [ ] plugin sandboxing?

## Sound file formats
- [ ] wav
- [ ] ogg
- [ ] mp3

## MIDI
- [ ] midi reader/writer
- [ ] midi2 reader/writer
- [ ] MPE support

## Essential Generators
- [ ] one-shot sampler
- [ ] test tone synth

## Essential FX
- [ ] gain & pan
- [ ] LP/BP/HP filter
- [ ] parametric EQ
- [ ] basic compressor
- [ ] basic limiter
- [ ] basic waveshaper/clipper
- [ ] basic delay unit
- [ ] stereo width adjustment tool
- [ ] multi-band splitter
- [ ] mid-side splitter
- [ ] patching plugin
- [ ] convolution plugin
- [ ] basic reverb
- [ ] delay sound by samples/time
- [ ] phase offset
- [ ] chorus
- [ ] phaser/flanger
- [ ] comb filter

## Essential MIDI FX
- [ ] LFO
- [ ] transposer
- [ ] multi-note/chords
- [ ] basic arpeggiator

## Nice-to-have Generators
- [ ] sf2/sfz multisampler
- [ ] multi-drum sampler
- [ ] basic subtractive synthesizer
- [ ] basic additive synthesizer
- [ ] basic drum synthesizer
- [ ] wavetable synthesizer
- [ ] granular synthesizer
- [ ] drum slicer

## Nice-to-have FX
- [ ] analouge-modeled EQ
- [ ] analouge-modeled compressor
- [ ] multiband compressor
- [ ] multiband distortion
- [ ] bus compressor
- [ ] look-ahead mastering limiter
- [ ] dynamic EQ
- [ ] linear-phase EQ
- [ ] tape distortion
- [ ] advanced delay unit
- [ ] pedal/guitar effects
- [ ] advanced reverb
- [ ] shimmering reverb
- [ ] vocoder
- [ ] pitch correction tool
- [ ] desser

## Misc
- [ ] undo/redo history
- [ ] project file format

## Housekeeping
- [ ] website
- [ ] example projects
- [ ] tutorials

<img src="/images/dank_meme.jpg">

[`tuix`]: https://github.com/geom3trik/tuix
[`iced`]: https://github.com/hecrj/iced
[`egui`]: https://github.com/emilk/egui
[`Rust Audio Discord`]: https://discord.com/channels/590254806208217089/590283781806620672
