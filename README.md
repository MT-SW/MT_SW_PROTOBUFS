# MT_SW Protobufs

Fork of [meshtastic/protobufs](https://github.com/meshtastic/protobufs) maintained for the
**MT-SW (Świętokrzyskie)** Meshtastic mesh network project.

## 🇵🇱 Polski

Fork [meshtastic/protobufs](https://github.com/meshtastic/protobufs) utrzymywany na
potrzeby sieci mesh **MT-SW (Świętokrzyskie)**.

To repozytorium jest źródłem definicji protobuf współdzielonych między naszym forkiem
firmware a forkiem aplikacji Android/desktop — dołączane jako submoduł git (nanopb, C++)
w firmware, oraz jako pakiet Kotlin Multiplatform (Wire) budowany lokalnie dla aplikacji.

### Czym różni się od oryginału
Dodaje własne rozszerzenia protokołu ponad oficjalny schemat Meshtastic (obecnie: protokół
diagnostyczny OnDemand oraz konfiguracja trybu Sniffer). Szczegóły w historii commitów —
poza tym fork stara się być zsynchronizowany z upstreamowym `meshtastic/protobufs`.

### Użycie
- **Firmware:** dołączane jako submoduł git; po aktualizacji uruchom `bin/regen-protos.sh`
  w repo firmware.
- **Aplikacja Android/Desktop:** zbuduj pakiet KMP lokalnie —
  `packages/kmp/gradlew -p packages/kmp publishToMavenLocal -PVERSION_NAME=x.y.z` — i użyj
  go przez `mavenLocal()`.

---

## 🇬🇧 English

This repository is the single source of truth for protobuf message definitions shared
between our firmware fork and our Android/desktop app fork — consumed as a git submodule
(nanopb, C++) by firmware, and as a Kotlin Multiplatform package (Wire) built locally for
the app.

### What's different from upstream
Adds our own protocol extensions on top of the official Meshtastic schema (currently: an
OnDemand diagnostics/query protocol, and Sniffer mode configuration). See commit history
for specifics — otherwise this fork tracks upstream `meshtastic/protobufs` and should be
kept in sync periodically.

### Usage
- **Firmware:** referenced as a git submodule; after updating it, regenerate with
  `bin/regen-protos.sh` in the firmware repo.
- **Android/Desktop app:** build the KMP package locally —
  `packages/kmp/gradlew -p packages/kmp publishToMavenLocal -PVERSION_NAME=x.y.z` — and
  consume it via `mavenLocal()`.