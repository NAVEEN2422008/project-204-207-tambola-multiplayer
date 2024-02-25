# PRO-C204-C207 - Tambola (Housie) Multiplayer Game

A multiplayer Tambola/Housie family-fun game with a Tkinter client and a threaded Python socket server.

## Features

- **Server** broadcasts random numbers (1–90) to all connected players every 3 seconds
- **Client** draws a randomized 3×9 ticket, flashes the broadcast number, and lets the player mark numbers
- **Win detection** — full row + all flash numbers called = "wins the game" (broadcast to everyone)
- **Lose detection** — all ticket numbers marked but wrong = game over
- Wrong-marking feedback disables not-yet-called numbers in pink
- Cross-platform UI handling for macOS (`tkmacosx`) and Windows

## Tech Stack

- **Python 3** — `socket`, `threading`, `random`
- **Tkinter** + **PIL/Pillow** for the GUI
- **tkmacosx** button support on macOS

## Project Structure

```
C204-C207/
├── server.py   # Number broadcaster, client handling, game-over logic
├── client.py   # Ticket UI, number marking, win/lose detection
└── assets/     # background.png game artwork
```

## Installation

1. Clone the repository.
2. Install dependencies:

```bash
pip install pillow tkmacosx   # tkmacosx needed on macOS only
```

## Usage

### Start the server

```bash
cd C204-C207
python server.py
```

### Start clients (at least 2)

```bash
python client.py
```

1. Enter a player name and save.
2. Mark numbers on your ticket as they are flashed.
3. Complete your ticket correctly with all flashed numbers to win; the winner's message appears on every client.
