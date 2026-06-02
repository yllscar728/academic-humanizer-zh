# academic-humanizer-zh

`academic-humanizer-zh` is a Codex skill for reducing AI-generated writing patterns in Chinese academic text while preserving meaning, terminology, argument structure, and academic tone.

`academic-humanizer-zh` 是一个面向中文学术写作场景的 Codex skill，专用于对论文、研究报告、毕业论文与 MBA 论文文本进行“降 AI”改写。

本项目的目标，不是对文本进行泛化润色或风格美化，而是在尽可能保留原意、术语、论证结构、事实口径与学术风格的前提下，降低机器生成痕迹，使文本呈现出更自然、更克制、更符合真实作者写作习惯的中文学术表达。

与通用型“去 AI 味”工具不同，`academic-humanizer-zh` 明确服务于强约束文本场景。它强调学术保真，反对为追求“更像人写的”表象而擅自改动研究结论、补造数据来源、弱化专业术语，或将论文文本改写为口语化、营销化、评论化表达。

## Overview

This project is designed for high-constraint writing scenarios such as theses, dissertations, research reports, and MBA papers in Chinese. Unlike general-purpose text humanizers, it does not optimize for a more casual, expressive, or marketable style. Instead, it focuses on removing recognizable machine-writing patterns while keeping the text academically credible and structurally faithful to the source.

Typical goals include:

- reducing formulaic AI phrasing in Chinese academic writing
- preserving technical terminology and research conclusions
- rewriting with minimal necessary intervention
- avoiding fabricated evidence, citations, or stylistic overcorrection

## 项目定位

本 skill 主要解决以下问题：

- 中文论文文本中常见的 AI 套话、模板化表达与机械衔接过重
- 学术段落存在明显的空泛拔高、模糊归因、结论先行、句式过度整齐等机器特征
- 用户希望降低文本的 AI 痕迹，但同时要求保留原有术语、数据、论证逻辑与章节功能
- MBA 论文、研究报告等实践导向文本，需要在“去机器感”和“保持专业边界”之间取得平衡

因此，本项目并不追求“最大幅度重写”，而是强调“最小必要改写”原则：优先处理高识别度 AI 痕迹，尽量减少对正文内容本身的侵入式改动。

## 核心能力

`academic-humanizer-zh` 重点识别并处理以下类型的表达问题：

- 套话式背景句，如“随着……发展”“在……背景下”“众所周知”
- 空泛价值判断，如“具有重要意义”“发挥关键作用”“成为核心抓手”
- 模糊归因，如“研究表明”“专家认为”“相关数据显示”
- 机械结构，如“首先、其次、最后”“第一、第二、第三”密集堆叠
- 表面分析词汇，如“体现了”“彰显了”“凸显了”，但缺乏机制解释
- AI 高频词，如“赋能、抓手、闭环、赛道、生态、落地、协同”
- 过于平滑或过于对称的句式节奏
- 将论文写成“像论文的模板”，而不是“像作者的文字”

除去 AI 痕迹之外，本 skill 同时强调以下保真约束：

- 不擅自改动研究结论
- 不擅自改写专业术语
- 不擅自补造文献、数据、案例、访谈与出处
- 不弱化原有论证链条
- 不将学术文本降格为口语文案

## 适用场景

本项目适用于以下中文文本类型：

- 本科毕业论文
- 硕士论文
- MBA 论文
- 管理类案例分析
- 研究报告
- 学术摘要
- 文献综述
- 问题分析与对策建议章节
- 结论与研究局限部分

典型请求包括但不限于：

- “这段论文降一下 AI”
- “把这段摘要改得更像人写的，但不要改原意”
- “这个文献综述去一下 AI 味，保留术语和引用口径”
- “把这段 MBA 论文改自然一点，但别写得太像文案”

## 不适用场景

本 skill 不适合作为通用文本润色工具。对于以下内容，建议使用更通用的 humanizer 类 skill，而不是本项目：

