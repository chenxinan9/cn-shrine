---
name: 读视频
version: 0.1.0
---

# 读视频 SKILL · 三段式视频理解

## ⚠️ 前置依赖(用户需自装)

| 工具 | 装法(macOS/Linux/Win)| 验装 |
|---|---|---|
| **ffmpeg** ≥ 6.0 | macOS: `brew install ffmpeg` / Linux: `apt install ffmpeg` / Win: 见 [ffmpeg.org](https://ffmpeg.org) | `ffmpeg -version` |
| **whisper**(本地 STT)| `pip install openai-whisper`(需 Python 3.9+ + ffmpeg)| `whisper --help` |
| **yt-dlp**(站点下载)| `pip install yt-dlp` 或 `brew install yt-dlp` | `yt-dlp --version` |
| **Claude vision** | Claude Code 内置(无需装)| 自动可用 |

→ 3 个工具任 1 缺 = 对应轨道不可用 · 但其他轨道仍可跑 · 跑前自验

---

## 1 · 触发场景(7 类通用)

| 派 | 场景 |
|---|---|
| **沙僧**(网页 DESIGN)| 客户/竞品 UI 录屏审 |
| **白龙**(营销) | 抖音/小红书/B 站 营销视频拆解 |
| **凤凰**(品牌)| 视觉品牌片解析 + 国际同源 |
| **文昌**(知识) | 教程视频 + 公开课 + 演讲转录沉淀 |
| **二郎神**(选型) | 工具演示视频审 |
| **唐僧**(5 指总管) | 5 子开发录屏汇报 |

---

## 2 · 三段式 Pipeline(三轨 · 选最快 · 兜底齐)

### 轨 1 · 字幕优先(快 · 零 STT 成本)

```bash
# YouTube / B 站 / 多数平台 · 拉视频自带字幕
yt-dlp --write-sub --sub-langs "zh,en,zh-CN,zh-Hans,zh-TW" \
 --skip-download \
 --sub-format "vtt/srt/best" \
 "<URL>" -o "/tmp/video-sub.%(ext)s"

# 字幕真物
cat /tmp/video-sub*.vtt 2>/dev/null || cat /tmp/video-sub*.srt 2>/dev/null
```

→ **优先用** · 平台官方字幕 · 准 · 反 STT 错

### 轨 2 · 音频转写(无字幕兜底 · whisper STT)

```bash