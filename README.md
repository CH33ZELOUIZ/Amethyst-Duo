# Amethyst Duo

A fork of [Taylen27/Amethyst-iOS](https://github.com/Taylen27/Amethyst-iOS) (itself forked from [AngelAuraMC/Amethyst-iOS](https://github.com/AngelAuraMC/Amethyst-iOS)) with iPhone Duo fold-aware layout and offline modpack import.

## Features

This fork adds:

1. **iPhone Duo fold-aware layout** - Game renders on the top half, touch controls on the bottom half when the device is half-folded horizontally. Fully open = fullscreen game.
2. **Offline modpack import** - Import Modrinth modpacks or CurseForge modpacks (with your own API key) from local ZIP files, plus direct client ZIP import.
3. **Virtual touch-mouse filtering** - iOS 27+ exposes the touchscreen as a virtual GCMouse; this fork filters it so touch controls remain visible.

Base: Taylen27's archived fork, which bundles LWJGL 3.4.x + SDL3 + Java 25 (required for Minecraft 1.26.x/NeoForge 27.x).

**Note:** This is a manual build from the donor branch. Full playability has not been independently verified.

## Installation

### Via AltStore/SideStore

Add this source URL to AltStore or SideStore:

```
https://raw.githubusercontent.com/CH33ZELOUIZ/Amethyst-Duo/main/altstore/source.json
```

Or download the latest IPA directly from [Releases](https://github.com/CH33ZELOUIZ/Amethyst-Duo/releases).

### Requirements

- **iPhone Duo** running iOS 27.1+ (for fold support)
- Or any supported iPhone/iPad on iOS 14.0+ (fold features disabled, rest works)
- SideStore/AltStore for signing, or TrollStore for permanent install
- JIT enabled (via StikDebug, AltStore, TrollStore, or jailbreak)

## Building from Source

Manual build only. Requires macOS with Xcode 27.1+ for the iOS 27.1 SDK (iPhone Duo APIs). No CI workflow is configured yet.

```bash
# Local build on macOS:
brew install cmake ldid wget make
export PATH="$(brew --prefix)/opt/make/libexec/gnubin:$PATH"
gmake -j$(sysctl -n hw.ncpu) package PLATFORM=2 BOOTJDK=/path/to/zulu-8-aarch64/bin
```

The build produces `artifacts/*.ipa` (unsigned; sign with ldid or AltStore/SideStore).

## Credits

- **AngelAuraMC** - Original Amethyst iOS project
- **Taylen27** - LWJGL 3.4.x + SDL3 + Java 25 integration
- **CH33ZE** - Duo layout, offline modpack import, and this fork

Amethyst is based on [Boardwalk](https://github.com/zhuowei/Boardwalk) by zhuowei.

## License

GPLv3 - see [LICENSE](LICENSE)
