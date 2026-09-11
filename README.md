# 聚光笔记创意分析 Skill / Juguang Note & Creative Analysis Skill

将聚光投放原始数据整理为按笔记 ID 和创意 ID 归因的分析工作簿，包含笔记内容拆解、漏斗诊断、ROI 标色与具体投放动作。

Transforms Juguang advertising exports into an analysis workbook attributed by note ID and creative ID, including note-content breakdowns, funnel diagnostics, ROI colour coding, and specific media actions.

本仓库不包含任何客户数据、品牌名称、供应商名称、账号、链接 token、模板或已生成工作簿。上传前请保持 `.gitignore` 生效。

This repository contains no client data, brand or supplier names, accounts, link tokens, templates, or generated workbooks. Keep `.gitignore` enabled before publishing.

## 工作方式 / How it works

Skill 在读取数据或生成工作簿前，先确认两项：供应商名称，以及本次需要分析的日期范围（`MMDD-MMDD`）。它会按该范围含首尾日期过滤全部记录；文件名格式固定为 `【供应商】-笔记&创意-数据MMDD-MMDD.xlsx`。

Before reading the data or building a workbook, the skill confirms two items: the supplier name and the requested analysis range (`MMDD-MMDD`). It filters every record inclusively to that range; the output is named `【Supplier】-笔记&创意-数据MMDD-MMDD.xlsx`.

对于可访问的笔记链接，Skill 会先打开页面，依据可见标题、封面和内容/视频信息完成拆解；只有链接无法访问或页面无法加载时，才会标明具体的核对限制。工作簿会开启网格线，并为所有已用表格区域提供完整细边框。

For every accessible note link, the skill first opens the page and uses its visible title, cover, and content/video details for the breakdown. It records a specific limitation only when the link or page cannot be accessed. Workbooks keep worksheet gridlines on and apply complete thin borders across every used table range.

## 安装 / Install

下载或克隆仓库后，将本目录放进 Codex 的 skills 目录：

After downloading or cloning the repository, place this folder in Codex’s skills directory:

```bash
git clone https://github.com/<shanmeizeng-bot>/juguang-note-creative-analysis.git
mkdir -p ~/.codex/skills
cp -R juguang-note-creative-analysis ~/.codex/skills/
```

重新打开 Codex 后，可在对话中使用：

Restart Codex, then use it in a conversation:

```text
使用 $juguang-note-creative-analysis，根据我提供的投放原始数据生成笔记与创意分析工作簿。
```

首次执行时，如果当前对话还没有给出供应商和日期范围，Skill 会先询问这两项，再开始处理。

On first use, if the supplier and date range have not already been stated in the conversation, the skill asks for them before processing begins.
