# PiJava Deck v3.14 — 中文 / English

2026-11-23：新增全宿主界面中英文切换，保留 v3.13 的内存修改与现有 Deck 功能。

## 切换语言 / Change language

- 游戏列表顶部点击 EN / 中文 按钮可直接切换。
- 手柄：≡ → 设置管理 → 最后一项“语言 / Language”，按 A 或左右切换。游戏内从 ≡ → 显示设置进入同一页。
- 安装器：点击 English / 中文；选择会与模拟器共用。
- 自动保存至用户目录 `pijava/language.cfg`，内容为 zh 或 en。默认中文，切换立即生效，下次启动记忆。不会写入游戏配置或即时存档。

On the game list, click the language button at the top. With a controller, press Menu, scroll to the last Settings row (Language), then press A or Left/Right. In-game, open Menu → Display settings. The installer has an English / 中文 button too. Language is saved globally and takes effect immediately.

## 安装 / Install

完整解压运行包，双击 PiJava 运行，或双击“一键安装”/“Install”更新桌面入口。添加到游戏模式使用“添加到游戏模式”/“Add to Gaming Mode”，无需退出 Steam。程序与 romfs 必须一起更新。

Extract the complete archive. Open PiJava to play, or Install to create/update desktop shortcuts. Open Add to Gaming Mode to submit the Steam shortcut using SteamOS; Steam can stay running. Keep romfs beside the executable.

将直接可用的 .jar 放入 PiJava-Deck/games；列表按 Y 刷新，L3 选择目录，A 正常启动，X 读取即时存档。升级前备份用户数据。

Put .jar games in PiJava-Deck/games. Y refreshes, L3 selects the folder, A starts a game, and X loads its save state. Back up your user data before upgrading. Commercial games are not bundled.

## 覆盖范围 / Scope

游戏列表、11 项设置、暂停/存档、按键映射/录入、目录选择、文字/数字输入、遮罩导入与窗口调整、内存搜索/锁定/撤销、安装器/Steam 导入和宿主提示。英文文本按可用区域调整字号。使用用户指定的 `cjk.ttf`，随包附带，SHA-256 为 `aa4560dd8fe5645745fed3ffa301c3ca4d6c03cbd738145b613303961ba733b8`。

All emulator host screens, settings, pause/save actions, key mapping, folders, text/numeric input, skins/viewports, memory tools, installer and host messages support English. The supplied user font is included. Desktop entry names have English defaults and zh_CN names.

游戏画面、游戏自己的菜单/文字、JAR 内容、用户输入、路径、游戏名和遮罩名保持原文；界面语言不能将中文游戏翻译成英文。语言选择按钮有意保留中文标识，便于切回中文。

Game content and in-game text are not translated. User text, names and file paths stay unchanged. The language switch intentionally retains a Chinese label so users can switch back.

## 保留功能 / Existing features

23 个分辨率选项、自动尺寸识别、等比横屏显示、旋转、三种机型键码、中文/英文编辑器、自定义遮罩、按键映射、即时存档和整数内存修改均保留。内存工具仅当前运行有效，读档或重启清空规则。类库和 J2S5 格式不因本次语言更新改变。

Resolution presets/auto-detection, aspect-fit landscape display, rotation, phone key profiles, custom skins, key mapping, save states and the integer memory editor are retained. Memory rules last for the current session. This language update does not change Java class layouts or J2S5 format.

## 验证 / Validation

语言保存/重载、词条、组合提示、用户原文保护、11 行导航和安装器文件操作的主机测试通过；渲染 22 张中英文界面并检查英文布局。相关内存/界面回归结果详见构建记录。Linux x86_64 SDL 编译链接通过。尚未在 Deck 实机或 Linux JIT 机器码路径验证。

Host tests cover language persistence, catalog/composed messages, user text preservation, navigation and installer file operations. 22 Chinese/English host screens were rendered. The Linux SDL target was cross-compiled; Steam Deck hardware and Linux JIT execution remain untested.
