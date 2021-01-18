# 0.1.0: Multi-track Audio Editor (High-level design doc)

## Objective

To get the RustyDAW project started, we need some goal to work towards. Ideally this is something simple enough for us to get started on quickly, but complex enough that we lay some substantial foundation for us to work towards a "full-featured" DAW afterwards.

One popular idea in the Discord was to create a **multi-track audio editor**, similar to something like Audacity. This fits the above-stated goal decently:

 - We have to worry about audio thread / GUI thread interaction, which all other DAWs have to do in some capacity.
 - Multiple-track functionality is a common, basic requirement for pretty much all DAWs. Work done here can be re-used and/or extended for use in other DAWs.
 - Multiple-track functionality is enough of a challenge that some decent amount of design work is required:
    - What is the scope of a "track"?
    - How do clips work?
    - How do we "schedule" clips for playback?

This editor will work with audio clips *only*, which leaves some obvious holes in functionality compared to what most people think of as a "DAW". While designing this phase, we should be careful not to paint ourselves into a corner: we should make it easy to extend our design to support more features you'd find in a typical DAW (instrument/effect devices and piano roll editing being an obvious one).

## Scope

### Goals

The ultimate goal is to have a multi-track audio editor (similar to something like Audacity), obviously. In more detail:

**Functionality overview**

 - All functionality works on all target systems (Windows, Mac OS, Linux)
 - Program only works with audio. No MIDI/piano roll clips.
 - Program handles WAV audio clips, assumed to be in the correct sampling rate. Resampling audio to import them into the program is not necessary yet.
 - Ability to have multiple tracks.
 - Ability to have multiple audio clips per track.
 - Ability to move clips around in time, and between tracks.
 - Playback causes audio output to occur, "as expected" (depends on clip content and location in time, mixed to a "master" output channel dependent on each track's volume, etc.)
 - During playback, visual feedback matches audio output state.

**GUI**

 - Program displays a GUI that the user can interact with.
 - GUI includes a basic transport control widget (play/pause/stop, current playback time, master volume, ...)
 - GUI includes a "track lane" view, which depicts multiple different "tracks" of audio clips.
 - GUI allows user to insert new audio clips (for example, maybe by dragging/dropping audio files into the editor).
 - GUI allows the user to move clips around in time (horizontally), and between different tracks (vertically).
 - GUI allows the user to copy/paste clips.
 - GUI allows the user to delete clips.
 - GUI allows the user to create a new track, delete a track, and move tracks around.
 - When the user starts playback (presses the "play" button), playback starts. Visual indication (such as a playhead moving horizontally through time across all tracks, for example) shows the user where the current position of playback is in the project.
 - When the user stops playback (presses the "stop" button), playback stops. Visual indication resets to time zero.
 - When the user pauses playback (presses the "pause" button), playback pauses. Visual indication does *not* reset. If user unpauses, playback is resumed from the position the pause happens.
 - User can control each track's volume independently, affecting the mixing of these tracks.
 - [stretch goal] User can set where the playback should start from, instead of always starting from time zero. Stopping playback will reset to this point instead of zero. Double-clicking the "stop" button will reset this time to zero (?).
 - [stretch goal] GUI support for muting/soloing tracks
 - [stretch goal] Stylizing tracks (user-selected colors? differentiation between mute/solo'd tracks and regular tracks?)

**Audio engine**

 - Audio clips (and their contents) are output at the correct time.
 - During playback, tracks are mixed together based on each track's volume.
 - When playback is stopped or paused, audio is no longer played. Playing/unpausing resumes playback at the correct time (described above).

**Miscellaneous**

 - Remember that we want to design things modularly, where possible. What can we split into a new crate?

### Non-goals

In order to reign in the scope of this first project, we're going to *explicitly* not support certain functionality that you'll find in most other DAWs. Again, we should be careful to **think about** these things when designing our first project so that we can implement them in the future, but we don't want to scope-creep ourselves too hard for this first project.

 - No MIDI / piano roll support. All clips are audio only.
 - Relatedly, all tracks are "audio" tracks. No need to support instrument tracks, group tracks, FX/send tracks, etc.
 - No instrument/effect devices.
 - No parameters, no automation.
 - All clips (tracks?) are either stereo or mono. We want to be able to support channel configurations eventually, but doing so right now might be too much scope creep.

### Undetermined

There are still a few bits of functionality to consider for this first iteration:

 - Saving a project (serializing/deserializing project state to/from a file)
 - Exporting a project to WAV
 - Can users "chop up" audio clips? Delete a portion of the audio clip instead of the entire clip? Copy just a portion to paste that portion elsewhere? etc.
 - Panning on tracks
 - Keyboard shortcuts
 - GUI menus

## Design overview

**(SECTION TODO -- wireframes for GUI, overview of the GUI/Audio engine interaction, overview of how the audio engine works, etc.)**

## Detailed designs

**(SECTION TODO -- new documents describing exactly how we're going to implement various things described throughout the document, linked here)**

## Future work

After this project is completed, there are some obvious things we can work on to move forward towards a "feature-complete" DAW:

 - Device support (instrument devices, effect devices, device chains, etc)
    - Piano roll / MIDI controls
    - Parameter automation
    - New track and clip types
 - Placing clips in beat-time, not seconds/samples
 - More complex audio channel configurations (beyond just stereo and mono)
