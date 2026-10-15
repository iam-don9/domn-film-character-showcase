# 06 一致性三锚点与负面词

## 1. 三锚点（每镜至少一个清晰可见）

| 锚点 | 内容 | 写法要求 |
|---|---|---|
| **外貌锚** | 2–3 个不变特征（发型 / 武器 / 瞳色 / 义体 / 伤疤 / 服装轮廓） | 写进**每一镜提示词的首句**，**措辞逐镜完全一致** |
| **能力锚** | 招牌技的**颜色 + 形状 + 运动方向** | 每镜保持同一色值与运动特征 |
| **色彩锚** | 主色 + 辅色 + 光源方向 | 全片统一单侧主光，**不许中途换色温 / 换光向** |

**锚点写法示例**（逐镜复制，一字不改）：
```
a young swordsman in a white robe with long black hair, carrying a slender straight blade
```

## 2. 锚点失效的三种典型

| 症状 | 原因 | 处方 |
|---|---|---|
| 每镜长得不一样 | 外貌描写逐镜换了措辞 | 建一条**锚点串**，逐镜粘贴 |
| 特效一上来就认不出人 | 特效占比过高 | 特效 ≤ 画面 40%，主体轮廓始终可见 |
| 换 clip 后衣服变色 | 色彩锚没写进提示词 | 主色 / 辅色 / 光向写进每镜结尾 |

## 3. 通用负面词（默认基线，逐镜追加）

```
人物变形、五官崩坏、多手多脚、手指粘连、面部模糊、身份不一致、服装突变、
武器变形、武器消失、背景闪烁、镜头漂移、主体出画、多人主体、与敌人对打、
低分辨率、过曝、塑料感、慢动作拖影、色彩跳变、光源方向突变
```

### 无字幕负面词（H10，**逐镜必带**）

中文：
```
字幕、硬字幕、烧录字幕、台词条、花字、标题卡、片名、文字、文字覆盖层、
UI 界面、招牌文字、乱码字符、水印、角标
```

EN：
```
subtitle, caption, subtitles, burned-in text, hardcoded text, text overlay,
title card, lower third, typography, lettering, on-screen text, UI text,
garbled characters, watermark, logo
```

### 按原型追加

| 原型 | 追加负面词 |
|---|---|
| P1 王者归来 | 姿势不稳定、Pose 崩坏、技能特效缺失 |
| P2 华丽炫技 | 动作断裂、落地停顿、慢动作拖影 |
| P3 角色独白 | 口型不同步、嘴部遮挡、字幕 |
| P4 一击定生死 | 追加挥砍、多余动作、节奏拖沓 |
| P5 元素爆发 | 爆发后不收、全屏过曝、元素粒子糊住主体 |
| P6 挑衅爆发 | 表情凶恶、反派化 |
| P7 压迫登场 | 灵活动作、跳跃、体量变小 |
| P8 反差日常 | 切换无触发、两段质感趋同 |

### 按画风追加（**必带**，来自 `10 §5`）

画风必禁词**不是从菜单里挑的**，是从用户的角色画风推出来的——禁的是**相邻媒介**（会把这套画风带跑的那几种）。

通用（所有画风都加）：
```
blurry, low resolution, jpeg artifacts, watermark, text, subtitle
```

再按用户的画风方向补一组：

| 用户的画风 | 追加负面词 |
|---|---|
| 2D 动画 / 赛璐璐 | photorealistic, live action, 3D render, CGI, painterly thickness |
| 真人实拍 | anime, cel-shading, illustration, 3D render, plastic skin |
| 3D / CG | 2D anime, flat drawing, hand-drawn, stop-motion, low-poly |
| 手绘厚涂 | flat cel-shading, clean line art, 3D render, glossy plastic |
| 水墨 / 国风 | photorealistic, neon colors, heavy outlines, 3D render |
| 像素 / 复古 | smooth anti-aliased edges, photorealistic, high-res render |
| 黏土 / 定格 | smooth CGI, glossy plastic, clean surfaces |

> 用户的画风不在表里时，用同一条规则自己推：**禁掉它最容易滑向的那一两种媒介**，而不是照抄上表。
