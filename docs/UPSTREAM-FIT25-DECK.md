# 作者 FIT25 综合适配与测试说明 · Deck v3.12

2026-10-30。承接 Deck v3.11，继续综合作者 PiJava-keyui7-fit25-source.zip。以最初源码、作者新包和 Deck 版做三方比较，合入 108 项 src/java 功能文件的更新，并补齐 Deck 适配。冲突集中于 host_menu.h、j2mevm.cpp、presentation/filters.h，逐处处理；Deck 的操作、数据目录、机型键码、等比显示和自定义遮罩继续保留。附件中的说明与历史证据仅作资料，本次测试结论来自重新编译、运行的结果。

## 本次合入

| 部分 | 结果 |
|---|---|
| 事件与调度 | 合入事件回调串行化、serviceRepaints 延后服务、画布生命周期和事件帧等待学习；文字输入提交、ItemStateListener 与命令事件接入同一路径。保留 Deck 暂停与焦点管理。 |
| 运行核心 | 合入作者快速分发、long 运算、接口分发与读叶路径、JIT 代码池/资源代际、数组缓冲池、集合/字符串索引、诊断及日志改进。未擅自改变 JIT 默认启用策略，未宣称帧率提升。 |
| MIDP 界面 | 合入 CustomItem 绘制、遍历、按键和 Form 焦点能力，以及 StringItem 字体/外观支持；保留 TextBox/Form TextField 的 Deck 文字编辑入口。 |
| 基础类库 | 保留 v3.11 的 Double、异常、Stack、缓冲输入流修补；所有随包 Java 源码整批编译，并重新生成受信任类库清单。保留我们 Canvas 的三个 native 键码接口。 |
| 新 API 边界 | 合入蓝牙、PIM、传感器、文件连接及厂商兼容类；这些是兼容接口与不可用行为边界，不等于已经实现 Deck 蓝牙发现、通讯或传感器硬件访问。 |
| 分辨率 | 共 23 个选项：21 个明确尺寸，加默认和自动识别。新增 176×205、240×400、320×480、352×416、360×360、480×800、800×480。单边最大 800，总像素预算 409600，不开放 800×800。 |
| 自动识别 | 作为独立可选项，不改变旧配置的“默认”。无 sidecar 时参考 JAD/清单、文件名和可识别的常量画布声明；冲突会提示，不能可靠判断时回退。明确菜单尺寸与 CLI 的优先级保留，读即时存档使用存档尺寸。 |
| 显示 | 加入每游戏 0/90/180/270 度画面旋转，仅旋转呈现，不改变逻辑画布或按键方向。接入自适应遮罩，原有 0–6 遮罩 ID 不重排，新 ID 为 7；自定义遮罩和等比黑边继续生效。 |
| 配置与映射 | 设置增至 10 项；每游戏配置升级为 v3，兼容读取 v1/v2，旧配置旋转默认为 0。映射页增加 Y 清空草稿，左摇杆方向保留，仍需视图键保存，B 可取消。 |
| 现有修补 | v3.11 的 MIDI、JAR 检查、RMS、终止线程整理、滤镜边界继续保留；保留 Deck 启动器、中文字体、游戏扫描、按键去重和无需退出 Steam 的导入入口。 |

Switch/桌面共用源码随关联更新一起保留；本次交付与构建目标仍为 Linux x86_64 SDL 前端，没有把 Switch GPU 后端当作 Deck 实现。

## 本次实际测试

用户允许恢复测试后，使用 Windows 主机运行由生产源码编译的模型测试和 VM 解释器探针。为 POSIX 文件系统、动态库与 CPU 查询提供仅供测试的 Windows 适配头，没有把这些适配头链接进发布的 Linux 程序。测试执行程序不放入运行包。

