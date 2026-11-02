# Multiplayer Pong

A real-time two-player Pong game built in C++ using SFML.

The game uses an authoritative client-server architecture, with TCP for connection setup and UDP for real-time game data. Clients use basic client-side prediction to reduce perceived input delay.

## Demo

[![Watch the multiplayer Pong demo](https://img.youtube.com/vi/p5ujrTgAWlM/maxresdefault.jpg)](https://www.youtube.com/watch?v=p5ujrTgAWlM)

The video demonstrates normal operation, latency, throttling, duplicate and out-of-order packets, bandwidth limiting, packet tampering and multiple combined conditions.

## Network testing

The application was tested using Clumsy. It remained playable at 150 ms latency, while 20% packet loss had little gameplay impact. Client-side prediction reduced input delay, although server corrections caused visible paddle jitter under latency.

## Running the application

1. Download `Pong-Multiplayer-Windows.zip` from the [latest release](https://github.com/EmilAlmazov/Pong-Multiplayer/releases/latest).
2. Extract all files into one folder.
2. Start `Server.exe` and wait for its terminal window to open.
3. Start `Client.exe` twice.
4. Two windows should open: `Pong Multiplayer: Client 0` and `Pong Multiplayer: Client 1`.

### Controls

- Client 0: `W` and `S`
- Client 1: Up and Down arrow keys

## Building from source

Requirements:

- CMake 3.26 or newer
- C++17 compiler
- SFML 2.6.x, downloaded automatically by CMake

```sh
cmake -B build
cmake --build build --config Release
```

The application has been tested on Windows 10. Run the generated `Server` executable first, followed by two instances of `Client`.

The CMake setup was based on the [SFML CMake tutorial](https://www.sfml-dev.org/tutorials/2.6/start-cmake.php).
