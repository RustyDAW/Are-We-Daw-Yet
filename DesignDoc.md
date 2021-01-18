# RustyDAW

RustyDAW is a collection of tools for creating Digital Audio Workstations (DAWs).

RustyDAW is a community-driven project. If you are interested in participating, feel free to join the [RustAudio Discord](https://discord.com/invite/8rPCp9Q), channels `#rusty-daw` and `#rusty-daw-gui`.

## Objective

*TL;DR: we want a solid, open-source, more-modular audio ecosystem, and we think Rust enables us to provide it.*

We believe the current state of audio software development is slow and bogged down by old technology, and the standards too closed. A DAW is a unique project: it's a large and complex one, but if successful, it can drive change for many different technologies and define new standards. It's important for this work to be done **in the open** to avoid the mistakes of other technologies/standards, and to accelerate the pace of innovation.

Why not contribute to an open-source DAW that already exists? We believe that the current state of open-source DAWs is lacking:
 - DAWs are inherently complex. Many different concepts must be taken into account simultaneously, and work together.
 - Existing DAWs rely on older technologies and standards, such as C++. While fine for the task of writing audio software, C++ makes it trickier to create a maintainable codebase (cross-platform support, ease of writing modular code, etc.).
 - People have different tastes in workflow, but having a monolithic DAW architecture locks projects into a specific use-case. With a **more modular** design, developers can more easily swap out components/libraries to suit the needs of *their* particular use-case, and a whole ecosystem of DAWs with different workflows can be acheived.

We believe Rust to be the perfect language for this project because of its design philosophy:
 - No garbage collection, so still (more easily) audio-safe
 - Cross-platform by default: works on Windows, Mac OS, and Linux, across multiple different CPU architectures, without much compilation fuss
 - The modules and crates system makes it easy to split your code into distinct modular components, and `cargo` handles all of the compilation for you
 - Rust's safety guarantees will significantly reduce the occurrence of DAWs crashing

## Implementation plan

We're going to break this massive "full-featured" DAW project into smaller projects so it's easier to work on.

 - v0.1.0: [Multi-track Audio Editor](0-1-0_MultitrackAudioEditor/)
