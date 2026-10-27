# 用思维模型拆问题

开源的 [Cursor / Grok Bot](https://cursor.com) **Skill** 配方：描述工作或业务问题后，固定选出 **3 个**思维模型，并**严格按每个模型细文里的步骤**逐步分析，用表格等结构化版式摊开结果。

细文（机制、步骤、例子、踩坑）托管在公开站 [51as.com/toolbox](https://51as.com/toolbox)，本仓库只放可复用的配方与轻量索引。

## 仓库里有什么

| 文件 | 作用 |
| --- | --- |
| `SKILL.md` | Skill 正文（YAML frontmatter + 步骤） |
| `models-index.yaml` | 156 条模型轻量索引（id / slug / 中英文名 / 分类 / 一句定义） |
| `scene-lookup.yaml` | 61 个工作场景 → 主模型 + 辅助模型 |
| `LICENSE` | MIT |

## 怎么用

### Cursor / Grok Bot

1. 新建一个 user skill 目录（或导入到助手的 skills 里）。
2. 把本仓库的 `SKILL.md`、`models-index.yaml`、`scene-lookup.yaml` 放进**同一目录**。
3. 在对话里用 `/用思维模型拆问题`（或描述问题时让助手自动匹配 description）触发。
4. 分析时需要读细文步骤：打开 `https://51as.com/toolbox/<slug>`（slug 见索引）。

本 Skill **不是** npm 包；`npm install` 不会把它装进助手的 skill 列表。

### 其它助手

只要能加载「目录内 Markdown 配方 + 旁路 yaml」，把上述三个文件放在一起即可；细文仍按链接读站上页。

## 硬规矩（摘要）

1. 选出模型只是半截；交付主体是「用该模型的 steps 拆用户问题」。
2. 恰好 3 个模型；禁止库外模型名。
3. 矩阵 / 对照 / 漏斗等结果用表格（或列表 / mermaid）摊开，扫表能下结论。

## 许可

- 本仓库配方与索引：**MIT**（见 `LICENSE`）
- 站上细文页面：[51as.com/toolbox](https://51as.com/toolbox) 的页面版权以站点标注为准；本仓库不二次分发全文

## 相关

- 工具箱站点：https://51as.com/toolbox
