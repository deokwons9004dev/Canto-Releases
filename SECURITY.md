# Security policy

## Supported versions

| Version | Security fixes |
| --- | --- |
| 1.0 beta (the latest pre-release) | Yes |
| 0.10.3 | Yes |
| Older versions | No. Please update. |

## Reporting a vulnerability

Please don't open a public issue. Email **support@lonelyduck.io** with "Security" in the subject, and include:

- the Canto version (Settings › About) and your macOS version
- what you found and the steps to reproduce it
- whether it needs physical access to the Mac, another app on the Mac, or nothing at all

I'm a solo developer. I'll reply within 3 business days, keep you updated until it's fixed, and credit you in the release notes if you'd like.

## Verifying a download

Every release is signed with my Apple Developer ID (Team ID `RD9TC9MV83`) and notarized by Apple. To check a copy:

```sh
codesign --verify --deep --strict --verbose=2 /Applications/Canto.app
spctl --assess --type execute --verbose /Applications/Canto.app
```

The second command should say `source=Notarized Developer ID` and name Team ID `RD9TC9MV83`.

In-app updates come only from this repository's releases. The updater checks each download against the SHA-512 in the release's `latest-mac.yml` (`beta-mac.yml` for betas), and macOS refuses an update that isn't signed by the same developer.

## What Canto sends off your Mac

Settings › Memory & privacy › What leaves this Mac lists every feature that can send anything, what it sends and where, each with its own switch. The privacy policy is at https://lonelyduck.io/legal/privacy.
