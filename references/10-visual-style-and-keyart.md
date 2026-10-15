# 10 画风：随角色而定（不自选、不预设）

> **H11：画风由用户提供的角色画风决定。** 本 skill 不提供"选一档"的默认画风，也不许替用户挑风格。
> 本文件的全部工作，是**把你看到的东西翻译成一条可逐镜复制的锁定块**。

## 1. 画风来源优先级（自上而下，命中即停）

| 序 | 来源 | 怎么做 | 可靠度 |
|---|---|---|---|
| **① 用户提供的角色图** | 最高 | **以图为准**。观察媒介、笔触、上色、光照、材质，逐项写进锁定块 | 最高 |
| **② 用户明写的画风词** | "水墨风""吉卜力""赛璐璐""UE5""真人实拍" | 原样采用，并按 §3 补齐同维度的其他描述 | 高 |
| **③ 用户提供的 IP** | 王者英雄 / 某动漫角色 / 某游戏 | **对齐原作画风**，不许换成自己顺手的风格 | 高 |
| **④ 描述中隐含的线索** | "手绘感""厚涂""水彩晕染""低多边形" | 提取为画风词，并在交付中标注「据描述推定」 | 中，需确认 |
| **⑤ 完全没有线索** | — | **必须问一次**："这个角色是哪种画风？（或给我一张参考图）" | — |

**唯一允许的自选**：用户明确说"你定"或"随便"时，才从 §4 的对照表挑一档，并注明是代选。

> C 类输入（只有名字）的 3 个反问里，画风问题**优先于其他两个**——没有画风就没法开工。

## 2. 看图六维度（拿到角色图就按这个拆）

| 维度 | 看什么 | 常用描述词 |
|---|---|---|
| **媒介** | 这是照片、绘画、3D、还是像素？ | live-action / 2D animation / 3D CGI / pixel art / stop-motion |
| **线稿与笔触** | 有没有描边？线是硬是软？笔触可见吗？ | clean line art / visible brush strokes / no outlines / sketchy lines |
| **上色方式** | 赛璐璐平涂、厚涂、渐变、水彩？ | cel-shading / painterly / soft gradient / watercolor bleed / flat color |
| **光照逻辑** | 写实光影、还是设计化打光？ | cinematic lighting / flat ambient / rim light only / Lumen GI |
| **材质质感** | 皮肤/布料的颗粒感、贴图感 | film grain / skin texture / matte / glossy / plastic |
| **镜头质感** | 景深、焦距、镜头畸变 | shallow DoF / 85mm / anamorphic / tilt-shift |

**拆完的结果就是锁定块。** 只写你**观察到**的东西，没观察到的不要补——补等于加噪。

## 3. 锁定块生成公式

```
[媒介] + [线稿/笔触] + [上色] + [光照] + [材质] + [镜头质感]
```

例（来自一张厚涂插画风的原创角色图）：
```
 painterly 2D animation, soft painterly brushwork with visible strokes,
 rich gradient shading, cinematic single-source lighting with soft falloff,
 matte fabric texture, subtle film grain, shallow depth of field, 50mm
```

### 锁定块四条纪律（同前，仍然成立）

1. **放在最前**：提示词第一个词就该是画风。
2. **逐镜一字不改**：换措辞 = 换画风。
3. **与该画风相邻的必禁词成对出现**（见 §5）。
4. **不与服务对象冲突**：写实片别写"能量粒子糊满屏"，厚涂插画片别追求照片级皮肤。

## 4. 常见画风对照表（**只用于归类和补词，不是菜单**）

用途：当你从图里认出了某个方向的线索，用这表补齐遗漏维度；或用户说"你定"时作为备选。

