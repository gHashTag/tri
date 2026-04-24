# tricli — Unified CLI for trios-server + Tailscale Funnel

One command to make your trios-server accessible from anywhere.

## Installation

```bash
git clone https://github.com/gHashTag/tri.git
cd tri
cargo install --path .
```

## Usage

```bash
# Start Funnel
tricli start

# Show status
tricli status

# Stop Funnel
tricli stop

# Open dashboard in browser
tricli open
```

## Requirements

- Tailscale installed from [App Store](https://apps.apple.com/app/tailscale/id1475387142)
- Tailscale logged in and connected

## Example

```bash
$ tricli start

╔═══════════════════════════════════════════════════════════════╗
║     tri                    ║
║     trios-server + Tailscale Funnel        ║
╚═══════════════════════════════════════════════════════════════╝

✅ Funnel started successfully!

┌─────────────────────────────────────────────────────────────┐
│  STATUS                    │
├─────────────────────────────────────────────────────────────┤
│  Device:  playra's MacBook Pro                             │
│  Funnel:  ACTIVE ✅                                         │
│  URL:     playras-macbook-pro-1.tail01804b.ts.net:443      │
└─────────────────────────────────────────────────────────────┘

🌐 Your trios-server is accessible at: https://playras-macbook-pro-1.tail01804b.ts.net:443/
🌐 Health check: https://playras-macbook-pro-1.tail01804b.ts.net:443/health
🌐 API status: https://playras-macbook-pro-1.tail01804b.ts.net:443/api/status
```

## Testing

All tests passed: 9/9 ✅

See [TESTING.md](TESTING.md) for details.

## License

MIT
