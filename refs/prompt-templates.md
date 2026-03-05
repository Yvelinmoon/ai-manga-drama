# 提示词模板库

适用于 `ai-manga-drama` 技能的 Step 3（分镜图）和 Step 4（视频动态）提示词构建。

---

## 一、提示词通用结构

### 图片提示词（make-image）

```
[角色一致性描述] + [本镜头姿势/动作] + [背景/场景] + [光影/氛围] + [艺术风格关键词]
```

### 视频动态描述（make-video）

```
[单一动作描述] + [速度修饰词] + [辅助动态（衣物/发丝/背景）]
```

---

## 二、艺术风格关键词

| 风格 | 图片提示词关键词 |
|------|----------------|
| 日漫 | `anime style, detailed illustration, vibrant colors, cel shading` |
| 国漫/古风 | `Chinese animation style, ink wash painting, flowing robes, traditional aesthetic` |
| 写实动漫 | `semi-realistic anime, detailed facial features, cinematic lighting, 8k quality` |
| 赛博朋克 | `cyberpunk anime, neon lights, dark city, holographic effects, futuristic` |
| 童话/奇幻 | `fantasy illustration, magical atmosphere, soft glow, fairy tale style` |
| 都市现代 | `modern anime style, urban setting, clean lines, fashion-forward character design` |
| 热血少年 | `shonen anime style, dynamic composition, bold linework, high energy` |

---

## 三、景别提示词模板

### 大远景（Extreme Wide Shot）
```
[环境描述，角色不可见或极小], vast landscape, establishing shot,
cinematic wide angle, [天气/时间], [氛围关键词],
[艺术风格], high quality, detailed background
```

**示例：**
```
ancient chinese city at twilight, vast landscape, pagodas and lanterns,
rivers reflecting golden light, establishing shot, cinematic wide angle,
misty atmosphere, Chinese animation style, high quality, detailed background
```

---

### 全景（Full Shot）
```
[角色完整外貌描述], full body shot, [姿势描述],
[背景环境], [光影描述], [氛围],
[艺术风格], high quality
```

**示例：**
```
18-year-old girl with silver twin-tails hair and purple eyes, wearing black school uniform
with red bow, full body shot, standing confidently on rooftop,
city skyline at night, rim lighting, cool blue atmosphere,
anime style, high quality
```

---

### 中景（Medium Shot）
```
[角色核心外貌：发型+眼睛+服装], medium shot waist up, [表情/情绪],
[动作], [背景环境简要], [光影],
[艺术风格], high quality
```

**示例：**
```
silver twin-tails girl purple eyes black school uniform, medium shot waist up,
determined expression, clenching fist, blurred school corridor background,
soft afternoon light, anime style, high quality
```

---

### 近景（Close-up）
```
[角色核心外貌], close-up portrait, [情绪表达], [眼神描述],
[背景虚化], [光影特写效果], [艺术风格], high quality
```

**示例：**
```
silver twin-tails girl purple eyes, close-up portrait, tearful but resolute expression,
glistening eyes, bokeh background, warm backlighting,
detailed anime portrait, high quality
```

---

### 特写（Extreme Close-up）
```
extreme close-up of [具体部位：hand/eye/face/object], [细节描述],
[背景完全虚化], [光影聚焦], [艺术风格]
```

**示例：**
```
extreme close-up of girl's eye with silver eyelashes, reflecting city lights,
single tear forming, bokeh background, dramatic lighting,
detailed anime illustration, high quality
```

---

## 四、不同情感场景的氛围词汇

| 情感 | 光影 | 色调 | 氛围关键词 |
|------|------|------|----------|
| 希望/决心 | 逆光、阳光从云中射出 | 暖橙、金色 | `hopeful, golden hour, rays of light` |
| 悲伤/孤独 | 阴天、冷白光 | 冷蓝、灰 | `melancholy, overcast, cold atmosphere` |
| 紧张/对抗 | 强侧光、阴影 | 高对比黑白 | `tense, dramatic shadow, high contrast` |
| 温情/浪漫 | 柔光、暖色调 | 粉、米黄 | `warm, soft lighting, cozy atmosphere` |
| 惊喜/震撼 | 强烈背光、爆炸感 | 鲜艳高饱和 | `stunning, dramatic, vibrant colors` |
| 神秘/悬疑 | 低调光、局部高光 | 深蓝、紫 | `mysterious, dark atmosphere, moody lighting` |

---

## 五、视频动态提示词模板（make-video / wan2.6）

### 按景别推荐动态

**大远景 / 远景**
```
云层缓缓流动，光线角度慢慢变化
灯光缓缓闪烁，远处有轻微雾气飘动
```

**全景**
```
角色深呼吸，胸部轻微起伏，发丝随风缓缓飘动
裙摆轻轻摆动，角色缓缓抬起头
```

**中景**
```
角色缓缓开口，嘴唇轻微动动（有台词时）
角色慢慢转头看向一侧，眼神坚定
角色叹气，肩膀略微下沉
```

**近景**
```
角色温暖微笑，眼角微微上扬
眼眶缓缓泛红，一滴泪水慢慢滑落
角色轻轻咬唇，眼神闪烁
```

**特写**
```
眼睛缓缓眨动，瞳孔微微收缩
手指轻微颤抖，握紧后松开
```

---

### 按情感推荐动态

| 情感 | 视频动态描述 |
|------|------------|
| 决心 | `角色缓缓抬头，眼神由柔和转为坚定，嘴角微微收紧` |
| 悲伤 | `眼眶缓缓泛红，泪水慢慢聚集，角色轻轻垂下目光` |
| 惊讶 | `眼睛缓缓睁大，嘴唇微微张开，身体轻微后仰` |
| 温柔 | `角色轻轻微笑，眼睛弯成月牙形，发丝缓缓飘动` |
| 紧张 | `角色缓缓咽了一口唾沫，眼神四处扫视，手指轻微抖动` |
| 震撼 | `角色缓缓抬起头，瞳孔颤抖，光芒在眼中闪烁` |

---

## 六、快速构建示例（完整镜头）

### 古风言情 - 近景镜头

**图片提示词：**
```
elegant young woman with long black hair pinned up with jade hairpin,
wearing flowing hanfu dress in pale blue and gold, close-up portrait,
gentle melancholy expression, teary eyes,
blurred traditional chinese garden background, soft lantern light,
Chinese animation style, ink wash aesthetic, high quality
```

**视频动态（make-video）：**
```
眼眶缓缓泛红，一滴泪水慢慢沿脸颊滑落，发丝轻柔地随风飘动
```

---

### 热血都市 - 全景镜头

**图片提示词：**
```
teenage boy with spiky black hair and sharp amber eyes, wearing torn school uniform,
full body shot, battle stance with fist raised,
dramatic debris and dust around him, glowing energy effects,
strong rim lighting, intense atmosphere,
shonen anime style, dynamic composition, high quality
```

**视频动态（make-video）：**
```
角色深吸一口气，拳头缓缓握紧，周围的能量光芒轻轻波动
```

---

### 悬疑现代 - 特写镜头

**图片提示词：**
```
extreme close-up of young woman's eyes, sharp calculating gaze,
dark eye shadow, city neon lights reflected in pupils,
rain droplets on eyelashes, deep shadow on one side,
noir anime style, cinematic, high quality
```

**视频动态（make-video）：**
```
眼睛缓缓眨动，瞳孔中的霓虹倒影微微闪动，眼神慢慢移向画面左侧
```
