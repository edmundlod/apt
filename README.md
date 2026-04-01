# edmundlod apt repository

Personal apt repository for Debian/Ubuntu packages maintained by Edmund Lodewijks.

## Packages

| Package | Description |
|---|---|
| `postallow` | Postfix Postscreen allowlist and blocklist generator from SPF records |
| `spf-tools` | Tools for querying and flattening SPF DNS records |
| `route-summarization` | IP route summarization and CIDR aggregation tool (`aggregateCIDR.pl`) |

## Installation

### 1. Add the signing key

```bash
sudo mkdir -p /usr/share/keyrings
curl -fsSL https://edmundlod.github.io/apt/key.asc \
  | sudo tee /usr/share/keyrings/edmundlod-apt.asc > /dev/null
```

### 2. Add the repository

```bash
echo "deb [signed-by=/usr/share/keyrings/edmundlod-apt.asc] \
https://edmundlod.github.io/apt trixie main" \
  | sudo tee /etc/apt/sources.list.d/edmundlod.list
```

### 3. Install

```bash
sudo apt update
sudo apt install postallow
```

`postallow` depends on `spf-tools` and `route-summarization` — both are pulled in automatically.

## Supported distributions

Currently targets **Debian 13 (trixie)**. All packages are `Architecture: all`
(pure shell/Perl scripts) and will work on any amd64 Debian or Ubuntu system
with a compatible libc.

## Signing key

Key ID: `E75C78A28F60F730`  
Fingerprint: `9FF4 1A44 270A 1D88 226E 50F3 E75C 78A2 8F60 F730`  
Expires: 2027-01-31

The key is renewed annually. When it expires, download the new key using the
same URL and re-run step 1.

## Source repositories

- [postallow](https://github.com/edmundlod/postallow)
- [spf-tools](https://github.com/edmundlod/spf-tools)
- [route-summarization](https://github.com/edmundlod/route-summarization)
