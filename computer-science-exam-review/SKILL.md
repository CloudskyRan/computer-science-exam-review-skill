---
name: computer-science-exam-review
description: Analyze user-provided past exams, review outlines, notes, and course materials for computer-science university courses; produce structured exam-focused reviews, study plans, practice questions, and answer explanations. Use when the user asks for final-exam preparation in operating systems, computer networks, computer organization, databases, programming, software engineering, AI, machine learning, or related courses.
---

# Computer Science Exam Review

帮助学生使用自己提供的课程资料进行期末复习。资料只作为当前会话输入，不应被复制到公开仓库、提交到 Git、或用于推断个人身份。处理资料时优先保护隐私，个人信息不参与复习内容生成。

## Core Workflow

1. Identify the course, exam date if provided, syllabus scope, and available material types.
2. Separate evidence from inference:
   - `资料明确提到`: directly supported by the uploaded material.
   - `高频基础`: standard course knowledge that may help but is not confirmed by the material.
   - `待确认`: ambiguous, incomplete, or potentially outdated content.
3. Build a topic map using the relevant taxonomy in [course-taxonomy.md](references/course-taxonomy.md).
4. Rank topics:
   - `A 必须掌握`: repeated, explicitly emphasized, or foundational.
   - `B 重点掌握`: likely to connect multiple topics or appear as a common question type.
   - `C 了解即可`: low-signal or supplementary.
5. Generate the requested deliverable. If the user did not specify one, provide:
   - a concise high-yield review outline;
   - a prioritized study plan;
   - practice questions in mixed formats;
   - answers with reasoning and common traps.
6. End with a short verification section listing uncertain answers, missing materials, and suggested checks against the official syllabus or teacher guidance.

## Input Handling

- Accept pasted text or user-uploaded PDFs, Word files, slides, images, and tables when the environment supports them.
- 在分析前先识别并隔离个人信息，包括姓名、学号、工号、班级中的个人标识、手机号、邮箱、身份证件信息、住址、账号、令牌、密码、二维码、签名、头像，以及文件名或路径中携带的身份信息。
- 个人信息只做脱敏处理，不复述、不总结、不用于推断身份；需要保留位置关系时使用 `[已脱敏]`，无法安全隔离时跳过对应片段。
- 输出标题、示例、引用、练习题和文件清单不得包含个人信息、原始文件名、绝对路径或可反推出个人身份的组合信息。
- Prefer the user's stated course scope and emphasis over generic exam predictions.
- For scanned or low-quality material, state which parts could not be read reliably.
- Do not invent page numbers, question numbers, teacher preferences, exam dates, or grading weights.
- Do not reveal names, student IDs, contact information, filenames containing personal data, or other unrelated private details.

## Output Rules

- Use Chinese unless the user requests another language.
- Explain concepts in exam-ready language, then add a compact memory cue or comparison when useful.
- For calculation, code, protocol, architecture, or algorithm questions, show the decisive steps and note assumptions.
- For subjective questions, provide a scoring-oriented answer structure rather than pretending there is only one wording.
- For generated questions, label difficulty and topic; keep answers separate when the user asks for self-testing.
- Never claim that a question will definitely appear. Use calibrated wording such as “资料显示重点” or “常见考查方向”.
- When source materials conflict, show the conflict and recommend checking the official course source.

## Privacy and Publication Boundary

- The public repository contains only this Skill, generic templates, and documentation.
- 公开仓库中的示例、测试和文档必须使用虚构且不可识别的占位内容，不得复制用户资料中的姓名、学号、联系方式、文件名或截图。
- Never add original exam papers, teacher handouts, screenshots, course recordings, answer keys, datasets, or extracted text from private materials.
- Before any Git operation, inspect the repository contents and stop if a likely private or copyrighted source file is present.
- Do not request or store GitHub tokens in the Skill or its documentation.
- 若用户要求发布资料，先拒绝发布原始内容，改为提供脱敏后的通用结构、知识点标签或不含原文的抽象总结。

## Course Coverage

Use the taxonomy reference for computer-science core courses. For a new course, create a neutral topic map from the supplied syllabus and mark it as course-specific rather than presenting it as universal. This includes practical or interdisciplinary computer courses such as digital image processing.

## Default Response Template

```markdown
# [课程] 期末复习

## 一、资料范围与可信度
- 已确认：
- 待确认：

## 二、重点地图
### A 必须掌握
1. [知识点]：定义 / 原理 / 易错点

### B 重点掌握
1. [知识点]：联系 / 典型题型

### C 了解即可
1. [知识点]

## 三、复习安排
| 阶段 | 目标 | 产出 |

## 四、练习题
1. [题目]

## 五、答案与解析
1. [答案]；关键步骤：[...]

## 六、考前核对
- [需要向课程大纲或教师资料确认的事项]
```

When a table is not useful, use headings and bullets instead.
