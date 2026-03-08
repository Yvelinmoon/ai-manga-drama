# 提示词模板

---

## 分镜图（make-image）

### 提示词结构

```
[艺术风格] + [景别关键词] + [场景：谁在做什么、在哪里] + [角色核心外貌] + [情绪/表情] + [背景/环境] + [光影氛围]
```

**顺序说明：** 艺术风格和景别放在最前面，接着描述这个场景发生了什么，最后才是角色外貌细节和氛围。

---

### 景别关键词

| 景别 | 关键词 |
|------|--------|
| 大远景 | `wide establishing shot, vast landscape, tiny silhouette` |
| 远景 | `wide shot, full environment visible` |
| 全景 | `full body shot, character and background both visible` |
| 中景 | `medium shot, waist up` |
| 近景 | `close-up portrait, shallow depth of field, bokeh background` |
| 特写 | `extreme close-up of [face/hand/object]` |

---

### 艺术风格关键词

| 风格 | 关键词 |
|------|--------|
| 日漫 | `anime illustration, vibrant colors, cel shading, clean linework` |
| 国漫/古风 | `Chinese animation style, ink wash aesthetic, flowing traditional robes` |
| 写实动漫 | `semi-realistic anime, cinematic lighting, highly detailed, 8k` |
| 赛博朋克 | `cyberpunk anime, neon lights, dark city, holographic effects` |
| 温情治愈 | `soft anime illustration, pastel colors, warm lighting, watercolor feel` |
| 热血少年 | `shonen manga style, dynamic composition, bold linework, high contrast` |

---

### 情感节拍 → 光影映射

| 情感节拍 | 光影描述 |
|----------|----------|
| 希望/决心 | `sunlight breaking through clouds, warm golden rays, rim lighting` |
| 悲伤/孤独 | `grey overcast, cold flat light, no strong shadows, muted colors` |
| 紧张/对抗 | `sharp side lighting, deep shadows on half face, high contrast` |
| 温情/信任 | `warm soft candlelight, intimate close framing, gentle amber glow` |
| 权威/威压 | `dramatic low angle, cold blue-white light, deep background shadow` |
| 迷茫/恐惧 | `cold moonlight, long shadows, dutch angle, desaturated colors` |
| 高潮/爆发 | `magical energy crackling, blue-white flash, cinematic lens flare` |
| 告别/余韵 | `golden hour backlight, silhouette, soft lens flare, warm farewell` |

---

### 分镜图常见误区

| ❌ 错误做法 | ✅ 正确做法 |
|------------|------------|
| 先写角色外貌，再写场景 | 先写艺术风格和景别，再写场景，最后写外貌 |
| 同一场景两个镜头背景措辞不同 | 逐字复用相同背景描述，只改前景细节 |
| 没有指定景别 | 必须有明确的景别关键词 |
| 角色外貌描述每个镜头不同 | 抽取一段固定外貌描述串，每个镜头粘贴 |

---

### 示例（古风言情，近景，悲伤节拍）

```
Chinese animation style, close-up portrait, shallow depth of field,
a young woman about to speak but holding back her words,
long black hair pinned with jade ornament, soft teary eyes, pale skin, light blue hanfu with silver embroidery,
blurred traditional garden background with red lanterns,
grey overcast cold flat light, muted colors, melancholy atmosphere,
high quality, cinematic
```

---

## 视频动态（make-video）

### 单镜头提示词结构

```
[主体 + 身份细节] 在 [环境/场景] 中。
主要动作：[单一具体动作，使用"缓缓/轻轻/慢慢"控制幅度]。
次要动作：[可选，发丝/衣物/背景的辅助动态]。
镜头：[运镜类型，如固定机位/缓慢推近/缓慢拉远]。
声音：[直接复制全集音频设计单内容；有台词时加：人物台词："XXX"（语气备注）]。
约束：保持 [发型/背景/服装颜色] 稳定，避免面部变形。
```

**核心原则：**
- 只描述动态，不重复图片中已有的静态内容
- 每个镜头只做**一件事**
- 声音字段必须填写，不可留空

