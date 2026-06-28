# 计划：xia_11–xia_20（含 xia_19x）备注规范化与 proof 归档终验

## 1. 任务摘要

对 `logs/contents/02_xia/` 下的 11 个故事文件（xia_11 至 xia_20，含 xia_19x）进行终验：

1. 确认每篇「备注」区已按 writing.md 要求使用四大顶层前缀：`### 史源：索引`、`### 考古：相关发现`、`### 推断：...`、`### 评论：延伸思考`。
2. 确认 `xia_12`（少康中兴）的「考古：相关发现」已明确标注二里头文化第二期及以后（Phase 2+）的考古迹象。
3. 确认正文中的局外视角/评价性语句已移入「评论：延伸思考」。
4. 确认/生成 `temp/02_xia/<id>.proof.md` 四阶段校对文件，且结果只能是 ✅ 或 ➖。
5. 使用 Grep 对 11 个故事文件的四大前缀进行批量校验。
6. 返回执行摘要。

---

## 2. 当前状态分析

### 2.1 故事文件

目标文件路径：

```
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_11.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_12.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_13.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_14.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_15.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_16.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_17.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_18.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_19.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_19x.md
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\logs\contents\02_xia\xia_20.md
```

已用 Grep 预审：每篇均包含 4 个目标前缀（共 44 次匹配），说明标题框架已就位。但仍需逐篇目视检查：

- 前缀是否恰好是要求的四个顶层标题，无旧标题残留（如「史源索引」「推断说明」「学术争议」等）。
- `xia_12.md` 考古段落是否含「二里头文化第二期」「二期以降」等 Phase 2+ 表述。
- 正文是否还有未移出的评论/比较/评价句。

### 2.2 Proof 文件

对应 proof 路径：

```
d:\yun\baidu\BaiduSyncdisk\gpt\agents\historical-stories\historical-stories\temp\02_xia\xia_11.proof.md
...（xia_12–xia_20、xia_19x）
```

抽样检查显示：11 个 proof 文件均已存在，结构包含「阶段 1–4」，结果符号均为 ✅ 或 ➖，无 ❌。但执行时仍需逐项确认：

- 是否包含 writing.md §8.3 的四个阶段标题。
- 是否仅有 ✅ / ➖ 两种结果符号。
- 对 xia_12、xia_13、xia_14 等之前缺失 proof 的文件，若现有文件不符合规范则覆盖重写。

---

## 3. 拟执行步骤

### 步骤 1：逐篇目视复核故事文件（11 篇）

对每篇执行：

1. `Read` 全文或「备注」区域。
2. 检查旧标题残留：搜索「史源索引」「推断说明」「学术争议」等非当前标准标题，如有则替换为 `### 史源：索引`、`### 推断：...`、`### 评论：延伸思考`。
3. 检查 `### 考古：相关发现`：
   - 所有正史线夏代故事必须存在该小节。
   - 内容须说明「直接考古证据尚不存在」，并给出二里头文化/周边文化的宏观背景。
   - **xia_12.md** 须特别指出「二里头文化第二期（约前1900—前1750年）」及以后迹象（宫城扩大、铸铜作坊成熟、礼器增多等）。
4. 检查正文是否有评论体/局外判断句（如「难能可贵」「是成功的」「对后世产生深远影响」等），如有则改写为中性叙事或移入「评论：延伸思考」。
5. 用 `Edit` 进行必要修正。

### 步骤 2：生成/覆盖 proof 文件（11 个）

对每篇执行：

1. 若 proof 文件已存在且符合四阶段结构、仅含 ✅/➖，则保留。
2. 若 proof 文件缺失、结构不全、含 ❌ 或描述不符合当前版本，则使用 `Write` 覆盖生成新版 proof。
3. proof 文件模板：
   - 标题：`# 校对记录：<id>`
   - 阶段 1：红线审查（5 项，正史线文学线项用 ➖）
   - 阶段 2：内容核心审查（7 项）
   - 阶段 3：叙事与形式规范审查（含叙事质量 6 项 + 形式规范 4 项）
   - 阶段 4：元数据与篇幅审查（3 项）
   - 独立验证记录（关键史料/考古来源核对）
   - 通读记录（阅读体验问题与处理）
   - 修订摘要
4. 所有审查结果只能是 ✅ 或 ➖，并附简短说明。

### 步骤 3：Grep 批量校验四大前缀

运行 Grep：

```
^### (史源：索引|考古：相关发现|推断：|评论：延伸思考)
```

路径：`logs/contents/02_xia`
文件模式：`xia_{11,12,13,14,15,16,17,18,19,19x,20}.md`

期望结果：11 个文件各出现 4 次匹配，共 44 次。

### 步骤 4：汇总并返回摘要

整理：

- 哪些文件被修改及修改要点。
- 哪些 proof 文件被新建/覆盖。
- Grep 校验结果。
- 是否存在未解决的阻塞项。

---

## 4. 关键依赖与假设

- 以 `.agents/writing.md` §4.1 / §4.2 / §4.4 / §8 为校对标准。
- 二里头文化分期采用项目内部约定：第二期约前1900—前1750年，第三期约前1750—前1600年，第四期约前1600—前1500年。
- 若发现故事文件与 proof 文件均已完成且合规，则本计划以「校验通过」为主，不做重复改写。

---

## 5. 验证标准

- [ ] 11 个故事文件均包含 `### 史源：索引`、`### 考古：相关发现`、`### 推断：`、`### 评论：延伸思考` 四个顶层标题。
- [ ] `xia_12.md` 考古小节出现「二里头文化第二期」或「二期以降」等 Phase 2+ 表述。
- [ ] 11 个 proof 文件均存在，且仅使用 ✅ / ➖ 两种结果符号。
- [ ] Grep 校验报告 11 文件 × 4 前缀 = 44 次匹配。
- [ ] 返回的最终摘要列出修改/生成文件清单与关键发现。
