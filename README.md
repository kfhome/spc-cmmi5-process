# spc-cmmi5-process

> AI 编程智能体（Agent）的全局工作方式技能 —— 一套对标 **CMMI v3.0 成熟度 5 级** 的软件过程体系，让 Agent 像一支纪律严明的工程团队一样干活。

An AI-agent skill that enforces a CMMI Level 5–style software process: planned work, tailoring, evidence-based delivery, quality gates, metrics, and continuous improvement — for any coding agent (Kimi Code, Claude Code, etc.).

## 这是什么

大多数 Agent 的默认行为是"接到任务就干"。本技能把它升级为一套**组织标准软件过程（SPC-00 ~ SPC-12）**：

- **计划先行**：非平凡任务先出方案，技术选型/架构改动先报方案获确认
- **裁剪机制**：微任务 / 标准任务 / 大型高风险任务三级裁剪，不一刀切
- **证据先于结论**：交付必须通过交付质量门 QGate-D（构建测试实测、端到端验证、文档联动）
- **危险动作红线**：不可逆操作、越目录、密钥、线上变更——不可裁剪的硬约束
- **度量留痕**：统一 YAML 记录工时/缺陷/返工，月度汇总驱动根因分析与持续优化
- **多智能体协同**：子代理派遣/复核/验收的作业标准（SPC-11）

适用于所有开发类任务：软件开发、脚本工具、部署运维、数据分析、课件工程等。

## 目录结构

```
spc-cmmi5-process/
├── SKILL.md                    # 技能入口（Agent 加载的纪律摘要与指针）
├── references/                 # 体系权威文件（细则冲突时以此为准）
│   ├── README.md               #   SPC-00 体系总纲与成熟度等级要求
│   ├── 01-组织过程定义与裁剪规程.md
│   ├── 02-需求开发与管理规程.md
│   ├── 03-项目策划与量化项目管理规程.md
│   ├── 04-设计开发与产品集成的过程.md
│   ├── 05-验证与确认规程.md
│   ├── 06-配置与变更管理规程.md
│   ├── 07-过程与产品质量保证规程.md
│   ├── 08-度量分析与组织过程性能规程.md
│   ├── 09-根因分析与持续优化规程.md
│   ├── 10-风险与决策管理规程.md
│   ├── 11-智能体协同作业规程.md      # Agent 作业标准、红线、QGate-D 全文
│   └── 12-模板与检查单集.md          # 交付自检清单 / 度量 YAML / 子代理简报模板
└── LICENSE
```

## 安装

把整个 `spc-cmmi5-process` 目录复制到对应 Agent 的用户技能目录：

| Agent | 目标路径 |
|---|---|
| Kimi Code | `~/.agents/skills/spc-cmmi5-process/` |
| Claude Code | `~/.claude/skills/spc-cmmi5-process/` |

Windows 示例（Git Bash）：

```bash
git clone <本仓库地址>.git
cp -r spc-cmmi5-process ~/.agents/skills/    # Kimi Code
cp -r spc-cmmi5-process ~/.claude/skills/    # Claude Code
```

安装后技能会在 Agent 接到开发类任务时自动触发（匹配关键词：CMMI、质量门、裁剪、度量留痕、交付自检等）。

## 核心纪律一览

**强制工作路径（接到任务按序执行）**

1. 定位需求：确认验收标准，歧义升级用户拍板，不猜
2. 查裁剪：按任务级别定最小执行集
3. 计划先行：非平凡任务先出方案
4. 照章执行：匹配既有代码风格、不假设依赖、大改动先备份
5. 验证交付：证据先于结论
6. 留痕度量：统一 YAML 记工时/缺陷/返工
7. 沉淀改进：踩坑回流知识库，同一坑不踩第二次

**交付质量门 QGate-D（逐项过才算完成）**：回读原指令全覆盖 / 构建测试实测通过 / 原始场景端到端验证 / 文档联动更新 / 度量留痕落盘 / 未触碰红线。

**度量目标**：一次通过率 ≥85%；返工率 ≤15%；证据合规率 100%；红线违例 0；沉淀率 ≥90%。

详见 `SKILL.md` 与 `references/`。

## 许可证

[MIT](LICENSE)
