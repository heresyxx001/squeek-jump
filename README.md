# Squeek Jump

A one-button sunset-beach jumping game powered by the live Squeekchain hamster wheel.

## How to play

Tap the screen, press Space, or hit JUMP to jump. Jump over rocks, crabs, and driftwood coming from the right. One hit ends the run. Your score is the distance you survive. The best score for your current mode is shown for the browser session only.

## The hamster

The runner is an original flat hamster character with a running animation and a clear jump pose. It is not copied from any existing Squeek NFT art.

## Live connection to Squeekchain

The game polls the public Squeekchain status API in your browser every 2 seconds:

`https://api.squeekchain.com/v1/status`

It reads `measurement.rpmMilli` (converted to RPM), `coreStatus`, and `freshness`. Obstacle speed follows the live wheel RPM: the faster the hamster runs on the wheel, the faster the obstacles come.

If the feed is unreachable, or `freshness` is not `online`, the game shows FEED DOWN, START is disabled, and an active run pauses. No live data is ever faked.

SIM MODE is available for practice only. It is always clearly labeled "SIMULATED — NOT LIVE" and uses a simulated wheel, never presented as live.

## Wallet and guest

On the start screen you can Connect Wallet or Play as Guest.

- **Connect Wallet** uses `window.ethereum` (EIP-1193) read-only. It only reads your wallet address, shows it truncated (first 6 + last 4 characters), and offers Disconnect. It never asks for a signature, never sends a transaction, and never stores keys.
- If no wallet is installed, the game says so clearly and offers Play as Guest instead.
- **Play as Guest** starts immediately and is labeled GUEST. The mode you chose (your truncated address or GUEST) is shown on the game screen and on the game-over screen.

The in-game wallet sign-in is only for playing. It is separate from project ownership on Genesis.

## Theme

Sunset beach: blue-orange sky, sun, sea, and sand. No palm trees. The background is kept clean so the hamster and obstacles stay easy to read.

## How to run it

This is a single self-contained `index.html` file. There is no backend, database, build step, or npm. Google Fonts is the only external dependency.

- Open `index.html` in a browser, or
- Host it as a static page (for example GitHub Pages) and open the live URL.
