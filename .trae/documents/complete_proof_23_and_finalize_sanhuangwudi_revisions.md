# 计划：完成 sanhuangwudi_23 校对记录并汇总三皇五帝故事修订结果

## 1. 摘要

继续完成指定 7 篇三皇五帝故事（sanhuangwudi_19 至 sanhuangwudi_25）的校对与修订收尾工作。当前 6 篇故事的修改与 proof 文件已完整，仅 `sanhuangwudi_23.proof.md` 因之前的文件锁定错误而内容截断，需要补全。完成后将按用户要求返回处理摘要。

## 2. 当前状态分析

- 已修改的故事文件（7 篇）均位于 `logs/contents/01_sanhuangwudi/`，且已按最新规范完成：
  - 新增/重构「考古：相关发现」专项；
  - 备注前缀统一为 `史源：`、`考古：`、`推断：`、`评论：`；
  - 正文局外视角语句已移入备注；
  - 史源索引中无考古发现条目需调整等级的问题。
- 已存在的 proof 文件（6 篇）内容完整，格式符合 `writing.md §8` 与 `file-spec.md §7`。
- `temp/01_sanhuangwudi/sanhuangwudi_23.proof.md` 已存在，但内容在「独立验证记录」表头处截断，缺少：
  - 表头分隔线 `|---|---|---|`；
  - 独立验证具体条目；
  - 「通读记录」；
  - 「修订摘要」。

## 3. 拟议变更

### 3.1 补全 `sanhuangwudi_23.proof.md`

- **文件路径**：`d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\temp\01_sanhuangwudi\sanhuangwudi_23.proof.md`
- **操作**：使用 `Write` 覆盖写入完整内容，保留已有的阶段 1–4 审查结果，补齐以下部分：
  - `## 独立验证记录` 下的完整表格（至少 3 项，对应本次修订关键点）；
  - `## 通读记录`（正文与备注的阅读体验结论）；
  - `## 修订摘要`（逐条列出对 sanhuangwudi_23.md 的具体修改）。
- **依据**：`writing.md §8.3` 的 4 阶段校对项目、`file-spec.md §7.2` 的 proof 文件结构与符号约定。

### 3.2 快速复核其余 6 篇 proof 文件

- **文件列表**：
  - `temp/01_sanhuangwudi/sanhuangwudi_19.proof.md`
  - `temp/01_sanhuangwudi/sanhuangwudi_20.proof.md`
  - `temp/01_sanhuangwudi/sanhuangwudi_21.proof.md`
  - `temp/01_sanhuangwudi/sanhuangwudi_22.proof.md`
  - `temp/01_sanhuangwudi/sanhuangwudi_24.proof.md`
  - `temp/01_sanhuangwudi/sanhuangwudi_25.proof.md`
- **操作**：通读确认每篇均包含阶段 1–4、独立验证、通读记录、修订摘要，且所有结果符号为 ✅/➖（无 ❌）。若发现格式瑕疵，仅做最小修正。

### 3.3 返回最终摘要

- 汇总 7 篇文件的处理结果；
- 列出每篇主要修改类型；
- 说明遇到的问题（前期文件锁定已自行恢复）及处理结果；
- 确认全部 proof 文件已成功落盘。

## 4. 假设与决策

- 假设 7 篇故事文件的修改内容已符合用户规范，本次不再大规模重写正文；仅在校对记录中反映已有修改。
- 假设 `sanhuangwudi_23.proof.md` 的截断是之前的写入异常导致，采用完整覆盖写入而非增量修补，以避免表格格式残留问题。
- 不修改