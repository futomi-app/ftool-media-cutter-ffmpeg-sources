# FFmpeg corresponding source

This repository provides the corresponding source materials for the FFmpeg and
ffprobe executables distributed with fTool Media Cutter by futomi.app.

Download the **two uploaded source ZIPs and their SHA256SUMS.txt file** from
[Releases](https://github.com/futomi-app/ffmpeg-sources/releases). Both ZIPs are required. The automatically generated
GitHub **Source code (zip)** and **Source code (tar.gz)** downloads contain this
repository's documentation, not the complete FFmpeg source bundle.

The downloads require no application purchase, subscription or GitHub sign-in.
Select the release that matches the build listed in your application's
open-source notices. Each release retains its own source materials.

## Current source set

- Build ID: `btbn-9.0-20261109`
- Version: `n9.0.2-48-gd4070a14ce-20261109`
- Target: Windows x64, GPL, static executables
- FFmpeg commit: `d4070a14cecc7e29eb278f9b6036c2284255f70d`
- Build-recipe commit: `c9fe5114060e507409f7ee07edfd82efaf25d767`

The source bundle contains FFmpeg, incorporated dependencies and additional
build/test source dependencies, patches, build and installation scripts,
copyright notices, and licenses. Original component archives are preserved.
This repository does not contain the proprietary application's source code.

## Download and extract

1. Open the release for the required build.
2. Download both `*-source-part1-of-2.zip` and `*-source-part2-of-2.zip`, and
   `SHA256SUMS.txt`.
3. Verify each ZIP's SHA-256 against `SHA256SUMS.txt`.
4. Extract **both ZIPs into the same new directory**. They are ordinary ZIP
   archives with non-overlapping files, not split-volume ZIP segments.
5. Read `BUILD.txt` in that directory. It explains the source inventory,
   build environment, commands, verification performed, and limitations.

On Windows, download the three files to one directory and run PowerShell there:

```powershell
Get-FileHash -Algorithm SHA256 .\btbn-9.0-20261109-source-part1-of-2.zip
Get-FileHash -Algorithm SHA256 .\btbn-9.0-20261109-source-part2-of-2.zip
Get-Content .\SHA256SUMS.txt

Expand-Archive -LiteralPath .\btbn-9.0-20261109-source-part1-of-2.zip -DestinationPath .\ffmpeg-source
Expand-Archive -LiteralPath .\btbn-9.0-20261109-source-part2-of-2.zip -DestinationPath .\ffmpeg-source
```

On Linux:

```sh
sha256sum -c SHA256SUMS.txt
mkdir ffmpeg-source
unzip btbn-9.0-20261109-source-part1-of-2.zip -d ffmpeg-source
unzip btbn-9.0-20261109-source-part2-of-2.zip -d ffmpeg-source
cd ffmpeg-source
sha256sum -c SHA256SUMS
```

The extracted `SHA256SUMS` checks the complete set of source files from both
ZIPs. `SHA256SUMS.txt` downloaded separately checks the two ZIP containers.

## Licenses and build validation

The selected FFmpeg / ffprobe executables are licensed under GPL-3.0-or-later.
See `GPL-3.0.txt`, `DEPENDENCY-NOTICES.txt`, `licenses/`, and the original notices
inside each component archive. The upstream build scripts are MIT-licensed;
the supplemental reconstruction scripts are GPL-3.0-or-later. Each component
retains its own applicable terms. Application purchase and trial conditions do
not restrict rights granted by these licenses.

FFmpeg and rav1e were rebuilt with networking disabled inside the pinned
upstream toolchain/dependency image. The full 97-stage dependency build was
not rerun locally, and byte-identical reproduction is not claimed. Original
and tested reconstruction source sets are supplied for the unpinned rav1e
build-helper resolution. See `BUILD.txt` for the full explanation.

## 日本語

Releasesから、対象の版のZIP **2つとも** と `SHA256SUMS.txt` をダウンロードしてください。
購入・ログインは不要です。両方のZIPを同じ新規フォルダーへ展開し、`BUILD.txt` を参照してください。
GitHubが自動で表示する「Source code (zip)」「Source code (tar.gz)」は、必要なソース一式ではありません。
公開対象はFFmpeg / ffprobeとその依存部品・ビルド資料です。

## Upstream

- [FFmpeg](https://ffmpeg.org/)
- [Binary provider release](https://github.com/FFmpeg-Builds/FFmpeg-Builds/releases/tag/autobuild-2026-11-09-12-42)
- [Pinned build recipes](https://github.com/FFmpeg-Builds/FFmpeg-Builds/tree/c9fe5114060e507409f7ee07edfd82efaf25d767)

This is a redistribution of source materials; it is not the upstream FFmpeg
project or an official FFmpeg-Builds repository.
