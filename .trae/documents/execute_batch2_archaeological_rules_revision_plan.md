# 执行计划：Batch 2 三皇五帝考古规则修订

## 1. 任务摘要

按 `.trae/documents/archaeological_rules_revision_sanhuangwudi_xia.md` 批次安排，处理三皇五帝时代第 2 批共 10 篇故事：

```
logs/contents/01_sanhuangwudi/sanhuangwudi_11.md  …  sanhuangwudi_20.md
```

对每篇完成：备注四前缀规范化、考古发现专项补全/重构、正文局外视角清理、proof 校对文档创建/覆盖、批次终检。

---

## 2. 当前状态分析

### 2.1 已探索文件

- `.agents/writing.md`：已读取 §4（备注）、§8（校对）等关键条款。
  - §4.1 强制备注前缀：`史源：`、`考古：`、`推断：`、`评论：`。
  - §4.4 考古发现不得默认省略；传说时代须写明无直接证据并给出宏观背景。
  - §8 校对须生成 `temp/<era_dir>/<id>.proof.md`，逐项标记 ✅ / ❌ / ➖。
- `.trae/documents/archaeological_rules_revision_sanhuangwudi_xia.md`：已读取完整计划，明确 Batch 2 范围与 proof 模板。
- `logs/contents/01_sanhuangwudi/sanhuangwudi_16.md`：磁盘文件已具备四前缀，考古专项完整。
- `logs/contents/01_sanhuangwudi/sanhuangwudi_17.md`、`sanhuangwudi_19.md`、`sanhuangwudi_20.md`：磁盘文件已具备四前缀，考古专项完整。
- `logs/contents/01_sanhuangwudi/sanhuangwudi_18.md`：**磁盘文件缺失 `### 考古：相关发现`**，且备注首标题为 `### 史源：索引与原文`，不符合四前缀硬约束。
- `temp/01_sanhuangwudi/sanhuangwudi_16.proof.md` 至 `sanhuangwudi_20.proof.md`：proof 文件均存在，但 `_16`、`_17`、`_18` 采用较早模板，缺少 `> 本次校对依据 writing.md 最新版本...` 导引及明确的 `正史线：备注已按 §4.4 规范处理考古发现` 检查项；`_19`、`_20` 已使用新模板。

### 2.2 关键问题

| 问题 | 涉及文件 | 影响 |
|---|---|---|
| 备注缺少 `### 考古：相关发现` | `sanhuangwudi_18.md` | 违反 writing.md §4.4「不得默认省略」 |
| 备注首标题为 `### 史源：索引与原文` 而非 `### 史源：索引` | `sanhuangwudi_18.md` | 与四前缀硬约束不一致 |
| proof 文件模板不统一 | `sanhuangwudi_16.proof.md`、`_17.proof.md`、`_18.proof.md` | 与考古规则修订计划给定模板不一致，缺少 §4.4 考古专项检查项 |

其余 7 篇故事文件与 proof 文件基本符合要求，但仍须逐篇校验确认。

---

## 3. 拟议变更

### 3.1 故事文件处理（10 篇）

对 `sanhuangwudi_11.md` 至 `sanhuangwudi_20.md` 逐篇执行：

1. **读取完整文件**，确认 YAML 元数据完整。
2. **备注结构重塑**：
   - 一级标题必须为 `### 史源：索引`、`### 考古：相关发现`、`### 推断：……`、`### 评论：……`。
   - 对 `sanhuangwudi_18.md`：
     - 将 `### 史源：索引与原文` 改为 `### 史源：索引`。
     - 将原有长篇古文引文移入 `### 史源：索引` 下的 `#### 史源原文` 子节（或直接保留在 `### 史源：索引` 表格之后）。
     - **新增 `### 考古：相关发现`**，按传说时代规则撰写：首句声明鲧禹治水/尧时洪水暂无直接考古证据，不可将传说人物与遗址等同；随后列出陶寺、二里头早期水利、喇家遗址、龙山—二里头过渡期环境考古等宏观背景。
   - 对其余 9 篇：若四前缀已存在且标题正确，仅做一致性微调；若发现旧标题或未前缀段落，按规范修正。