- 公众号文章
- 广告文案
- 社交媒体帖子
- 评论、随笔、短文
- 口语化说明文

原因在于，这些文本更强调表达风格、情绪、传播感和语气变化，而不是学术文本所要求的术语稳定性、论证约束与引用边界。

## 方法原则

本项目遵循以下基本原则：

1. 保留原意  
   所有改写以不改变原文核心观点、研究对象和结论为前提。

2. 保留术语  
   专业概念、模型名称、变量表述、制度术语与学科表达默认不做口语化替换。

3. 最小必要改写  
   优先修改句式、衔接、套话和空泛判断，不轻易重写整段内容。

4. 反对虚构增强  
   不为了“更像真人写作”而补充原文没有的数据、案例、出处、细节或主观体验。

5. 学术风格优先  
   去除 AI 痕迹的同时，保留学术写作应有的克制性、清晰度与边界意识。

## 文件结构

```text
academic-humanizer-zh-skill/
├── README.md
├── SKILL.md
└── references/
    └── rewrite-checklist.md
```

各文件职责如下：

- `SKILL.md`
  项目的核心说明文件，定义触发条件、改写原则、工作方式、章节级建议与禁止事项。

- `references/rewrite-checklist.md`
  轻量检查清单，用于快速核对“哪些内容不能动”“哪些 AI 痕迹优先改”“如何判断论文是否被改歪”。

## 安装方式

将本项目目录放置到本地 Codex skills 目录下，例如：

```text
~/.codex/skills/academic-humanizer-zh/
```

安装完成后，当请求语义与学术文本“降 AI”高度相关时，Codex 即可按该 skill 的规则处理文本。

## 使用方式

安装后，可直接在对话中提出学术文本改写请求，无需手动执行额外命令。为了获得更稳定的结果，建议在请求中明确以下边界信息：

- 是否保留原意
- 是否保留术语
- 是否允许调整语气
- 文本所属类型（摘要、综述、结论、MBA 论文等）

示例：

```text
这段论文降一下 AI，保留原意和术语，不要写得太口语。
```

```text
把这段文献综述改得更像真实作者写的，去掉套话，但别动引用口径。
```

```text
这个 MBA 论文摘要有点像机器生成，帮我自然化一下，保持学术语气。
```

## 与通用 Humanizer 的区别

`academic-humanizer-zh` 与通用型 `Humanizer-zh` 的主要区别在于应用边界不同。

通用型 humanizer 更适合面向普通中文文本，通过增强语气变化、节奏变化和“人味”来降低机器感；而本项目更强调学术保真，通常不会主动引入强烈个性，也不会为了表达更生动而打破学术文本的稳定性。

简言之：

- 如果目标是“文章、文案、说明文去 AI 味”，优先使用通用 humanizer
- 如果目标是“论文、研究报告、摘要、综述降 AI”，优先使用本项目

## 当前版本特性

当前版本已经具备以下能力：

- 针对中文学术文本定义清晰的适用边界
- 对常见 AI 套话、宏大叙事、模糊归因与机械结构进行定向规避
- 对摘要、文献综述、问题分析、对策建议、结论等章节提供差异化处理思路
- 对 MBA 论文场景加入额外约束，但避免将所有文本强行模板化

## 已知边界

本项目并不提供以下能力：

- 自动核验参考文献真伪
- 自动补齐缺失数据来源
- 自动判定学校格式规范是否完全合规
- 自动检测全文重复率或 AI 检测率

换言之，本项目是“学术文本降 AI 改写”工具，而不是“全流程论文审查”工具。

## 开发说明

本仓库当前维护的是 skill 本体与最小参考文件，保持结构简洁，便于安装、复用与后续扩展。

后续若继续扩展，推荐优先沿以下方向演进：

- 摘要专用规则
- 文献综述专用规则
- MBA 论文专项规则
- 更细粒度的章节级参考文件
- 轻量检测脚本

## 许可证

This repository is released under the [MIT License](./LICENSE).

当前仓库使用 [MIT License](./LICENSE) 开源发布。
