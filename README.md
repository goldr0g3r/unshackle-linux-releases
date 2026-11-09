# Unshackle for Linux: releases

Signed packages of **Unshackle for Linux**, a porn blocker for Linux desktops that doesn't
get in the way of development work. It forces filtered DNS for every app, manages Chrome,
Brave and Firefox, and blocks every other browser, including Flatpak and Snap ones.
Loosening a protection waits for a cooldown; tightening applies at once. There is always a
way out: a cooldown Full Release, or a recovery code held by a trusted person.

This repository only hosts release files; see [Releases](../../releases). Each release has:

| File | What it is |
|---|---|
| `unshackle_X.Y.Z-1_amd64.deb` | Package for Debian, Ubuntu and derivatives |
| `unshackle-X.Y.Z-1.x86_64.rpm` | Package for Fedora, openSUSE and derivatives |
| `unshackle-X.Y.Z-1-x86_64.pkg.tar.zst` | Package for Arch and derivatives |
| `unshackle-X.Y.Z-x86_64.tar.gz` | The static binaries and units, used by the AUR package |
| `SHA256SUMS` | Checksums of the files above |
| `manifest.json` | Version, files and checksums, read by the updater |
| `PKGBUILD` | The AUR package's build file |
| `*.minisig` | A minisign signature for each file |

## Verify before installing

Every release is signed with the same minisign key:

```
untrusted comment: minisign public key F3B6493C9DCF3CCA
RWTKPM+dPEm280Mpwu8HRJb/8sGrFmxGg+zn9B3s0LZ87TsJZn6vvu+Z
```

Check a download against it before installing, and don't install a package whose signature
doesn't verify, whoever sent it:

```bash
minisign -Vm <package> -P RWTKPM+dPEm280Mpwu8HRJb/8sGrFmxGg+zn9B3s0LZ87TsJZn6vvu+Z
```

Each release's notes repeat it, and installed copies pin it for updates.

Pre-releases (`-rc.N`) are for testing.