- 11 组基础回归：四组音频、原始数组池、诊断、Deck 输入、UI 输入去重、映射、游戏扫描、即时存档文件管理。
- 3 组界面/移植回归：菜单导航，UTF-8 编辑/旧配置迁移/旋转/800 像素边界/遮罩等比，以及六套真实遮罩和六种滤镜。
- 接口解释执行与状态往返两组：111 项语义检查，含多态、空引用、GC 和恢复。
- 事件绘制 96 个 cap/场景组合；事件帧等待 633 项检查，含真实 Timer 回调链、长等待与生命周期守卫。
- 195 项字符串索引检查：强制哈希碰撞、重复、修改、内存预算及回收。
- long 运算 2516 组向量，覆盖预算 0–5 和边界字面量。
- 新类库/Form/CustomItem 实际 VM 探针：文字回写与监听器、字体、绘制/遍历、机型 native 键码、J2S5 编解码及恢复。

共 21 组运行结果通过。测试曾发现 Double.toString(1.5) 受旧底层格式化影响返回 1.500，已改为可往返的数值格式，并加入科学记数、负零、无穷与最小非正规数回归。删除了测试目录里会遮蔽真实 CustomItem 的 API 编译桩，再重新运行表单与事件测试。

另以项目真实中文字体渲染并目视检查游戏列表、旋转设置和文字编辑器，修正了标题排布。Linux x86_64/glibc 2.31 的 SDL 目标完成编译、链接及 ELF/归档检查；完整 Java 类库编译通过。

**边界：未在 Steam Deck 实机运行，未执行发布的 Linux ELF，未验证 Linux JIT 机器码、Steam Input 实际事件、SteamOS 导入与中文系统输入法，也未跑商业游戏场景或测量帧率。Windows VM 测试不能代替这些验证。** 原始日志和测试用适配头见《测试记录-v3.12.zip》，结果汇总见《构建验证记录-v3.12.md》。作者原包历史日志没有计入本次通过项。

## 升级与即时存档

完整解压新包，运行一键安装，确认列表显示 v3.12。游戏 JAR 的 SHA-256 身份和 RMS 数据目录不变，旧每游戏配置可读取。

本次 StringItem 等类库布局和执行路径有变化。虽然继续使用 J2S5，**部分旧即时存档可能无法恢复**，不能保证跨版本挂起状态兼容；本版新建的 Form/CustomItem 状态往返已经测试。原兼容校验没有绕过，旧存档文件不主动删除。升级前先在游戏内保存进度，并保留 v3.11 程序与用户数据备份；必要时用旧版恢复旧即时存档。不要让旧版覆盖已经升级到 v3 的游戏配置。

新增操作：设置管理 → 游戏分辨率 → 自动识别或具体尺寸；设置管理 → 画面旋转 → 左右切换。分辨率/机型需下次 A 正常启动，画面旋转可用于当前游戏。按键映射页 Y 清空后，视图键保存。

## 来源与补丁

作者归档 SHA-256：`5cf1a572a78e7916e7219f85cbbdea1df1759f3a21df2f50a27c4a17e3c4cdfd`。

《作者更新合入-v3.12.patch》相对 Deck v3.11；《steamdeck-v3.12.patch》相对最初 PiJava-main.zip。文本补丁不包含二进制 class/字体/图片，完整资源请使用源码 ZIP。以下是此次三方合入的功能文件，不把测试日志和换行变化算作功能：

