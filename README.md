# index-docs

`index-docs` 是一个 Codex Skill，用于为项目初始化或维护以根目录 `AGENTS.md` 为入口的本地协作文档索引。它覆盖 Agent 设计规格、可恢复的任务记录与 handoff、规则索引和人工待办管理。

## GitHub 导入

本仓库根目录就是 Skill 根目录，包含必需的 `SKILL.md` 和推荐的 `agents/openai.yaml`。在 Codex 的 Skill 导入入口中使用仓库地址即可：

<https://github.com/HoraceGriffin/Init-Docs-Skill>

导入时选择仓库根目录，不要只选择 `references/rules/` 子目录。导入后可用 `$index-docs` 显式调用，或直接提出初始化、整理项目协作文档的任务。

## 目录结构

```text
SKILL.md                 # Skill 元数据和执行流程
agents/openai.yaml       # Codex UI 元数据
references/rules/        # 按需复制到目标项目的通用规则
README.md                # GitHub 导入说明
```

`references/rules/` 中的文件只在目标项目确实需要时读取和复制，不会自动加载全部规则。

## 本地校验

在包含 PyYAML 的 Python 环境中运行 Skill Creator 的基础校验：

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py .
```
