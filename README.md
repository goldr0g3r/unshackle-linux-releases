# Unshackle for Linux: releases

Signed packages of **Unshackle for Linux**, a porn blocker for Linux desktops that doesn't
get in the way of development work. It forces filtered DNS for every app, manages Chrome,
Brave and Firefox, and blocks every other browser, including Flatpak and Snap ones.
Loosening a protection waits for a cooldown; tightening applies at once. There is always a
way out: a cooldown Full Release, or a recovery code held by a trusted person.

This repository only hosts release files. There are no releases yet. Each release will have:

| File | What it is |
|---|---|
| `unshackle_X.Y.Z_amd64.deb` | Package for Debian, Ubuntu and derivatives |
| `unshackle-X.Y.Z.x86_64.rpm` | Package for Fedora, openSUSE and derivatives |
| `unshackle-X.Y.Z-1-x86_64.pkg.tar.zst` | Package for Arch and derivatives |
| `*.sha256`, `*.minisig` | Checksums and minisign signatures |
| `manifest.json` | Version, files and checksums, read by the updater |

## Verify before installing

Every release is signed with the same minisign key. Its public key will be published here
with the first release. Don't install a package whose signature doesn't verify against it,
whoever sent it.

```bash
minisign -Vm <package> -P <public key>
```

Pre-releases (`-rc.N`) are for testing.
