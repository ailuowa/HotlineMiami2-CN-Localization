# Hotline Miami 2 简体中文汉化 / Chinese (Simplified) Localization

> 让《迈阿密热线 2：错号》的菜单、操作提示、HUD、对话、字幕、章节标题全部显示简体中文。
> 一键安装，无需改动任何游戏程序文件，随时可还原。

**适用版本**：Steam 版《Hotline Miami 2: Wrong Number》 ｜ **系统**：Windows 10 / 11

---

## ✨ 特性

- **2889 条文本全翻译**：游戏内全部英文文本（菜单 / 操作提示 / HUD / 对话 / 字幕 / 章节标题）均为简体中文，覆盖游戏全部剧情与玩法内容；
- **76 套字体注入 1340 个汉字字形**：原版字体不含任何中文字形（连自带日文都没有），本补丁为全部 76 套字体追加了中文字形，原版字形一个像素未动；
- **按键标记零错漏**：`[WASD]`、`[SPACE]`、`[LMB]` 等按键标记逐条自动比对，全部原样保留；
- **非破坏式注入**：只修改游戏资源包内的文本库与字体，不碰 exe、不碰存档、不联机（本游戏也无联机）；
- **一键安装 / 一键还原**：安装前自动备份，双击即可恢复英文原版。

## 📦 下载

前往 [**Releases**](../../releases) 页面下载最新的 `HotlineMiami2_简体中文汉化包.zip`。

## 🔧 安装

1. **完整解压**压缩包到一个文件夹（不要在压缩软件里直接运行）；
2. 双击 **`安装汉化.bat`**；
3. 安装器会自动定位 Steam 游戏目录并完成注入（约 10–30 秒）。

安装器会把你的原版文件备份为 `hlm2_data_desktop.wad.bak`，还原随时可行。

## 🎮 开始游戏

启动游戏即中文（默认英文语言下显示中文）。
若看到英文：**Options → Language → English**。

## ↩️ 还原英文原版

- 双击 **`卸载汉化.bat`**；或
- 在 Steam 中对游戏执行 **验证文件完整性**。

> 注意：Steam 验证完整性会把游戏恢复为英文原版（汉化消失）。想再玩中文，重新运行安装器即可。

## ❓ FAQ

**Q：安装器被 Windows SmartScreen / 杀毒软件拦截？**
安装器是免费开源的 PowerShell 脚本，未做数字签名，可能触发提示。选择「更多信息 → 仍要运行」即可；不放心可以先看源码再运行。

**Q：需要正版的 hotlinemiami2.exe 吗？**
是。本补丁只提供汉化数据并注入到**你自己购买安装的游戏**中，不包含、也不用于绕过任何正版验证。

**Q：其他版本（GOG / 学习版）能用吗？**
只测试过 Steam 版。理论上 WAD 结构一致即可使用，风险自负，欢迎反馈。

**Q：字体有点小 / 和原版像素风不一样？**
见下方「已知限制」。

## ⚠️ 已知限制

- 原版正文字体只有 8 像素高，中文在该尺寸无法辨认，汉化将其放大至约 12–14 像素并对齐原行高，笔画比原版粗体像素英文略细；菜单（约 20 像素）效果最好；
- 字体使用「黑体」（SimHei），与原版像素风不完全一致；
- 少数很长的对话行可能贴近文本框边缘。

## 🛠️ 技术原理（简）

游戏文本集中在资源包 `hlm2_data_desktop.wad` 内的 `Assets/hlm2_localization.bin`（自定义二进制格式，10 种语言 × 3247 条，UTF-8）；字体为 BMFont XML + 8-bit 灰度字形图集。本补丁将中文文本库与追加中文字形后的字体**原位注入** WAD（新数据追加到文件末尾并改写对应条目索引，其余数千个文件字节级不动）。注入器在发布前经过逐字节比对验证。

## 📄 免责声明

本项目为粉丝制作的非官方汉化，与 Dennaton Games / Devolver Digital 无关。仓库与发布包**不包含任何官方游戏资源文件**——仅包含补丁数据（翻译文本与派生字体）和安装脚本，且仅供已合法购买游戏的玩家使用。请支持正版。使用本补丁产生的任何问题由使用者自行承担。

---

## English Quick Start

Simplified Chinese localization for the Steam version of Hotline Miami 2: Wrong Number.

1. Download `HotlineMiami2_简体中文汉化包.zip` from [Releases](../../releases) and extract it;
2. Double-click `安装汉化.bat` — it auto-locates the game, backs up your original `hlm2_data_desktop.wad`, and patches in the Chinese text library + CJK fonts;
3. Launch the game — Chinese shows under the default English language (you can also pick the new "Chinese (Simplified)" entry if it appears);
4. To revert: run `卸载汉化.bat`, or use Steam's "Verify integrity of game files".

All 2,889 in-game strings are translated; CJK glyphs were injected into all 76 bitmap fonts. No executable or save files are touched. Fan-made, unofficial, not affiliated with Dennaton Games or Devolver Digital.
