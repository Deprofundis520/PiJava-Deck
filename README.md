# PiJava Deck v3.14

PiJava Deck 是面向 **Steam Deck / SteamOS（Linux x86_64）** 的实验性 J2ME / MIDP 手机游戏模拟器，支持桌面模式和 Steam 游戏模式。当前版本为 v3.14，内部标识为 `0.2.114-deck-experimental3.14`。

PiJava Deck is an experimental J2ME / MIDP mobile-game emulator for **Steam Deck / SteamOS (Linux x86_64)**. It supports Desktop Mode and Steam Gaming Mode. The current release is v3.14, identified internally as `0.2.114-deck-experimental3.14`.

本版基于 [incuryou/PiJava](https://github.com/incuryou/PiJava) 移植，并综合适配作者的 FIT25 更新；Steam Deck 的 SDL 前端、启动器、控制器操作、显示设置和扩展工具以本源码树中的实现为准。原项目链接用于注明出处，不是本版运行包下载入口。

This port is based on [incuryou/PiJava](https://github.com/incuryou/PiJava), with adaptations of the author's FIT25 updates. This source tree defines the Deck SDL frontend, launcher, controller behavior, display settings and added tools. The upstream link credits the original project; it is not a download link for this Deck release.

[使用与语言切换 / Use and language](docs/LANGUAGE.md) · [内存修改 / Memory editor](docs/MEMORY-EDITOR.md) · [贡献 / Contributing](CONTRIBUTING.md) · [署名 / Notices](NOTICE.md) · [第三方 / Third parties](THIRD_PARTY.md)

## 主要功能 / Features

中文、英文宿主界面可即时切换并记住选择，覆盖游戏列表、设置、暂停菜单、按键映射、文字输入、遮罩和内存修改等页面。使用随包的 cjk.ttf 字体；游戏自身的文字、游戏名、路径和用户输入保持原文。

The Chinese and English host interfaces can be switched instantly, with the choice saved across launches. Coverage includes the game list, settings, pause menu, mapping, text entry, skins and memory tools. The supplied cjk.ttf font is bundled. Game text, names, paths and user input remain unchanged.

支持 23 个分辨率选项（21 个明确尺寸、默认和自动识别）、横屏与竖屏等比显示、0/90/180/270 度显示旋转、三种手机键码配置、内置遮罩、PNG/JPG/.skin 自定义遮罩导入和显示窗口调整，以及原画、双线性、Scale2x、LCD、CRT、ScanlinesDX 滤镜。

There are 23 resolution options (21 explicit sizes, Default and Auto), aspect-fit portrait and landscape display, 0/90/180/270-degree display rotation, three phone key-code profiles, built-in skins, PNG/JPG/.skin imports with viewport editing, and Original, Bilinear, Scale2x, LCD, CRT and ScanlinesDX filters.

支持手柄优先的手机按键映射、标准 MIDP TextBox/Form TextField 文字输入、游戏显示名修改、游戏内 RMS 存档、J2S5 即时存档和整数内存修改。内存工具提供精确搜索、未知初值、变化筛选、单目标改值、锁定与撤销。

Features include controller-oriented phone key mapping, text entry for standard MIDP TextBox/Form TextField controls, game display aliases, in-game RMS saves, J2S5 save states and an integer memory editor. Memory tools include exact and unknown-value searches, change filters, individual edits, locks and undo.

## 安装与启动 / Install and launch

将本版完整运行包解压到 Deck。双击 `PiJava` 直接运行，或双击 `一键安装` / `Install` 创建或更新桌面入口。使用 `添加到游戏模式` / `Add to Gaming Mode` 提交 Steam 快捷方式；无需退出 Steam，按系统可能显示的确认完成操作。正常使用不需要终端命令或另装 Java。

Extract the complete Deck runtime package. Open `PiJava` to run it directly, or `一键安装` / `Install` to create or update desktop shortcuts. Use `添加到游戏模式` / `Add to Gaming Mode` to submit the Steam shortcut, completing any system confirmation. Steam can stay running. Normal use requires neither terminal commands nor a separate Java installation.

程序必须与 `romfs` 等资源一起更新。首次运行若提示权限，在文件属性中允许作为程序执行。升级前关闭模拟器并备份用户数据；安装后确认列表显示 v3.14，避免旧桌面图标仍指向旧程序。

Update the executable together with `romfs` and the other resources. If prompted, allow execution in the file properties. Close the emulator and back up user data before upgrading. Confirm that the list shows v3.14 so an old shortcut does not silently launch an older build.

## 放游戏与基本按键 / Games and basic controls

把直接可用的 `.jar` 文件放进程序旁的 `games` 文件夹。游戏列表中 Y 刷新，L3（按下左摇杆）选择游戏目录，左摇杆或十字键选择，A 正常启动，X 读取所选游戏的即时存档。ZIP/RAR/7z 先解压；随包不附商业游戏。

Put ready-to-run `.jar` files in the adjacent `games` folder. On the game list, Y refreshes, L3 (left-stick click) selects a folder, the left stick or D-pad selects a game, A starts it, and X loads its save state. Extract ZIP/RAR/7z archives first. Commercial games are not bundled.

游戏中右侧 ≡ 打开暂停菜单，左侧视图键回到游戏列表。暂停菜单可返回游戏、调整显示设置、保存或读取即时存档、返回列表、结束游戏、打开文字输入或内存修改。返回游戏本身不会自动保存即时存档。

In a game, the right Menu button (≡) opens the pause menu; the left View button opens the game list. The pause menu offers Resume, Display settings, Save state, Load state, Game list, End game, Text input and Memory editor. Resuming a game does not itself save a state.

切换语言可点击列表顶部 EN / 中文，也可按 ≡ 进入设置，滚动到最后一项 Language，按 A 或左右切换。安装器也提供语言按钮。语言保存于用户目录的 `language.cfg`。

Switch languages with the EN / 中文 button at the top of the list, or open Settings with Menu, scroll to the last Language row and press A or Left/Right. The installer also has a language button. The choice is stored in the user directory's `language.cfg`.

修改映射时先选择手机目标键，按 ≡ 捕获 Deck 物理键，松开后按 A 确认，最后按视图键保存。左摇杆方向固定保留；B 取消未保存的映射草稿。建议在 Steam 为本程序选择标准游戏手柄布局。

To remap a control, select the target phone key, press Menu to capture a Deck control, release it, confirm with A, and finally press View to save. Left-stick directions are reserved. B discards unsaved mapping changes. A standard gamepad layout in Steam is recommended.

## 显示、输入与内存工具 / Display, input and memory tools

分辨率和手机机型按游戏保存，在下次按 A 正常启动时应用；读即时存档使用存档中的尺寸和配套机型记录。显示旋转只旋转画面，不自动改变按键方向。选择横屏尺寸不能保证写死竖屏布局的游戏会自动重排。

Resolution and phone profile are saved per game and apply on the next normal A launch. Loading a state uses its saved dimensions and associated phone record. Display rotation does not automatically rotate controls. A landscape resolution cannot guarantee that a game with a fixed portrait layout will rearrange itself.

文字工具适用于标准 TextBox 和 Form 中当前选中的 TextField；Canvas 自绘取名界面仍需游戏自己的输入方式。中文可由系统输入法或粘贴提交，内置键盘没有拼音词库。自定义遮罩可在设置中浏览导入并调整窗口。

The text tool supports standard TextBox controls and the selected TextField in a Form. Canvas-based name-entry screens still require the game's own input method. Chinese text can be submitted through a system IME or paste; the built-in keyboard has no Pinyin dictionary. Custom skins can be imported and their viewports adjusted in Settings.

内存修改支持 8/16/32/64 位有符号整数，最多 10 万候选、64 条锁定和 32 次撤销记录。规则只在当前运行有效，读档、重启或换游戏会清空。周期锁定不拦截每条 Java 指令；修改后的普通数值可以随即时存档保存。详见[内存说明](docs/MEMORY-EDITOR.md)。

The memory editor supports signed 8/16/32/64-bit integers, up to 100,000 candidates, 64 locks and 32 undo records. Rules last for the current session and are cleared on state load, restart or game switch. Periodic locking does not intercept every Java instruction. Edited ordinary values can be saved in a state. See the [memory guide](docs/MEMORY-EDITOR.md).

## 数据、兼容性与验证 / Data, compatibility and validation

默认用户数据根目录是 `/home/deck/.local/share/pijava`；设置 `XDG_DATA_HOME` 时以其下 `pijava` 为准。`app` 存程序，`rms` 存游戏自身进度，`state` 存即时存档，`game-options` 存每游戏配置与存档机型记录，`skins` 存导入素材。备份时建议保留整个用户目录。

The default user-data root is `/home/deck/.local/share/pijava`, or `pijava` under `XDG_DATA_HOME` when set. `app` holds the application, `rms` the game's own saves, `state` save states, `game-options` per-game options and state phone records, and `skins` imported artwork. Back up the entire user directory where possible.

不同版本、类库布局及挂起方法变化可能影响即时存档兼容性，不保证所有旧状态均能恢复。游戏兼容性需逐款确认，能启动不等于关卡、音频、输入和存档均已验证。手机机型是键码兼容配置，不是完整硬件仿真。

Save-state compatibility can be affected by version, library layout and suspended-method changes; not every old state is guaranteed to load. Compatibility must be checked per game. Launching successfully does not establish complete level, audio, input or save validation. Phone profiles are key-code presets, not full hardware emulation.

本版已完成 Linux x86_64 SDL 交叉编译、Windows 主机相关 VM/界面回归及发布包检查，双语界面生成了 22 张渲染截图。尚未验证发布 Linux ELF、Linux JIT 机器码、Deck 实机 Steam Input 或商业游戏完整流程。上游 Switch 的三核、GPU、NRO/NSP 验证不作为本版性能或设备验收结论。

The release has been cross-compiled for Linux x86_64 SDL, with related Windows-host VM/UI regressions and package checks. Twenty-two bilingual host-screen renders were generated. The released Linux ELF, Linux JIT machine code, physical Deck Steam Input and complete commercial-game runs have not been validated. Upstream Switch CPU, GPU and NRO/NSP results are not presented as Deck performance or device acceptance.

## 源码与构建 / Source and build

本源码包包含 C++/Java 源码、随包类库字节码、资源、测试和许可。Deck 的主要入口是 `src/platform/sdl_host.inc`，界面与工具在相邻 `deck_*` 文件中。语言实现在 `deck_i18n.h`，词表对照在 `docs/ui-english.json`；增加文案时需同步并保留用户内容的原文保护。

The source package includes C++/Java source, runtime library bytecode, resources, tests and licenses. The main Deck entry is `src/platform/sdl_host.inc`, with UI and tools in adjacent `deck_*` files. Language support lives in `deck_i18n.h`, with a readable catalog in `docs/ui-english.json`. Update both when adding text and preserve raw user content.

Linux 原生构建需要 CMake、pkg-config、SDL2 开发包和支持 C++17 的编译器。在源码根目录运行以下命令。此 CMake 路径不自动重编 Java，也不覆盖全部 VM 测试；以下命令是构建入口说明，本次文档改写未重新执行它们。

A native Linux build needs CMake, pkg-config, SDL2 development packages and a C++17 compiler. Run the following at the source root. This CMake path does not rebuild Java automatically or cover every VM test. These commands document the build entry point; they were not rerun for this documentation revision.

```sh
cmake -S . -B build-deck -DCMAKE_BUILD_TYPE=Release -DBUILD_TESTING=ON
cmake --build build-deck -j2
ctest --test-dir build-deck --output-on-failure
cmake --install build-deck --prefix ./dist-deck
```

修改 Java 类库后，使用兼容 JDK8 的完整类库构建流程更新 `romfs/classes`，再生成 `tools/generate_library_manifest.py` 对应的受信任清单。`tools/deck-maintenance/` 保存本机维护脚本快照及路径说明，包含原工作区依赖，不能在任意目录直接视为一键构建工具。

After changing the Java library, rebuild the complete library with a JDK8-compatible process, update `romfs/classes`, then regenerate the trusted manifest with `tools/generate_library_manifest.py`. `tools/deck-maintenance/` contains snapshots of local maintenance scripts and path notes. They retain original workspace dependencies and are not portable one-click builders.

`SHA256SUMS` 校验源码文件，`SOURCE-MANIFEST.json` 记录本次源码清单，`STEAMDECK-PORT.json` 记录移植信息。这些文件使用机器可读格式，不采用中英段落交错。上游历史说明仅作来源资料，当前介绍与使用以本 README 和 Deck 专用文档为准。

`SHA256SUMS` checks source files, `SOURCE-MANIFEST.json` records this source inventory, and `STEAMDECK-PORT.json` records port metadata. Their machine-readable formats do not use alternating prose paragraphs. Historical upstream documentation is provenance material; this README and the Deck-specific guides define current use.

## 来源与许可 / Origin and licenses

感谢 incuryou/PiJava 原作者及各第三方贡献者。本版保留原出处、源文件署名和许可，项目自有代码沿用 GPL-3.0-or-later；第三方文件、字体和素材按其各自条款。请阅读 [LICENSE](LICENSE)、[NOTICE.md](NOTICE.md) 和 [THIRD_PARTY.md](THIRD_PARTY.md)。本版与 Valve、Steam、Nintendo、Nokia、Java 等名称的权利人无隶属或背书关系。

Credit goes to the incuryou/PiJava author and all third-party contributors. This port retains provenance, file-level attribution and licenses. Project-owned code remains under GPL-3.0-or-later; third-party files, fonts and artwork keep their own terms. Read [LICENSE](LICENSE), [NOTICE.md](NOTICE.md) and [THIRD_PARTY.md](THIRD_PARTY.md). No affiliation with or endorsement by the owners of Valve, Steam, Nintendo, Nokia, Java or related names is implied.
