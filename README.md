# Hotline Miami 2 简体中文汉化 / Simplified Chinese Localization

> 把《迈阿密热线 2：错号》彻底变成中文——**菜单、操作提示、HUD、对话、字幕、章节标题、成就页、关卡编辑器**，一个不落。
> 一键安装、一键还原；不碰存档，**Steam 成就 ID 一字不改**，成就照常解锁。

**适用版本**：Steam 版《Hotline Miami 2: Wrong Number》 ｜ **系统**：Windows 10 / 11

![成就页面](docs/shot_achievement.png)
![关卡编辑器](docs/shot_editor.png)

<sub>上图不是设计稿，是把汉化后的游戏字体文件重新解出来渲染的真实结果。</sub>

---

## ✨ 特性

- **2889 条游戏文本全翻译**：菜单 / 操作提示 / HUD / 对话 / 字幕 / 章节标题，覆盖全部剧情与玩法内容；
- **成就页也是中文**：成就名与描述硬编码在 `HotlineMiami2.exe` 里（**不读 WAD 文本库**），只改 WAD 永远是英文。本补丁对 exe 做**等长字节替换**——偏移不变、Steam 成就 ID 不变；
- **关卡编辑器也汉化了**：编辑器整套 UI（下载/上传/本地/战役/单人关卡/搜索、快捷键提示、确认弹窗…共 56 条）同样硬编码在 exe 里，已一并处理。**这是市面上多数汉化补丁漏掉的一块**；
- **中文用微软雅黑粗体渲染**：原版字体是粗斜体像素字，中文字形若用常规体在 10px 下横画会整根丢失。本补丁给 76 套字体各注入 1343 个汉字字形，字号取该字体行高允许的最大值，字距重算，**逐字比对 0 缺字**；
- **按键标记零错漏**：`[WASD]`、`[SPACE]`、`[LMB]`、`[Del]` 等标记逐条比对，原样保留；
- **非破坏式注入**：文本/字体只改 WAD（新数据追加到文件末尾，其余 4369 个文件字节级零改动）；exe 只做等长文本替换。安装前自动备份 `hlm2_data_desktop.wad.bak` 与 `HotlineMiami2.exe.bak`；
- **纯 PowerShell 安装器**：不需要 Python、不需要额外运行库；安装器按**文件偏移**定位替换，重复执行也安全（幂等）。

## 📦 下载

前往 [**Releases**](../../releases) 页面，下载最新的 `HotlineMiami2_CN_Pack_v*.zip`（约 79 MB，只含汉化数据与安装脚本，不含任何游戏官方资源）。

## 📜 版本历史

| 版本 | 内容 | 状态 |
|---|---|---|
| **v1.1（当前）** | 文本 + **成就页** + **关卡编辑器** 全汉化；中文改用微软雅黑粗体 | 最新 |
| v1.0 | **只汉化文本**，成就页与编辑器仍英文；轻量注入版（不改 exe） | 历史存档，仍可在 Releases 下载 |

各版详细差异、以及 v1.1 初版（成就字迹发虚）为何被撤下，见 [**CHANGELOG.md**](CHANGELOG.md)。

## 🔧 安装

1. **完整解压**压缩包到一个文件夹（不要在压缩软件里直接双击运行）；
2. 双击 **`安装汉化.bat`**；
3. 等它显示「安装完成」（约 10–30 秒）。

安装器会自动定位 Steam 游戏目录，并把你的原版文件备份为 `hlm2_data_desktop.wad.bak` 与 `HotlineMiami2.exe.bak`。

## 🎮 开始游戏

启动游戏即中文（默认英文语言下显示中文）。若看到英文：**Options → Language → English**。

## ↩️ 还原英文原版

- 双击 **`卸载汉化.bat`**；或
- 在 Steam 中对游戏执行 **验证文件完整性**。

> 注意：Steam 验证完整性会把游戏恢复为英文原版（汉化消失）。想再玩中文，重新运行安装器即可。

## 🖼️ 效果

| 菜单 | 对话与字幕 |
|---|---|
| ![菜单](docs/shot_menu.png) | ![对话](docs/shot_dialog.png) |

| 操作提示 | 关卡编辑器 |
|---|---|
| ![操作提示](docs/shot_controls.png) | ![编辑器](docs/shot_editor.png) |

## ❓ FAQ

**Q：安装器被 Windows SmartScreen / 杀毒软件拦截？**
安装器是免费开源的 PowerShell 脚本，未做数字签名，可能触发提示。选择「更多信息 → 仍要运行」即可；不放心可以先看源码（`install.ps1` / `uninstall.ps1` / `patch_exe.ps1` 全在里面）再运行。

