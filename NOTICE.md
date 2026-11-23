# PiJava Deck 署名与声明 / Notices

本发行版是基于 [incuryou/PiJava](https://github.com/incuryou/PiJava) 的 Steam Deck / SteamOS 移植版。原项目的代码、类库与素材贡献继续保留署名；本版的 SDL 宿主、控制器界面、安装器、显示配置、文字工具和内存修改按当前源码记录。源码中的 Switch 后端和历史文档是继承的来源材料，不表示本包交付 NRO/NSP 或验证了相应硬件路径。

This distribution is a Steam Deck / SteamOS port of [incuryou/PiJava](https://github.com/incuryou/PiJava). Attribution for upstream code, libraries and assets is retained. This source tree records the Deck SDL host, controller UI, installer, display configuration, text tools and memory editor. Inherited Switch backends and historical documents do not mean this package ships NRO/NSP binaries or validates those hardware paths.

PiJava 项目自有代码沿用 GPL-3.0-or-later，完整文本见 [LICENSE](LICENSE)。第三方文件保留其各自的版权、许可选择和限制；根目录许可不会把 GPL-2.0-only、字体专用许可、宽松许可或公有领域材料改成项目自有代码。

PiJava project-owned source remains under GPL-3.0-or-later; see the complete text in [LICENSE](LICENSE). Third-party copyright, license choices and restrictions remain applicable. The root license does not convert GPL-2.0-only, font-specific, permissive or public-domain material into project-owned code.

本源码包含 FreeJ2ME/FreeJ2ME-Plus 贡献者、Sean Barrett 与 stb 贡献者、Mark Adler、fincs、FFmpeg 贡献者、NVIDIA、Daniel Hepper，以及 Unifont 和文泉驿材料中标注的字体贡献者的工作。原始声明保存在相应文件和许可材料中，逐项说明见 [THIRD_PARTY.md](THIRD_PARTY.md)。

This source includes work by FreeJ2ME/FreeJ2ME-Plus contributors, Sean Barrett and stb contributors, Mark Adler, fincs, FFmpeg contributors, NVIDIA, Daniel Hepper, and font contributors identified in the Unifont and WenQuanYi materials. Original notices remain in the relevant files and license materials; see [THIRD_PARTY.md](THIRD_PARTY.md) for the inventory.

本版的分辨率、机型键码和横屏功能曾参考用户提供的 j2me-nx-port 工程，并为 SDL 前端重新适配；手机名称仅标识键码兼容配置。标准输入框编辑、按内容标识的游戏显示名、自定义遮罩与窗口工具为 Deck 移植功能；空白遮罩模板由简单几何布局生成，既有遮罩美术继续保留其来源说明。

Resolution, phone key-code and landscape features were informed by the user-provided j2me-nx-port project and adapted for the SDL frontend. Phone names identify key-code presets only. Standard-field editing, content-keyed game aliases, custom skins and viewport tools are Deck additions. The blank skin template was generated from simple geometry; inherited artwork retains its provenance notices.

`romfs/font/cjk.ttf` 是用户指定并提供的字体，校验值及记录见 `licenses/user-cjk-font.json`。提供文件和记录哈希不等于取得额外字体许可；本移植不将其重新授权为 GPL，也不凭文件名推定许可。其他字体的来源和条款见第三方说明。

`romfs/font/cjk.ttf` is the font supplied and selected by the user; its hash and record are in `licenses/user-cjk-font.json`. Supply of a file and recording its hash do not grant additional font rights. This port does not relicense it as GPL or infer a license from its filename. Other font origins and terms are described in the third-party inventory.

Steam Deck、Steam、Valve、Nintendo、Nintendo Switch、Nokia、Java 等名称属于相应权利人，仅用于标识平台、API 或格式。本项目独立维护，不暗示隶属或背书，也不通过软件许可授予商标权。随包不含商业游戏、个人存档、主机密钥、Nintendo SDK 或 Nintendo 系统字体。

Steam Deck, Steam, Valve, Nintendo, Nintendo Switch, Nokia, Java and other names belong to their respective owners and identify platforms, APIs or formats only. This is an independent project; no affiliation, endorsement or trademark grant is implied. Commercial games, personal saves, console keys, the Nintendo SDK and Nintendo system fonts are not bundled.

软件不提供担保，完整条款以各适用许可证为准。编解码与平台依赖的继承资料见 [docs/DEPENDENCY-SOURCES.md](docs/DEPENDENCY-SOURCES.md)；其中 Switch 依赖和历史二进制记录不得解读为本 Deck 发行版的打包清单或测试结果。

The software has no warranty; consult the applicable license texts for complete terms. Inherited codec and platform dependency references are indexed in [docs/DEPENDENCY-SOURCES.md](docs/DEPENDENCY-SOURCES.md). Switch dependency and historical binary records there are not the packaging inventory or test results for this Deck release.
