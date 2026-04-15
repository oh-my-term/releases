# Oh My Term — Binary Releases

Official binary releases for [Oh My Term](https://github.com/oh-my-term) components.

## Why download from here?

In a zero-trust architecture, the Oh My Term server (omts) is treated as an **untrusted relay**. Downloading omtc from the server would allow a compromised server to serve a backdoored binary. This repo provides:

- **Auditable releases**: all binaries are built from tagged commits and published here
- **SHA-256 checksums**: every release includes `checksums.sha256` for verification
- **Public visibility**: anyone can inspect release history and checksums

## Verification

After downloading, verify the checksum:

```bash
# Download binary and checksum
curl -fsSL -o omtc https://github.com/oh-my-term/releases/releases/download/v2.1.6/omtc-linux-amd64
curl -fsSL -o checksums.sha256 https://github.com/oh-my-term/releases/releases/download/v2.1.6/checksums.sha256

# Verify
sha256sum -c checksums.sha256 --ignore-missing
```

## Available Binaries

Each release includes:

| Binary | Platform |
|--------|----------|
| `omtc-linux-amd64` | Linux x86_64 |
| `omtc-linux-arm64` | Linux aarch64 |
| `omtc-darwin-amd64` | macOS x86_64 |
| `omtc-darwin-arm64` | macOS Apple Silicon |
| `omts-linux-amd64` | Server, Linux x86_64 |
| `checksums.sha256` | SHA-256 checksums for all binaries |

## Install Script

The install script (`GET https://server/i/sh`) downloads omtc from **this GitHub repo**, not from the server. The server only provides the script itself — the binary comes from a trusted, auditable source.
