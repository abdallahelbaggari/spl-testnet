# SPL Testnet

Testnet (Pi sandbox) copy of **SPL** — live football scores for Pi Network.
Mainnet lives in a separate repo (`abdallahelbaggari/spl`) and a separate Cloudflare project.

- `PI_SANDBOX: true` in `index.html` — all Pi sign-in and payments use **test-Pi**.
- Amber "Pi Testnet" badge and stripe so it is never confused with the real app.
- Same features and file layout as mainnet SPL.

## Cloudflare Pages project (testnet)

- Connect this repo, branch `main`. Build command: *(empty)*. Build output directory: `.`
- Secrets / variables:
  - `PI_API_KEY` — API key of the **testnet** app in develop.pi
  - `FD_API_KEY` (or `FOOTBALL_DATA_KEY`) — football-data.org token
  - Optional: KV binding `SPL_CACHE`
- Leave out `API_FOOTBALL_KEY` unless you use a separate API-Football account — the same key
  on mainnet and testnet shares one 100 requests/day allowance.

## Pi (develop.pi, testnet app)

- App URL = this project's pages.dev address.
- Domain validation: add the testnet app's key as the Cloudflare variable `PI_VALIDATION_KEY` (or put `validation-key.txt` at the top level of this repo).
- Open `/launch-check` on the testnet site to see what is still missing.
- Test flow: My Football → Sign in with Pi → Support SPL → 1 π (test-Pi).
  Logs: Cloudflare → Functions → Real-time Logs (`SPL-PI` lines).

## Endpoints

`/api/*` football data · `/approve` · `/complete` · `/cancel-payment` · `/verify-user`