- `java/com/motorola/multimedia/Lighting.java`
- `java/com/samsung/util/LCDLight.java`
- `java/com/siemens/mp/game/Vibrator.java`
- `java/java/io/BufferedInputStream.java`
- `java/java/io/FilterInputStream.java`
- `java/java/lang/Double.java`
- `java/java/lang/StringIndexOutOfBoundsException.java`
- `java/java/lang/UnsupportedOperationException.java`
- `java/java/util/Stack.java`
- `java/javax/bluetooth/DataElement.java`
- `java/javax/bluetooth/DiscoveryAgent.java`
- `java/javax/bluetooth/LocalDevice.java`
- `java/javax/bluetooth/ServiceRecord.java`
- `java/javax/bluetooth/ServiceRegistrationException.java`
- `java/javax/microedition/io/Datagram.java`
- `java/javax/microedition/io/DatagramConnection.java`
- `java/javax/microedition/io/file/ConnectionClosedException.java`
- `java/javax/microedition/io/file/FileConnection.java`
- `java/javax/microedition/io/file/FileSystemListener.java`
- `java/javax/microedition/io/file/FileSystemRegistry.java`
- `java/javax/microedition/io/file/IllegalModeException.java`
- `java/javax/microedition/io/HttpsConnection.java`
- `java/javax/microedition/io/PushRegistry.java`
- `java/javax/microedition/io/SecurityInfo.java`
- `java/javax/microedition/lcdui/CustomItem.java`
- `java/javax/microedition/lcdui/Display.java`
- `java/javax/microedition/lcdui/Form.java`
- `java/javax/microedition/lcdui/Item.java`
- `java/javax/microedition/lcdui/StringItem.java`
- `java/javax/microedition/pim/Contact.java`
- `java/javax/microedition/pim/ContactList.java`
- `java/javax/microedition/pim/FieldEmptyException.java`
- `java/javax/microedition/pim/FieldFullException.java`
- `java/javax/microedition/pim/PIM.java`
- `java/javax/microedition/pim/PIMException.java`
- `java/javax/microedition/pim/PIMItem.java`
- `java/javax/microedition/pim/PIMList.java`
- `java/javax/microedition/pim/UnsupportedFieldException.java`
- `java/javax/microedition/pki/Certificate.java`
- `java/javax/microedition/sensor/Channel.java`
- `java/javax/microedition/sensor/ChannelInfo.java`
- `java/javax/microedition/sensor/Condition.java`
- `java/javax/microedition/sensor/ConditionListener.java`
- `java/javax/microedition/sensor/Data.java`
- `java/javax/microedition/sensor/DataAndErrorListener.java`
- `java/javax/microedition/sensor/DataListener.java`
- `java/javax/microedition/sensor/MeasurementRange.java`
- `java/javax/microedition/sensor/SensorConnection.java`
- `java/javax/microedition/sensor/SensorInfo.java`
- `java/javax/microedition/sensor/SensorListener.java`
- `java/javax/microedition/sensor/SensorManager.java`
- `java/javax/microedition/sensor/Unit.java`
- `java/mmpp/media/BackLight.java`
- `src/array_storage.h`
- `src/async_log.inc`
- `src/audio_engine.h`
- `src/canvas_declared_size.h`
- `src/canvas_resolution.h`
- `src/causal_diagnostics.h`
- `src/causal_diagnostics.inc`
- `src/continuation.inc`
- `src/controller_skin_labels.h`
- `src/event_frame_sleep.h`
- `src/event_frame_sleep_runtime.inc`
- `src/exec_context.h`
- `src/host_display_menu.h`
- `src/host_display_preferences.h`
- `src/host_keymap.h`
- `src/host_keymap_ui.h`
- `src/host_menu.h`
- `src/host_menu_settings.h`
- `src/host_skin.h`
- `src/instant_state.inc`
- `src/interpreter_fast.inc`
- `src/j2mevm.cpp`
- `src/jit_code_pool.h`
- `src/jit_region.h`
- `src/logical_screen.h`
- `src/menu_actions.h`
- `src/native_jit236.h`
- `src/p1_diagnostics.inc`
- `src/p7_present.h`
- `src/pace.h`
- `src/platform/desktop_host.inc`
- `src/platform/switch_host.inc`
- `src/poll_gate.h`
- `src/present_fps.h`
- `src/presentation/filters.h`
- `src/presentation/gpu_filter.h`
- `src/presentation/gpu_filter_assets.h`
- `src/presentation/gpu_filter_math.inc`
- `src/presentation/orientation.h`
- `src/presentation/viewport.h`
- `src/primitive_buffer_pool.h`
- `src/runtime/interpreter.inc`
- `src/runtime/library_index.h`
- `src/runtime/library_intrinsics.inc`
- `src/runtime/midp_bridge.inc`
- `src/runtime/native_jit.inc`
- `src/runtime/object_model.inc`
- `src/runtime/reviewed_library_manifest.h`
- `src/runtime_diagnostics.h`
- `src/runtime_diagnostics.inc`
- `src/switch_audio.h`
- `src/switch_gpu_present.h`
- `src/threading.h`
- `src/vm_access_impl.h`
- `src/vm_storage.h`