---

### 多分镜提示词结构（--multi-shots）

将 2-3 个同场景镜头合并为一条视频，wan2.6 会自动处理镜头之间的切换。

```
【整体风格】[全集美术风格关键词]，[色调基准]，[整体光影氛围]。

【分镜1（0-Xs）】
景别：[景别] [角度]
画面：[主体做什么，在哪里]
动作：[单一动作描述]
声音：[环境音 / 台词 / 无背景音乐]

【分镜2（Xs-Ys）】
景别：[景别] [角度]
画面：[主体做什么]
动作：[单一动作描述]
声音：[环境音 / 台词 / 无背景音乐]

【分镜3（Ys-Zs）】（可选）
景别：[景别] [角度]
画面：[主体做什么]
动作：[单一动作描述]
声音：[环境音 / 台词 / 无背景音乐]
```

**时间分配参考：**
- 2 个分镜：各约 5-7s（总 10-14s）
- 3 个分镜：约 4s + 4s + 5s（总 13s，不超过 15s 上限）
- 每个分镜内只写一个主要动作

**多分镜示例（战斗场景，2分镜）：**
```
【整体风格】anime illustration, cel shading, high contrast，冷蓝紫色调，战场光影。

【分镜1（0-6s）】
景别：中景 平视
画面：女特工站于废墟之中，目视前方
动作：缓缓抬起手中双枪，指向远处，表情冰冷坚定
声音：远处爆炸余震与防空警报的环境底噪，无背景音乐。

【分镜2（6-13s）】
景别：近景 仰角
画面：女特工面部特写，眼神
动作：眼眸微微收缩，嘴唇轻轻张开说出台词
声音：室内静谧环境音，人物台词："战争，从不等人。"（语气低沉，带着疲倦），无背景音乐。
```

---

### 声音字段标准写法

> ⚠️ **重要：** BGM 在 merge-video 阶段统一混入，单段视频提示词中**严禁要求生成背景音乐**。
> 声音字段只写：环境音 + 对白。

**无台词镜头：**
```
声音：战场远处炮声与防空警报的环境底噪，无背景音乐。
```

**有台词镜头：**
```
声音：室内安静环境音，人物台词："你来了。"（语气平静，带一丝苦涩），无背景音乐。
```

**特殊音效镜头（高潮/转折）：**
```
声音：单一枪响音效，随后静默，无背景音乐。
```

---

### 按景别推荐的动态措辞

**大远景 / 远景**
```
云层缓缓流动，光线角度随云影轻微变化。
远处有模糊的飞鸟掠过画面边缘。
```

**全景**
```
角色深呼吸，胸部轻微起伏，发丝随风缓缓飘动。
角色缓缓抬起头，目光投向画面外。
```

**中景（无台词）**
```
角色慢慢转头望向一侧，眼神坚定。
角色轻轻叹气，肩膀略微下沉。
```

**中景（有台词）**
```
角色开口说话，嘴唇轻微动动，说话时眼神温柔。
固定机位，角色说完后沉默片刻，视线缓慢移开。
```

**近景**
```
眼眶缓缓泛红，一滴泪水慢慢沿脸颊滑落。
角色轻轻咬唇，嘴角微微颤动。
```

**特写**
```
眼睛缓缓眨动，瞳孔微微收缩。
手指轻微颤抖，缓缓握紧后松开。
```

---

### 视频动态常见误区

| ❌ 错误做法 | ✅ 正确做法 |
|------------|------------|
| 声音字段为空或"无" | 每个镜头必须填写声音描述 |
| 不同镜头 BGM 措辞不同 | 所有镜头的 BGM 措辞逐字相同 |
| 一个镜头描述3个以上动作 | 只描述1个主要动作 + 最多1个辅助动态 |
| 动作幅度过大（跑/跳/打斗） | 加"缓缓/轻轻/慢慢"，幅度适中 |
| 重复图片里已有的静态描述 | 只写图片里没有的：动态与声音 |
