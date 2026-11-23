# 参与 PiJava Deck 开发 / Contributing to PiJava Deck

本源码以 Steam Deck / SteamOS 的 Linux x86_64 SDL 版本为维护目标。提交问题或补丁时，请说明它对本版用户的影响，保持改动集中，保留原项目及第三方署名。

This source tree targets the Steam Deck / SteamOS Linux x86_64 SDL version. Explain the impact on this port's users when submitting an issue or patch. Keep changes focused and retain upstream and third-party attribution.

报告问题请提供 Deck 版号、桌面或游戏模式、实际启动入口、Steam 控制器布局、复现步骤、预期与实际结果。游戏问题还需 JAR 的 SHA-256、分辨率、手机机型和是否使用即时存档；附必要日志时先去掉账号、路径中的个人信息和其他隐私数据。

For bug reports, include the Deck version, Desktop or Gaming Mode, actual launch entry, Steam controller layout, reproduction steps, and expected versus actual behavior. For game issues, add the JAR SHA-256, resolution, phone profile and save-state use. Remove account details, personal path information and other private data from logs.

不要提交商业游戏、个人存档、密钥、专有 SDK 或未经授权的字体和图片。可提交自写最小 Java fixture、测试源码及不含游戏数据的必要证据；主机探针、界面渲染和 Deck 实机结果应分别标注。

Do not submit commercial games, personal saves, keys, proprietary SDKs or unauthorized fonts and images. Self-authored minimal Java fixtures, test source and necessary evidence without game data are welcome. Label host probes, UI renders and physical Deck results separately.

界面改动应同时检查中文和英文、手柄及鼠标命中区域、导航数量、返回路径与焦点；新增文字同步 `deck_i18n.h` 和 `docs/ui-english.json`，不要翻译游戏名、文件路径和用户输入。按键改动要检查 Steam 键盘模拟与 SDL 手柄双来源的去重。

UI changes should check both languages, controller and pointer hit areas, navigation counts, back paths and focus. Update `deck_i18n.h` and `docs/ui-english.json` together, without translating game names, file paths or user input. Input changes should check deduplication between Steam keyboard emulation and SDL controller sources.

VM、GC、事件、JIT、数组、类库或存档改动应附相关回归和兼容性说明。Java class 更新后重新生成受信任清单；内存写入遵守类型、epoch/generation、布局和缓存屏障。不要绕过校验来掩盖过期目标或存档不兼容。

VM, GC, event, JIT, array, library and state changes need relevant regressions and compatibility notes. Regenerate the trusted manifest after updating Java classes. Memory writes must respect types, epoch/generation, layout and cache barriers. Do not bypass checks to hide stale targets or incompatible states.

提供实际使用的构建命令、工具版本和测试结果。性能对比注明设备、同一 JAR/场景、设置与测量方法；不能把交叉编译、短时启动、主机解释器或上游 Switch 结果当成 Deck 全流程或满帧验收。

Record the actual build commands, tool versions and test results. Performance comparisons should identify hardware, identical JAR/scenario, settings and measurement method. Cross-compilation, brief launches, a host interpreter and upstream Switch results do not establish complete Deck or full-frame-rate acceptance.

新依赖应记录版本、来源、许可、构建方法和所附文件。项目自有代码按 GPL-3.0-or-later 提交；第三方原有许可不因本项目而改变。提交前更新相关使用说明、源码清单与校验值，避免把本地临时文件或旧测试结论收入发布。

For new dependencies, record version, origin, license, build method and included files. Submit project-owned code under GPL-3.0-or-later; third-party licenses remain unchanged. Update relevant documentation, source inventories and hashes before release, excluding local temporary files and stale test claims.
