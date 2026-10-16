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
  <img src="https://img.shields.io/badge/LICENSE-MIT-16A34A?style=for-the-badge&labelColor=555555" alt="License MIT">
</p>

<p align="center">
  <a href="#画面特点">画面特点</a> ·
  <a href="#安装">安装</a> ·
  <a href="#使用">使用</a> ·
  <a href="#出图方式">出图方式</a> ·
  <a href="#目录">目录</a> ·
  <a href="#欢迎晒图">晒图</a> ·
  <a href="#许可">许可</a>
</p>

---

## 画面特点

- **80 年代赛璐璐画风**：把主体重绘成《轨道双子星 / Orbitals》的老动画质感，不是给照片套滤镜。
- **游戏界面元素**：章节标题、拟声词、对白字幕、任务 HUD、头像卡，按画面需要组合。
- **多层交叠的小窗口**：4–5 个大小不一、错位叠压的界面窗口，其中 1–2 个是主体的局部特写；窗口内容跟着主体走，不套固定模板。
- **内框 + 纯黑外底**：主画面放在内框里，框外统一纯黑；画框和小窗口的尺寸、边框粗细参考 `assets/frame-size-reference.png`。
- **越框与鱼眼**：主体的一部分从不同方向越过并遮住边框，形成空间层次；框内带轻微鱼眼弯曲，人物和文字保持清晰。
- **安静的背景**：低对比、少细节、留白充足，让主体和界面成为视觉重点。
- **默认宇宙场景**：深空、行星轨道、空间站、小行星地表等，星空稀疏克制。
- **默认日文对白**：底部对白和说话人标签用日文。
- **默认 4:3 横版**：改画幅时拓展并重排画面，不拉伸主体、不裁掉关键内容。

以上都是默认值，你在请求里指定的文字、语言、场景和比例优先。

## 安装

在具备内置生图工具的 Codex 环境中使用。以下命令会下载完整的工作流、脚本、参考文档和全部图片素材，不需要逐个复制文件。

### 用 Git 安装（推荐）

在终端运行（macOS / Linux）：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/yesyflami/flami-orbitals-skill.git ~/.agents/skills/flami-orbitals-skill
```

`~/.agents/skills/` 是 Codex 官方支持的用户级 Skill 目录。Windows 用户可把完整文件夹放在 `%USERPROFILE%\.agents\skills\flami-orbitals-skill`。

如果目标目录已经存在，不要重复 clone；用下面的命令更新 Git 安装的版本：

```bash
git -C ~/.agents/skills/flami-orbitals-skill pull --ff-only
```

如果你之前已安装在 `~/.codex/skills/` 且 Codex 能识别它，可以继续使用原目录；避免在不同目录重复安装同名 Skill。

### 用 ZIP 安装

在本仓库页面点击 **Code → Download ZIP**，解压后把仓库根目录重命名为 `flami-orbitals-skill`，将完整文件夹放进 `~/.agents/skills/`。确认 `SKILL.md` 直接位于该文件夹下，`assets/`、`references/`、`scripts/`、`agents/` 与它同级。不要只复制 `SKILL.md`，也不要漏掉素材。

安装后在 Codex 中新开一个对话；如果没有发现 Skill，重启 Codex。在支持 Skill 选择器的界面中输入 `$` 并选择 `flami-orbitals-skill`，也可以直接在消息里写出 Skill 名称。

官方说明：[Codex Skills](https://developers.openai.com/codex/skills/)。

## 使用

### 复制这条 Prompt 即可测试

安装完成后，在 Codex 中上传一张你想重绘的照片，再复制发送：

```text
请使用 $flami-orbitals-skill，把我上传的这张照片生成一张《轨道双子星 / Orbitals》风格的游戏画面。严格读取并遵循这个 Skill 的 SKILL.md 和参考文档，保留人物或主体的辨识特征，采用 80 年代赛璐璐画风，使用默认的 4:3 横版、宇宙场景、纯黑外底、内框、越框效果、大小不一且交叠的功能面板，以及日文对白。其余构图、章节标题和任务内容由你按 Skill 选择，只生成一张图片。使用 Skill 优先指定的 Codex 内置生图工具，不修改 Skill、脚本或 API 配置；如果该工具不可用或失败，请说明原因并停止，不要自行切换 API。生成后展示图片，并告知保存路径、实际尺寸及明显偏差。
```

不用照片也可以，直接把主体描述清楚，例如：

```text
请使用 $flami-orbitals-skill，画一只戴着圆框眼镜、举着咖啡杯的橘猫宇航员，在太空站控制室值夜班。其余按 Skill 默认流程选择，只生成一张。使用 Codex 内置生图工具，不修改 Skill 或 API 配置；不可用或失败时停止并说明原因。展示图片并告知保存路径。
```

想调整画面时，可以在 Prompt 后补充：

- 色调：红幕菜单 / 深空极光 / 遗迹森林 / 熔炉 / 金色漩涡 / 跃迁霓虹 / 控制室。
- 版式：章节标题卡 / 角色切入 / 道具获得 / 双人分屏 / 主菜单 / 对话特写。
- 比例：4:3（默认）/ 16:9 / 竖版 / 方形；需要具体比例时请明确写出。
- 场景、标题和对白：明确指定即可；你给出的文字与语言优先。

完整仓库让大家使用相同的工作流和素材；生成结果仍会随模型、工具能力和随机性变化，不保证每次得到完全相同的图片。最终尺寸以实际输出为准。

## 出图方式

1. **Codex 内置生图工具（优先）**：工具可用时按 Skill 直接调用，无需为内置工具另配 `OPENAI_API_KEY`。不同 Codex 环境提供的工具可能不同，安装 Skill 本身不会增加生图权限。
2. **仓库自带脚本（备用）**：Skill 原文规定，没有内置工具时可使用 `scripts/generate.py` 调用 OpenAI Images API。需要 Python 3 和 `OPENAI_API_KEY`，脚本只使用 Python 标准库。上面的测试 Prompt 要求不可用时停止，因此不会自行切换到这条路径。

仓库保留原有脚本和 API 行为：默认模型为 `gpt-image-1`，可通过 `OPENAI_IMAGE_MODEL` 指定模型、`OPENAI_BASE_URL` 指定兼容服务地址。密钥请仅在自己的环境中配置，不要写入仓库或聊天消息。脚本支持的横版尺寸为 1536×1024（3:2），并非默认目标 4:3；使用脚本时应如实说明尺寸偏差。

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

## 欢迎晒图

用这个 skill 画出了满意的图？欢迎到 [Issues](https://github.com/yesyflami/flami-orbitals-skill/issues) 发出来，顺便说说用了什么主体、色调和版式。效果不理想、文字乱码或者有改进想法，也欢迎在那里反馈。

这个 skill 不会向作者回传任何数据：你的照片、描述和生成的图片只会发给你自己使用的生图服务（Codex 或 OpenAI），作者看不到。

## 许可

本仓库的文档和脚本以 [MIT 许可证](LICENSE) 发布，可自由使用、修改和再发布，保留署名即可。

`assets/style-refs/` 中的图片是游戏截图，版权归原游戏所有，不在 MIT 授权范围内。

## 贡献者

- [yesyflami](https://github.com/yesyflami)