3. **考古：相关发现 内容规则**：
   - 三皇五帝属传说时代，任何具体人物/事件均不得与考古遗址直接等同。
   - 必须给出宏观考古学文化背景（贾湖、裴李岗、磁山、仰韶、龙山、大汶口、红山、良渚、陶寺、石峁等），按主题相关性筛选。
4. **正文局外视角清理**：
   - 将「影响深远」「奠定了……基础」「我们可以看到」等评论句移入 `### 评论：延伸思考`。
   - 删除正文末尾的总结性评论段落。
5. **写回文件**（覆盖原文件）。

### 3.2 Proof 文件处理（10 篇）

对 `temp/01_sanhuangwudi/sanhuangwudi_11.proof.md` 至 `sanhuangwudi_20.proof.md` 逐篇执行：

1. 统一使用考古规则修订计划给定模板：
   - 开头加入 `> 本次校对依据 writing.md 最新版本（含 2026-06-27 修订的「考古：」备注前缀与考古发现规范）执行。`
   - 四阶段表格：阶段 1 红线审查、阶段 2 内容核心审查、阶段 3 叙事与形式规范审查、阶段 4 元数据与篇幅审查。
   - 阶段 2 必须包含 `正史线：备注已按 §4.4 规范处理考古发现（有则标注，无则说明阙如）` 检查项。
   - 阶段末尾附：独立验证记录、通读记录、修订摘要。
2. 所有检查结果仅允许 `✅` 或 `➖`（正史线文学项），不得遗留 `❌`。
3. 对 `sanhuangwudi_18.proof.md` 额外记录：新增考古专项、修正史源标题等主要修订点。

### 3.3 终盘校验

1. 用 Grep 确认 `logs/contents/01_sanhuangwudi/sanhuangwudi_11.md` 至 `sanhuangwudi_20.md` 每篇均包含：
   - `### 史源：`
   - `### 考古：`
   - `### 推断：`
   - `### 评论：`
2. 用 Grep 确认 `temp/01_sanhuangwudi/sanhuangwudi_11.proof.md` 至 `sanhuangwudi_20.proof.md` 每篇均包含四阶段标题且无 `❌` 标记。
3. 记录校验结果到最终汇报。

---

## 4. 假设与决策

| 决策点 | 选择 | 理由 |
|---|---|---|
| 是否重新处理已看似完成的篇目 | 逐篇读取校验，仅对不符合处打补丁 | 避免重复劳动，同时保证规范一致 |
| `sanhuangwudi_18.md` 是否重写备注 | 是 | 磁盘文件确实缺少考古专项且史源标题错误 |
| 旧模板 proof 是否覆盖 | 是 | 统一为考古规则修订计划最新模板，确保阶段 2 含 §4.4 考古检查项 |
| 考古专项是否直接等同传说与遗址 | 否 | 三皇五帝为传说时代，必须保留证据边界 |
| 是否修改 `logs/eras/` 或 `logs/progress.md` | 否 | 本次为质量回查修正，不改变原完成状态 |

---

## 5. 验证步骤

1. 逐篇读取 10 个故事文件与 10 个 proof 文件。
2. 按 3.1 与 3.2 执行修订与 proof 覆盖。
3. Grep 校验故事文件四前缀覆盖：
   ```powershell
   foreach ($n in 11..20) { $f = "logs/contents/01_sanhuangwudi/sanhuangwudi_$n.md"; foreach ($p in '### 史源：','### 考古：','### 推断：','### 评论：') { if (-not (Select-String -Path $f -Pattern $p)) { Write-Host "MISSING $p in $f" } } }
   ```
4. Grep 校验 proof 文件无 ❌：
   ```powershell
   foreach ($n in 11..20) { $f = "temp/01_sanhuangwudi/sanhuangwudi_$n.proof.md"; if (Select-String -Path $f -Pattern '\| ❌ \|') { Write-Host "UNCLEARED ❌ in $f" } }
   ```
5. 生成修订摘要：列明修改文件、主要改动、校验结果。

---

## 6. 风险控制

- 任一文件读取/写入失败立即暂停并报告，不跳过。
- 不修改计划范围之外的文件。
- 不主动创建 README 等文档文件。
