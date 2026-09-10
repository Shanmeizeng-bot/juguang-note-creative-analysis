# 聚光笔记创意分析 Skill

将投放原始数据整理为按笔记 ID 和创意 ID 归因的分析工作簿，包含视频拆解、漏斗诊断、ROI 标色与具体投放动作。

本仓库不包含任何客户数据、品牌名称、供应商名称、账号、链接 token、模板或已生成工作簿。上传前请保持 `.gitignore` 生效。

## 安装

下载或克隆仓库后，将本目录放进 Codex 的 skills 目录：

```bash
git clone https://github.com/<Shanmeizeng-bot>/juguang-note-creative-analysis.git
mkdir -p ~/.codex/skills
cp -R juguang-note-creative-analysis ~/.codex/skills/
```

重新打开 Codex 后，可在对话中使用：

```text
使用 $juguang-note-creative-analysis，根据我提供的投放原始数据生成笔记与创意分析工作簿。
```

首次使用时，Skill 会先检查原始文件；只有在指标口径、转化目标或视频/截图关联不明确时，才生成需要转发给供应商的问题清单。
