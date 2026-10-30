# MT_SW Protobufs

> ⏸️ **Projekt wstrzymany / Project on hold**
>
> Nie rozwijamy już tego repozytorium. Projekty MT_SW korzystają z oficjalnych definicji [meshtastic/protobufs](https://github.com/meshtastic/protobufs). Repozytorium zostaje jako archiwum i może być nieaktualne względem oryginału.
>
> This repository is no longer developed. MT_SW projects use the official [meshtastic/protobufs](https://github.com/meshtastic/protobufs). It stays as an archive and may be out of date compared with the original.

---

## 🇵🇱 Polski

Fork [meshtastic/protobufs](https://github.com/meshtastic/protobufs) utrzymywany dawniej na
potrzeby sieci mesh **MT-SW (Świętokrzyskie)**.

### Status

**Projekt wstrzymany.** Repozytorium nie jest już rozwijane ani synchronizowane z oryginałem. Nasze projekty (MT_SW_APP, MT_SW_FIRMWARE, MT_SW_INTEGRATION) korzystają z oficjalnych protobufów [meshtastic/protobufs](https://github.com/meshtastic/protobufs). Jeśli potrzebujesz aktualnych definicji, użyj oryginału.

### Do czego służyło

To repozytorium było źródłem definicji protobuf współdzielonych między naszym forkiem
firmware a forkiem aplikacji Android/desktop — dołączane jako submoduł git (nanopb, C++)
w firmware, oraz jako pakiet Kotlin Multiplatform (Wire) budowany lokalnie dla aplikacji.

### Czym różni się od oryginału
Dodaje własne rozszerzenia protokołu ponad oficjalny schemat Meshtastic (protokół
diagnostyczny OnDemand oraz konfiguracja trybu Sniffer). Szczegóły w historii commitów.

### Użycie (dla archiwum)
- **Firmware:** dołączane jako submoduł git; po aktualizacji uruchom `bin/regen-protos.sh`
  w repo firmware.
- **Aplikacja Android/Desktop:** zbuduj pakiet KMP lokalnie —
  `packages/kmp/gradlew -p packages/kmp publishToMavenLocal -PVERSION_NAME=x.y.z` — i użyj
  go przez `mavenLocal()`.

### Metadane pól

Pola mogą nieść metadane istotne dla aplikacji/UI (np. `diy_only`) przez opcje `meshtastic.field_metadata` — zobacz [`meshtastic/field_metadata.proto`](meshtastic/field_metadata.proto). Są udostępniane jako generowane akcesory bez refleksji: pakiet KMP generuje je przez Wire `SchemaHandler` ([`packages/kmp`](packages/kmp/README.md)), a inne języki przez wtyczkę [`tools/protoc-gen-fieldmeta`](tools/protoc-gen-fieldmeta/README.md) (ma gotowe przepisy integracji dla firmware/Apple/Python).

### Licencja, nazwa i cudze treści

Kod jest otwarty — możesz go używać, zmieniać i udostępniać dalej na zasadach licencji repozytorium (szczegóły w pliku LICENSE). Prosimy o dobre praktyki:

- zmienioną lub cudzą wersję nazwij inaczej i zaznacz, że nie pochodzi od nas;
- nie przedstawiaj swojego produktu, strony ani grupy jako oficjalnego projektu MT_SW, jeśli nim nie jest;
- nasze teksty i dokumentację możesz cytować z podaniem autora i źródła;
- jeśli chcesz napisać o projekcie lub sieci, odezwij się do nas wcześniej — pomożemy sprawdzić fakty; prosimy nie publikować prywatnych danych osób tworzących projekt.

Nie odpowiadamy za informacje, artykuły, filmy, strony ani wypowiedzi osób i podmiotów trzecich, w tym za błędne, nieaktualne lub niezwiązane z nami fakty. Odcinamy się od stron, struktur, grup i osób, które piszą lub mówią o nas bez kontaktu z nami i bez udziału w naszej społeczności i sieci. Rzetelne informacje o projekcie są w naszych własnych kanałach i repozytoriach (GitHub MT-SW, mt-sw.pl). Pytania: przez nasze kanały (lokalne grupy, Discord/WhatsApp/Signal, sieć mesh).

Projekt nie jest afiliowany ani wspierany przez Meshtastic LLC. Meshtastic® jest zarejestrowanym znakiem towarowym Meshtastic LLC. Korzystasz na własne ryzyko, bez żadnej gwarancji.

---

## 🇬🇧 English

A fork of [meshtastic/protobufs](https://github.com/meshtastic/protobufs) formerly maintained
for the **MT-SW (Świętokrzyskie)** mesh network project.

### Status

**Project on hold.** This repository is no longer developed or synchronised with upstream. Our projects (MT_SW_APP, MT_SW_FIRMWARE, MT_SW_INTEGRATION) use the official [meshtastic/protobufs](https://github.com/meshtastic/protobufs). If you need current definitions, use the original.

### What it was for

This repository was the single source of truth for protobuf message definitions shared
between our firmware fork and our Android/desktop app fork — consumed as a git submodule
(nanopb, C++) by firmware, and as a Kotlin Multiplatform package (Wire) built locally for
the app.

### What's different from upstream
Adds our own protocol extensions on top of the official Meshtastic schema (an
OnDemand diagnostics/query protocol and Sniffer mode configuration). See commit history
for specifics.

### Usage (for the archive)
- **Firmware:** referenced as a git submodule; after updating it, regenerate with
  `bin/regen-protos.sh` in the firmware repo.
- **Android/Desktop app:** build the KMP package locally —
  `packages/kmp/gradlew -p packages/kmp publishToMavenLocal -PVERSION_NAME=x.y.z` — and
  consume it via `mavenLocal()`.

### Field metadata

Fields can carry app/UI-relevant metadata (e.g. `diy_only`) via the `meshtastic.field_metadata` option — see [`meshtastic/field_metadata.proto`](meshtastic/field_metadata.proto). It is exposed to consumers as reflection-free generated accessors: the KMP package generates them with a Wire `SchemaHandler` ([`packages/kmp`](packages/kmp/README.md)), and other languages via the [`tools/protoc-gen-fieldmeta`](tools/protoc-gen-fieldmeta/README.md) plugin (which has integration recipes for firmware/Apple/Python).

### Licence, name and third-party content

The code is open — you may use, modify and redistribute it under the repository's licence (see the LICENSE file). We kindly ask for good practice:

- please give a modified or third-party version a different name and state that it does not come from us;
- please do not present your product, website or group as an official MT_SW project if it is not;
- you may quote our texts and documentation, naming the author and source;
- if you want to write about the project or the network, please contact us beforehand — we will help check the facts; please do not publish private data of the people behind the project.

We are not responsible for information, articles, videos, websites or statements made by third parties, including incorrect, outdated or unrelated facts about us. We distance ourselves from websites, structures, groups and persons who write or speak about us without any contact with us and without taking part in our community and network. Reliable information about the project is in our own channels and repositories (GitHub MT-SW, mt-sw.pl). Questions: through our channels (local groups, Discord/WhatsApp/Signal, the mesh network).

This project is not affiliated with or endorsed by Meshtastic LLC. Meshtastic® is a registered trademark of Meshtastic LLC. You use it at your own risk, with no warranty.