**Q：为什么要改 exe？不是只动 WAD 吗？**
绝大多数文本都在 WAD 内的 `hlm2_localization.bin`。但**成就名/描述与关卡编辑器 UI 硬编码在 `HotlineMiami2.exe` 中**，文本库里一条都没有，只改 WAD 这两块永远是英文。所以安装器额外做等长替换：每个英文串原地换成中文 UTF-8 字节、尾部补 `0x00` 到原长，**所有文件偏移不变**，Steam 成就 ID 一字未动。

**Q：需要正版吗？**
是。本补丁只提供汉化数据并注入到**你自己购买安装的游戏**里，不包含、也不用于绕过任何正版验证。

**Q：其他版本（GOG / 学习版）能用吗？**
只测试过 Steam 版。WAD 结构一致理论上可用，风险自负，欢迎反馈。

**Q：为什么选 English 显示的是中文？**
本补丁把 English 列**替换**为中文（并额外新增一列 `Chinese (Simplified)`），这样无论引擎从哪一列取文本都是中文。想要英文随时按上文还原。

**Q：字体和原版像素风不一样？**
中文字形用的是微软雅黑粗体，属于必要妥协（原版字体只含拉丁/西里尔字形）。详见「已知限制」。

## ⚠️ 已知限制

1. **3 个成就名保持英文**：`1-800-CLEARED`、`1-800-GETHELP`、`1-800-GODDAMN`。这几个成就的**显示名就是它的 Steam API 标识符本身**，改了会导致成就无法解锁，因此**刻意保留英文**。同理，编辑器里的 `PUBLISH_CONFIRM` 等全大写标识符与 `Tab`/`Esc`/`Del` 等按键名也未翻译。
2. **正文字号偏小**：原版正文字体只有 8–12 像素高，中文已放大到行高允许的上限并换用粗体，但清晰度仍不及约 20 像素的菜单文字。
3. 少数很长的对话行可能贴近文本框边缘。
4. 离线验证做到极限：安装后逐一反查 121 条 exe 文本、1343 个字形在 76 套字体中比对 0 缺字、未改动的 4369 个文件字节级一致。正式版已由作者**在真机实机验证**成就页与编辑器显示正常。

## 🛠️ 技术原理（简）

- **文本库** `Assets/hlm2_localization.bin`：自定义二进制格式，10 种语言 × 3247 条（其中 2889 条真实文本），UTF-8。中文作为新语种追加，并把其余语种列一并填为中文。
- **字体** `Fonts/*.fnt`（BMFont XML）+ `_0.png`（8-bit 灰度掩码）：原图集原样保留，空白区追加中文字形，只更新 `chars count` / `scaleW` / `scaleH` 并追加 `<char>` 行——**原有字形坐标一个像素未动**。
- **WAD 注入**：AGAR 容器格式。新数据追加到文件末尾，只原位改写对应条目的 u64 长度/偏移字段，文件名不变 ⇒ 目录表与头部完全不动。
- **exe 补丁**：`patch_exe.ps1` 读取 `exe_map.json`（121 条 `{偏移, 原文, 中文, 预算}`），按偏移定位、等长写入 NUL 补齐；替换前校验当前字节与原文一致，失败即中止。

## 📄 免责声明

本项目为粉丝制作的非官方汉化，与 Dennaton Games / Devolver Digital 无关。仓库与发布包**不包含任何官方游戏资源文件**，仅包含补丁数据（翻译文本与派生字体）和安装脚本，且仅供已合法购买游戏的玩家使用。请支持正版。使用本补丁产生的任何问题由使用者自行承担。

---

## English Quick Start

Simplified Chinese localization for the Steam version of Hotline Miami 2: Wrong Number — menus, prompts, HUD, dialogue, subtitles, chapter titles, **achievement page** and **level editor** (the latter two are hardcoded in the .exe, not in the WAD).

1. Download `HotlineMiami2_CN_Pack_v*.zip` from [Releases](../../releases) and extract it;
2. Double-click `安装汉化.bat` — it auto-locates the game, backs up your original `hlm2_data_desktop.wad` and `HotlineMiami2.exe`, then patches them in place;
3. Launch the game — Chinese shows under the default English language;
4. To revert: run `卸载汉化.bat`, or use Steam's "Verify integrity of game files".

All 2,889 in-game strings are translated; 1,343 CJK glyphs were injected into all 76 bitmap fonts. The executable receives a **length-safe in-place patch** for 121 hardcoded strings (23 achievement names + 42 descriptions + 56 level-editor UI labels) — file offsets are unchanged, Steam achievement IDs are preserved, and your original exe is backed up. Saves are never touched. Fan-made, unofficial, not affiliated with Dennaton Games or Devolver Digital.