| 方向 | 典型锁定词 | 典型必禁词 |
|---|---|---|
| 真人实拍 / 电影感 | photorealistic live-action, shot on 35mm anamorphic, natural skin texture, film grain, cinematic color grading | anime, cel-shading, 3D render, CGI, illustration, plastic skin |
| 日式赛璐璐动画 | 2D anime, clean line art, cel-shading with soft gradients, vibrant color design | photorealistic, live action, painterly, thick outlines |
| 厚涂插画风 | painterly illustration style, visible brush strokes, rich gradients, textured canvas | flat color, clean line art, photorealistic, 3D render |
| 水墨 / 国风 | ink wash painting style, flowing brush strokes, ink bleed on rice paper, restrained palette | photorealistic, neon colors, heavy outlines, 3D render |
| UE5 / 高保真 CG | Unreal Engine 5 real-time render, PBR materials, Nanite detail, Lumen GI, volumetric fog | anime, cel-shading, rubber suit, low-poly, flat shading |
| 美漫 / 硬边卡通 | bold black outlines, flat color blocks, halftone, comic book style | photorealistic, soft gradients, no line art |
| 像素 / 低分辨率复古 | pixel art, limited palette, crisp pixel edges, retro game aesthetic | anti-aliased smooth edges, photorealistic, high-res render |
| 黏土 / 定格动画 | stop-motion claymation, tactile clay texture, visible fingerprints, practical lighting | smooth CGI, photorealistic plastic, clean surfaces |

> 这张表**不是八选一**。用户给图时永远以图为准；表只用来回答"这类画面通常还要写哪些词"。

## 5. 必禁词的生成规则

**禁什么**：禁的是**相邻的、容易把你这套画风带跑的媒介**——不是凭空罗列。

| 你的画风 | 该禁 | 理由 |
|---|---|---|
| 2D 动画 | photorealistic, live action, 3D render, CGI | 模型容易偷偷往写实滑 |
| 真人实拍 | anime, cel-shading, illustration, 3D render | 反过来同样会滑 |
| 3D CG | 2D anime, flat drawing, hand-drawn, stop-motion | 防降级成平面感 |
| 手绘厚涂 | flat cel-shading, clean line art, 3D render | 防退化成赛璐璐 |

**通用必禁**（所有画风都加）：`blurry, low resolution, jpeg artifacts, watermark, text, subtitle`

## 6. 画风一致性：全片一套，闪回也不例外

- 所有 clip 用**同一条锁定块**，逐镜复制。
- 闪回 / 回忆段**不许换画风**（换媒介 = 观众以为是另一部片子）。
- 闪回的时间层差异只用**三种手段**表达：
  1. 色温偏移（冷 / 暖）
  2. 饱和度与对比度
  3. 景深与颗粒（更柔、更重颗粒）
- 唯一允许改的两个词：`desaturated`、`cool/warm color grade`。**媒介、线稿、上色、光照逻辑一律不动。**

## 7. 角色设定图（Key Art）

展示片强依赖参考图（`07 §5`）。分两种情况：

| 情况 | 做法 |
|---|---|
| **用户已提供角色图** | 直接用。锁定块从这张图提取（§2）。**不许在此基础上"优化"画风**。 |
| **没有图，需要生成** | 先问画风（§1 ⑤），拿到后再出 Key Art。Key Art 提示词 = 锁定块 + 角色描述。 |

### Key Art 提示词结构

```
[从用户画风提取的锁定块]
+ 身份 / 年龄 / 性别
+ 外貌锚点（2–3 个，剪影可辨）
+ 服装与配色（主色 / 辅色）
+ 武器或标志道具
+ 姿态（与 S1 或 S3 的 Pose 对齐）
+ 表情与眼神（对应性格）
+ 背景（与主场一致，或纯色虚化便于复用）
+ 镜头参数（焦距 / 景深 / 光向明确）
+ 负面词（画面风必禁 + 通用 + 无字幕）
```

### Key Art 四条硬要求

| # | 要求 | 理由 |
|---|---|---|
| 1 | **外貌锚点全部可见** | 后续每 clip 靠它锚一致性 |
| 2 | **光向明确且单一** | 锁死色彩锚，防止换 clip 光漂 |
| 3 | **画面零文字** | 招牌 / 徽章 / UI 会在视频里变乱码（H10） |
| 4 | **姿态贴近 S1 或 S3** | 参考图与成片姿态差太远，模型会"纠正"你的 Pose |

## 8. 自检

- [ ] 画风来自用户提供的图 / 明写的词 / IP 原作，**不是我替他选的**
- [ ] 没有线索时已经问过用户，而非默认某档
- [ ] 锁定块写的是**观察到的事实**，没有追加没看到的词
- [ ] 必禁词对准了相邻媒介，不是随手罗列
- [ ] 全片（含闪回）用同一条锁定块，闪回只改冷暖与饱和
