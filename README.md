# Briscola Chiamata — 5-player online

A real-time, private-room browser game for five people. Server-authoritative hands and trick resolution, public called card, secret partner revealed when played, no cumulative scoring.

## Run locally
1. Install Node.js 18 or newer.
2. Run `npm install` in this folder.
3. Run `npm start`.
4. Open http://localhost:3000.

## Put it online
Push the folder to a GitHub repository. Create a new **Web Service** on a Node.js hosting service such as Render, using `npm install` as the build command and `npm start` as the start command. Use a hosting plan that supports persistent WebSocket connections. Share the generated HTTPS URL with your friends. Only one server instance should be running, since rooms live in memory.

## House rules
- Five players, 40 Italian-suit cards, eight per player.
- Dealer rotates each hand. Player to dealer's right (next seat in counter-clockwise seating order) automatically bids 60. Others may raise in whole points or pass; a pass is final.
- Caller freely chooses Brisk suit. Called card is automatically the highest-ranked card of that suit not in caller's hand. The called card is visible to all; its holder is the secret teammate.
- No solo calls. No follow-suit requirement. Winner is highest trump, otherwise highest card of lead suit.
- Caller + teammate must score at least their bid. No match scoreboard.

## Current limitations
- If a player disconnects mid-hand, the room waits; there is no reconnection token or bot takeover. Restart the room to continue.
- Rooms are not stored in a database and reset when the server restarts.
- No authentication, public matchmaking, or anti-collusion measures.
