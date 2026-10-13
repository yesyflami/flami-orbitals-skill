<p align="center">
  <img src="assets/banner.webp" alt="flami-orbitals-skill" width="100%">
</p>

<h1 align="center">轨道双子星 · flami-orbitals-skill</h1>

<h3 align="center">让任何主体都成为游戏里的一帧</h3>

<p align="center">
  把一张照片或一句描述交给 Agent，说一句你想画什么。<br>
  自动重绘成《轨道双子星 / Orbitals》的 80 年代赛璐璐画风，并配上章节标题、对白字幕、任务 HUD 与特写小窗。
</p>

<p align="center">
  <img src="https://img.shields.io/badge/VERSION-3.0-E8443A?style=for-the-badge&labelColor=555555" alt="Version 3.0">
  <img src="https://img.shields.io/badge/CODEX-SKILL-0D1B2A?style=for-the-badge&labelColor=555555" alt="Codex Skill">
  <img src="https://img.shields.io/badge/CLAUDE%20CODE-SKILL-2563EB?style=for-the-badge&labelColor=555555" alt="Claude Code Skill">
</p>

<p align="center">
  <a href="#画面特点">画面特点</a> ·
  <a href="#安装">安装</a> ·
  <a href="#使用">使用</a> ·
  <a href="#出图方式">出图方式</a> ·
  <a href="#目录">目录</a>
</p>

---

## 画面特点

把一张照片或一句描述，变成《轨道双子星 / Orbitals》游戏画面风格的插画：80 年代赛璐璐动画画风 + 游戏里的章节标题、拟声词、对话字幕、任务 HUD、头像卡等界面元素。构图采用：一个主体 + 多层叠压的界面元素 + 局部特写小窗 + 围绕主体新增的世界观元素。

默认采用大小不同、错位交叠的游戏界面窗口，搭配局部特写；背景保持低对比、少细节和足够留白。底部对白及说话人标签默认使用日文，用户指定的文字和语言优先。每张图根据主体选择窗口内容，不固定套用足球示例。

新增默认画面规则：内边框之外统一纯黑底；主体或相关元素在不同方向局部越框，以遮挡边框形成空间层次；框内加入轻微鱼眼弯曲，保持人物和文字清晰。默认画幅为横向 4:3，用户明确指定其他比例时按请求执行。主画框及所有小窗口的尺寸和边框粗细统一参考 `assets/frame-size-reference.png`，具体比例见 `references/composition.md`。默认把场景放在宇宙中（深空、行星轨道、空间站、小行星地表等），星空保持稀疏克制，用户指定其他场景时以指定为准。改画幅优先拓展和重排，不拉伸主体或裁掉关键内容。

## 安装

本地 ZIP 安装：解压后将完整的 `flami-orbitals-skill` 文件夹放入 `~/.codex/skills/`（Codex）或 `~/.claude/skills/`（Claude Code）。可直接修改本地文件并重新打包，无需 Git 提交。


**Codex**

```bash
git clone https://github.com/yesyflami/flami-orbitals-skill.git ~/.codex/skills/flami-orbitals-skill
```

**Claude Code**

```bash
git clone https://github.com/yesyflami/flami-orbitals-skill.git ~/.claude/skills/flami-orbitals-skill
```

## 使用

- 「把这张照片做成轨道双子星风格」
- 「画一张轨道双子星风格的橘猫，用熔炉色调、道具获得版式」

可选指定：
- 色调：红幕菜单 / 深空极光 / 遗迹森林 / 熔炉 / 金色漩涡 / 跃迁霓虹 / 控制室
- 版式：章节标题卡 / 角色切入 / 道具获得 / 双人分屏 / 主菜单 / 对话特写
- 比例：4:3（默认）/ 16:9 / 竖版 / 方形
- 场景：宇宙（默认）/ 自行指定

## 出图方式

1. 环境自带生图工具（如 Codex）时直接使用；
2. 否则使用 `scripts/generate.py` 调用 OpenAI Images API（仅需 Python 标准库），需设置 `OPENAI_API_KEY`。

## 目录

```
SKILL.md                     工作流
references/style-guide.md    画风 / 配色 / 字体 / 质感
references/composition.md    构图层级、六种版式、变化规则
assets/style-refs/           风格参考图（游戏截图，版权归原游戏所有，后续将替换为自制示例）
assets/frame-size-reference.png  画框与小窗口的尺寸参考图
scripts/generate.py          OpenAI 出图脚本
agents/openai.yaml           Codex 界面元数据
```
