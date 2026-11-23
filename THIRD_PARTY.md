# PiJava Deck 第三方代码、字体与素材 / Third-party code, fonts and assets

本清单针对当前 Steam Deck 源码和运行资源。项目自有代码沿用 GPL-3.0-or-later，见 [LICENSE](LICENSE)；第三方文件保留原有条款，尤其不能推定 GPL-2.0-only 文件具有“或更高版本”选项。文件内原始声明及附带完整许可优先，本说明不重新授权第三方材料。

This inventory describes the current Deck source and runtime resources. Project-owned code remains GPL-3.0-or-later; see [LICENSE](LICENSE). Third-party files retain their original terms, especially where GPL-2.0-only has no later-version option. Original file notices and complete license texts prevail; this document does not relicense third-party material.

## 代码与接口头文件 / Code and interface headers

`java/javax/microedition/m3g/` 中源自 FreeJ2ME 的文件及对应 `romfs/classes/javax/microedition/m3g/` 字节码保留原头部的 GPL-3.0-or-later；适配文件保留其自身声明。上游为 [FreeJ2ME-Plus](https://github.com/TASEmulators/freej2me-plus)，记录提交 `ca8e8e667a8d5da80f12693465da722793e1aaf3`。见 [来源记录](licenses/FreeJ2ME-plus-M3G-provenance.txt) 和 [GPL 文本](licenses/FreeJ2ME-plus-GPL-3.0.txt)。

FreeJ2ME-derived files in `java/javax/microedition/m3g/` and their corresponding `romfs/classes/javax/microedition/m3g/` bytecode retain GPL-3.0-or-later as stated in their original headers. Adapter files retain their own notices. The recorded upstream is [FreeJ2ME-Plus](https://github.com/TASEmulators/freej2me-plus), commit `ca8e8e667a8d5da80f12693465da722793e1aaf3`. See the [provenance record](licenses/FreeJ2ME-plus-M3G-provenance.txt) and [GPL text](licenses/FreeJ2ME-plus-GPL-3.0.txt).

`src/third_party/stb_image.h` v2.30 由 Sean Barrett 及原文件列出的贡献者提供，本项目使用 MIT / 公有领域双许可中的 MIT 选项。`src/jpeg_decoder.h` 是项目封装，不改变 stb 许可。[固定版本](https://raw.githubusercontent.com/nothings/stb/2c980bb59875b0d32144a71867fbdebb2f77cd20/stb_image.h)；[完整选项、哈希和声明](licenses/STB-IMAGE.txt)。

`src/third_party/stb_image.h` v2.30 is by Sean Barrett and the contributors credited in the file. This project uses the MIT option of its MIT/public-domain dual license. `src/jpeg_decoder.h` is a project wrapper and does not change stb's license. See the [pinned header](https://raw.githubusercontent.com/nothings/stb/2c980bb59875b0d32144a71867fbdebb2f77cd20/stb_image.h) and [full options, hash and notices](licenses/STB-IMAGE.txt).

`src/third_party/stb_truetype.h` v1.26 同样保留 Sean Barrett 与贡献者署名，使用 MIT / 公有领域双许可中的 MIT 选项。[固定版本](https://raw.githubusercontent.com/nothings/stb/6e9f34d5429cf16790ec43c9bac3f1ee4ad1f760/stb_truetype.h)；[完整声明](licenses/STB-TRUETYPE.txt)。

`src/third_party/stb_truetype.h` v1.26 retains attribution to Sean Barrett and contributors and uses the MIT option of its MIT/public-domain dual license. See the [pinned header](https://raw.githubusercontent.com/nothings/stb/6e9f34d5429cf16790ec43c9bac3f1ee4ad1f760/stb_truetype.h) and [complete notices](licenses/STB-TRUETYPE.txt).

`src/puff.c`、`src/puff.h` v2.3（2013-01-21）版权归 Mark Adler（2002–2013），保留 zlib 风格许可及三项限制。[上游 puff](https://github.com/madler/zlib/tree/master/contrib/puff)；完整原文在头文件和 [PUFF.txt](licenses/PUFF.txt)。

`src/puff.c` and `src/puff.h` v2.3 (2013-01-21) are copyright 2002–2013 Mark Adler, retaining the zlib-style permission and its three restrictions. See [upstream puff](https://github.com/madler/zlib/tree/master/contrib/puff); the complete original notice remains in the header and [PUFF.txt](licenses/PUFF.txt).

`tests/vendor/deko3d.h` 保留 fincs（2018–2020）的 zlib 风格许可，仅为继承的测试接口头，不是 Deck GPU 后端或完整 SDK。[原接口](https://github.com/devkitPro/deko3d/blob/master/include/deko3d.h)；`tests/vendor/README.md`（上游记录 / upstream reference）；[许可](licenses/deko3d.txt)。

`tests/vendor/deko3d.h` retains the zlib-style license of fincs (2018–2020). It is an inherited test interface header, not a Deck GPU backend or complete SDK. See the [upstream header](https://github.com/devkitPro/deko3d/blob/master/include/deko3d.h), `tests/vendor/README.md`（上游记录 / upstream reference） and [license](licenses/deko3d.txt).

`third_party/ffmpeg_headers/` 继承自 `switch-ffmpeg 7.1-5` 的 FFmpeg 7.1 公共头。除下述 GPL 和生成文件外，按各文件原作者声明使用 LGPL-2.1-or-later。分发时 include 路径改成相对路径，声明未改；原始和分发哈希在 [MANIFEST.json](third_party/ffmpeg_headers/MANIFEST.json)。见 [LGPL 文本](licenses/FFmpeg-LGPL-2.1.txt) 和 [FFmpeg 7.1 源码](https://ffmpeg.org/releases/ffmpeg-7.1.tar.xz)。

`third_party/ffmpeg_headers/` inherits FFmpeg 7.1 public headers from `switch-ffmpeg 7.1-5`. Apart from the GPL and generated files below, they use LGPL-2.1-or-later under their original authors' notices. Include paths were made relative without changing declarations; original and distributed hashes are in [MANIFEST.json](third_party/ffmpeg_headers/MANIFEST.json). See the [LGPL text](licenses/FFmpeg-LGPL-2.1.txt) and [FFmpeg 7.1 source](https://ffmpeg.org/releases/ffmpeg-7.1.tar.xz).

`libavutil/hwcontext_nvtegra.h`、`nvtegra.h` 保留 averne（2024）的 GPL-2.0-or-later；`nvhost_ioctl.h` 保留 NVIDIA（2016–2020）的 GPL-2.0-or-later；`nvmap_ioctl.h` 保留 NVIDIA（2009–2020）的 **GPL-2.0-only**，不声明更高版本选项。这些独立接口头不由根目录许可重新授权。完整原文见文件头和 [GPL-2.0.txt](licenses/GPL-2.0.txt)。

`libavutil/hwcontext_nvtegra.h` and `nvtegra.h` retain averne's (2024) GPL-2.0-or-later notices. `nvhost_ioctl.h` retains NVIDIA's (2016–2020) GPL-2.0-or-later notice. `nvmap_ioctl.h` retains NVIDIA's (2009–2020) **GPL-2.0-only** notice without a later-version option. These separate interface headers are not relicensed by the root license. See their headers and [GPL-2.0.txt](licenses/GPL-2.0.txt).

`libavutil/avconfig.h`、`ffversion.h` 是生成的 FFmpeg 配置和版本声明，随继承的头文件集原样保留；其生成文件声明与清单一并保留。

`libavutil/avconfig.h` and `ffversion.h` are generated FFmpeg configuration and version declarations retained verbatim with the inherited header set. Their generated-file notices and inventory are retained.

## 字体与派生字形 / Fonts and derived glyphs

Deck 宿主界面使用用户提供的 `romfs/font/cjk.ttf`，SHA-256 为 `aa4560dd8fe5645745fed3ffa301c3ca4d6c03cbd738145b613303961ba733b8`。本项目记录该指定文件，不凭文件名声明其字体家族、作者或许可，不将其重新授权；现有记录见 [user-cjk-font.json](licenses/user-cjk-font.json)。

The Deck host uses the user-supplied `romfs/font/cjk.ttf`, SHA-256 `aa4560dd8fe5645745fed3ffa301c3ca4d6c03cbd738145b613303961ba733b8`. This identifies the selected file without inferring its family, author or license from its filename, or relicensing it. See [user-cjk-font.json](licenses/user-cjk-font.json) for the existing record.

`src/font8x8_basic.h` 来自 Daniel Hepper 的 font8x8，基于 Marcel Sondaar / IBM 公有领域 VGA 字体，原头部声明为公有领域。[上游 font8x8](https://github.com/dhepper/font8x8)；原署名保留。

`src/font8x8_basic.h` comes from Daniel Hepper's font8x8, based on Marcel Sondaar / IBM public-domain VGA fonts. Its original header states public-domain terms. See [upstream font8x8](https://github.com/dhepper/font8x8); attribution is retained.

`src/latin16.h` 的继承 95 个 ASCII 字形，与随包 Unifont 输入在扩展每行 8 位为左对齐 16 位、去掉首行并补末行后逐字形相符，空格全零。这确认来源家族，不声明掌握原生成器或历史输入版本；适用下述 Unifont 字体条款。

The 95 inherited ASCII glyphs in `src/latin16.h` match the bundled Unifont input after expanding each 8-bit row to a left-aligned 16-bit row, dropping the first row and padding a final zero row; space is all zero. This establishes the source family, not an original generator or historical input version. The Unifont font terms below apply.

`romfs/font/cjk16.bin` 的 U+2E80–U+9FFF 字形由 `tools/rebuild_cjk16.py` 从固定 `third_party/unifont/unifont-16.0.04.hex.gz` 恢复，旧代码点和非 CJK 记录保留。[来源](third_party/unifont/README.txt)；[完整许可](third_party/unifont/LICENSE.txt)。Unifont 字形可按 SIL OFL-1.1 或 GPL-2.0-or-later 加字体嵌入例外使用，jiskan16 例外为公有领域；两种选择不由项目根 GPL 替换。

`tools/rebuild_cjk16.py` restores U+2E80–U+9FFF glyphs in `romfs/font/cjk16.bin` from pinned `third_party/unifont/unifont-16.0.04.hex.gz`, retaining legacy codepoints and non-CJK records. See the [source record](third_party/unifont/README.txt) and [complete license](third_party/unifont/LICENSE.txt). Unifont glyphs offer SIL OFL-1.1 or GPL-2.0-or-later with a font embedding exception; jiskan16 exceptions are public domain. Neither choice is replaced by the project's root GPL.

固定 Unifont 输入哈希为 `f9c8c7802453f47be02677176aeac2342ee96d354fad7a26cedcce48e68e1d9f`。继承 cjk16 非 CJK 部分没有全部重生成；只读比较可解释 21,425 项中的 21,422 项，包括原位图、行位移、半宽扩展和双倍 ASCII/Latin 或标点别名。U+FF02、U+FF06、U+FFE6 三个字形不匹配已检查的变换，历史输入仍未记录。这是来源追溯限制，不是新的许可授予。

The pinned Unifont input hash is `f9c8c7802453f47be02677176aeac2342ee96d354fad7a26cedcce48e68e1d9f`. The inherited non-CJK cjk16 portion was not fully regenerated. Read-only comparison explains 21,422 of 21,425 records through exact bitmaps, row shifts, halfwidth expansion and doubled ASCII/Latin or punctuation aliases. U+FF02, U+FF06 and U+FFE6 do not match the checked transformations, and their historical input remains unrecorded. This is a provenance limitation, not a new license grant.

`romfs/font/small12.bin` 非 ASCII 字形由 `tools/rebuild_small12.py` 打包随附文泉驿点阵宋体 0.9.9.8 的 9pt/12px BDF。版权归文泉驿项目委员会与 Qianqian Fang（2004–2010），按 BDF 原文为 **GPL v2 加字体嵌入例外**，不推定更高版本。见[作者](third_party/small12/WQY-AUTHORS.txt)、[许可](third_party/small12/WQY-COPYING.txt)、[来源](third_party/small12/README.txt) 和压缩 BDF 中原声明。固定单元格以外字形仍可能回退。

Non-ASCII glyphs in `romfs/font/small12.bin` are packed by `tools/rebuild_small12.py` from the bundled WenQuanYi Bitmap Song 0.9.9.8 9pt/12px BDF. Copyright belongs to the WenQuanYi Project Board of Trustees and Qianqian Fang (2004–2010), under **GPL v2 with a font embedding exception** as stated in the BDF, without an inferred later-version option. See the [authors](third_party/small12/WQY-AUTHORS.txt), [license](third_party/small12/WQY-COPYING.txt), [source details](third_party/small12/README.txt) and original BDF notices. Glyphs outside the fixed cell may still fall back.

small12 的 ASCII U+0020–U+007E 由同一脚本使用 `third_party/small12/6x12.bdf.gz` X11 Misc Fixed 打包，其 BDF 版权字段为“Public domain terminal emulator font. Share and enjoy.”。来源详情见同目录 README；原声明保持原文。

ASCII U+0020–U+007E in small12 is packed by the same script from `third_party/small12/6x12.bdf.gz`, X11 Misc Fixed. Its BDF copyright field reads “Public domain terminal emulator font. Share and enjoy.” Source details are in the adjacent README; the original notice is retained verbatim.

## 美术与遮罩 / Artwork and skins

`assets/app-logo.png` 是上游维护者在 2026-10-25 选定的 PiJava 图标；`assets/icon.png`、`assets/icon.jpg` 由 `tools/render_icon.py` 确定性转换尺寸和格式。出处见 `assets/LOGO.md`；本版保留图标文件及声明，不据此主张第三方商标所有权。根目录介绍不嵌入 HTML 图片标签。

`assets/app-logo.png` is the PiJava logo selected by the upstream maintainer on 2026-10-25. `assets/icon.png` and `assets/icon.jpg` are deterministic size/format derivatives from `tools/render_icon.py`. See `assets/LOGO.md`. This port retains the files and notices without claiming third-party trademark ownership. The root introduction embeds no HTML image tag.

`assets/phone-skins/phone-{black,blue,ivory}.png` 与 `romfs/skins/phone-*.skin` 继承原手机概念图素材。历史 `docs/RELEASE-0.1.85.md` 记录使用图像生成去除游戏画面；素材目录的 README 和 `packed-assets.json` 保留打包几何与输入/输出哈希。这记录制作过程，不声明所有参考图都由项目独立创作。

`assets/phone-skins/phone-{black,blue,ivory}.png` and `romfs/skins/phone-*.skin` descend from inherited phone-concept artwork. Historical `docs/RELEASE-0.1.85.md` records image generation used to remove game imagery; the asset README and `packed-assets.json` retain geometry and input/output hashes. This records the process without claiming independent authorship of every reference image.

`assets/phone-skins/controller-*.png` 与 `assets/keymap/pro-controller.png` 的历史制作过程包括基于用户参考图的图像生成、去文字及透明提取；打包产物为 `romfs/skins/controller-*.skin` 和 `romfs/ui/pro-controller.rgba`，相邻 JSON 保留哈希与几何。上游已去除的编辑器手机参考图不属于当前界面功能；可选运行时手机遮罩是另一些素材，沿用以上说明。不主张硬件外观或商标所有权。

The historical preparation of `assets/phone-skins/controller-*.png` and `assets/keymap/pro-controller.png` used image generation from user references, label removal and transparent extraction. Packed forms are `romfs/skins/controller-*.skin` and `romfs/ui/pro-controller.rgba`, with adjacent hashes and geometry. The editor phone-reference image removed upstream is not a current UI feature; selectable runtime phone skins are separate assets with the provenance above. No ownership of hardware designs or trademarks is claimed.

Deck 的空白自定义遮罩模板由简单几何布局生成；用户后来导入的图片属于用户素材，不因导入而转让权利或统一为项目许可。

The blank Deck custom-skin template is generated from simple geometric layout. Images later imported by users remain user-supplied material; importing them does not transfer rights or place them under the project license.

## 外部依赖与发行范围 / External dependencies and distribution scope

Deck SDL 前端使用 SDL2，并动态依赖 Linux 系统库；构建需另备 SDL2 开发文件、C++17 工具链、CMake/pkg-config 等。完整运行包不捆绑一整套 Linux 系统库或专有 SDK。实际 ELF 依赖以本版构建检查为准，不套用上游主机包的依赖结论。

The Deck SDL frontend uses SDL2 and dynamically depends on Linux system libraries. Building requires SDL2 development files, a C++17 toolchain, CMake/pkg-config and related tools. The runtime does not bundle an entire Linux system-library set or proprietary SDK. Use this release's ELF inspection for actual dependencies rather than upstream console-package conclusions.

libnx（[ISC 风格许可](licenses/libnx.txt)）和 deko3d（[许可](licenses/deko3d.txt)）是继承 Switch 后端的外部依赖，不是运行 Deck SDL 前端所需的完整 SDK 分发。源码保留测试接口头不等于分发完整 SDK；不包含 Nintendo 系统字体、密钥或商业 JAR。

libnx ([ISC-style license](licenses/libnx.txt)) and deko3d ([license](licenses/deko3d.txt)) are external dependencies of the inherited Switch backend, not a full SDK distributed for running the Deck SDL frontend. Retaining a test interface header does not distribute the complete SDK. Nintendo system fonts, keys and commercial JARs are not included.

继承的 Switch FFmpeg 恢复包是 GPL 配置，不是仅 LGPL；源码、补丁、配方、声明及证据限制索引见 [docs/DEPENDENCY-SOURCES.md](docs/DEPENDENCY-SOURCES.md)。这些历史依赖资料保持来源语境，不表示本 Deck 运行包附带上游 NRO/NSP、SDK 二进制，或已完成新增设备验收。

The inherited recovered Switch FFmpeg package is GPL-configured, not LGPL-only. Source, patches, recipes, notices and evidence limits are indexed in [docs/DEPENDENCY-SOURCES.md](docs/DEPENDENCY-SOURCES.md). Those historical references retain their original context; they do not mean this Deck runtime includes upstream NRO/NSP or SDK binaries, or that new device acceptance has been performed.
