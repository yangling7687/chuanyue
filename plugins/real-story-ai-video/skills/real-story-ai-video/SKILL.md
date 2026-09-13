---
name: real-story-ai-video
description: 制作真实故事 AI 短视频生产包，支持固定 10 秒版和固定 15 秒版。启动时必须先询问用户选择版本，再读取对应提示词包执行。
metadata:
  short-description: 真实故事 AI 短视频 10 秒/15 秒双版本工作流
---

# 真实故事 AI 短视频制作

## 启动选择

每次用户启动本 skill 时，先询问：

```text
请选择视频版本：
1. 10 秒版
2. 15 秒版
```

在用户选择前，不开始生成阶段内容。用户回复“10秒”“10 秒版”“1”时，读取并严格执行 `references/real_story_ai_video_prompt_pack_10s.md`；用户回复“15秒”“15 秒版”“2”时，读取并严格执行 `references/real_story_ai_video_prompt_pack_15s.md`。

如果用户在启动消息中已经明确指定版本，则无需重复询问，直接使用对应版本。

## 执行规则

- 只使用用户选择的版本，不混用另一版本的时长或时间区间。
- 10 秒版的每个 Seedance 片段固定 10 秒，默认区间为 `[0-4秒]`、`[4-8秒]`、`[8-10秒]`。
- 15 秒版的每个 Seedance 片段固定 15 秒，默认区间为 `[0-3秒]`、`[3-7秒]`、`[7-11秒]`、`[11-15秒]`。
- 角色声线必须结合角色人设进行固定描述，并在后续所有 Seedance 片段中保持一致。
- 生成阶段内容时，遵循所选提示词包中的阶段顺序、用户确认机制和门禁规则。

## 资源

- [10 秒版提示词包](references/real_story_ai_video_prompt_pack_10s.md)
- [15 秒版提示词包](references/real_story_ai_video_prompt_pack_15s.md)
