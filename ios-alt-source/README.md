# Troy LC Source

A small curated source for SideStore / LiveContainer with an upstream-first bias.

## Add this source

Paste this URL into SideStore / LiveContainer:

```text
https://raw.githubusercontent.com/troyzx/scripts/master/ios-alt-source/source.json
```

## What is included

### TikTok — RXTikTok

- Source type: **official upstream IPA**
- Project source: `https://raw.githubusercontent.com/RXTikTok/rxtiktok.github.io/refs/heads/main/source.json`
- Included build: RXTikTok 1.6.6 / TikTok 43.9.0.2
- Bundle ID kept as `com.zhiliaoapp.musically`
- RXTikTok requires its own lifetime license.
- If follow/login still behaves abnormally, test the same account on TikTok Web / App Store TikTok before assuming LiveContainer is the cause.

### X — NeoFreeBird

- Source type: **official upstream sideload IPA**
- Project source: `https://raw.githubusercontent.com/orionblur/NeoFreeBird/v6/AltSource-X.json`
- Included build: NeoFreeBird 6.6.1 / X 12.21
- Bundle ID: `com.atebits.Tweetie2`
- X uses server-side attestation on some flows. Email/password login is generally more reliable than Apple/Google login in modified clients.

### YouTube — YouTubePlus / YTLite

- Source type: **community convenience build**
- Included build: YouTube 21.24.3 + YouTubePlus 5.2.2
- Convenience source: `https://raw.githubusercontent.com/mrdrvt99/Altstore-Repository/main/ytlite.json`
- Upstream tweak project: `https://github.com/dayanch96/YTLite`
- This IPA is **not an official dayanch96 binary**. The upstream YTLite project intentionally does not ship decrypted YouTube IPAs; the most trustworthy route is to build it yourself from the upstream project using your own decrypted base IPA.

## Instagram — Sparkle (manual on purpose)

Sparkle is the Instagram tweak I recommend, but it is **intentionally not placed in `source.json`**.

Reason: the developer explicitly does not publish the pre-injected Instagram IPA on GitHub. Official sideload builds are distributed only through the official Telegram channel, while the GitHub Releases page contains the tweak / jailbreak packages. Adding Sparkle to an automatic AltSource would therefore require either:

1. mirroring a proprietary Instagram IPA ourselves, or
2. trusting a third-party repack/mirror.

Both defeat the supply-chain goal of this source.

Use the official paths instead:

- Sparkle project: `https://github.com/efibalogh/sparkle-ig`
- Official IPA channel: `https://t.me/sparkle_ig`

For SideStore / LiveContainer, download the build whose filename contains `_sidestore` when offered. That variant strips app extensions and is the developer-recommended form for AltStore / SideStore / LiveContainer.

## Trust model

The source intentionally distinguishes three levels:

1. **Official upstream IPA** — preferred. Binary is released by the tweak/project maintainer.
2. **Community build from open upstream** — usable for convenience, but not equivalent to an upstream binary.
3. **Random cracked/repacked IPA** — not included.

A GitHub-hosted IPA is not automatically trustworthy. A checksum only proves that you downloaded the same file the uploader published; it does not prove the uploader added only the claimed tweak.

## LiveContainer notes

- Guest apps do not each consume a free developer app slot.
- Keep original bundle IDs when possible, especially TikTok and X.
- Modified clients can still be rejected by server-side anti-abuse / attestation even when signing and LiveContainer are working correctly.
- Treat apps that receive account passwords/session tokens as higher-risk than apps that only consume public data.

## Update policy

Prefer upstream source metadata when an official source exists. Do not silently replace an official build with a third-party mirror. If a project stops publishing a directly installable IPA, keep the entry pinned or remove it rather than substituting an opaque repack.
