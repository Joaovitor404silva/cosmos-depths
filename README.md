# Cosmos Depths: free co-op roguelike in your browser

**Play now: https://joaovitor404silva.github.io/cosmos-depths/**

Cosmos Depths is a small co-op ASCII dungeon crawler for 1 to 4 players. Host a
run and send the join code to friends, or open a public run that shows up in
the lobby list. Fight down through the depths together. Notes you write and
graves you leave stay in the dungeon for other players' runs, and you can see
the ghosts of players in other runs at the same depth.

No account, no download, no game server.

## How the multiplayer works

- **Meeting:** players find each other through public
  [Nostr](https://nostr.com) relays. A join code never leaves your browser
  as is: runs are listed under a key derived from the code (Argon2id), and
  the advert is encrypted with it.
- **Playing:** game traffic goes straight between browsers over WebRTC
  data channels. The host decides who is in the run.
- **Persistence:** notes, graves, ghosts and public runs are short-lived
  signed records on the same relays, and they expire on their own.

Most home networks connect fine. On very strict networks (some mobile
carriers, offices) two players may not be able to reach each other, because
there is no relay server to fall back on.

## Controls

| Key | Action |
| --- | --- |
| H / P | host a private / public run |
| L | lobby list of public runs |
| J | join with a code |
| arrows or WASD | move, bump to attack |
| Q E Z C | diagonals |
| Space | descend on `>` |
| N | write a note for later runs |
| Esc | leave |

You need a desktop browser and a keyboard. Tested in Chromium-based browsers (Chrome, Edge, Brave).

## About

The game is written in C with [raylib](https://www.raylib.com) and compiled
to WebAssembly with Emscripten. Its networking is a browser build of a
serverless multiplayer SDK, [The Cosmos](https://github.com/Joaovitor404silva/the-cosmos)
(WebRTC + Nostr in the browser). Game and SDK source, MIT licensed:
[the-cosmos/examples/cosmos-depths](https://github.com/Joaovitor404silva/the-cosmos/tree/master/examples/cosmos-depths).
This repository only holds the built site served by GitHub Pages.
Third-party licences: [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt).
