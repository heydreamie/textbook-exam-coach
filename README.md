# 教材期末教练 · Textbook Exam Coach

一个面向大学课程期末复习的 Codex Skill。上传教材、课件或考试范围后，从考点梳理开始，逐题讲解、批改答案、整理错题，并按剩余时间安排复习。

## 能做什么

- 按实际读到的材料建立考点与来源定位，区分教师明确范围、试卷证据和复习建议。
- 用小测找出薄弱点，一题一题讲解与练习；默认先作答，再看答案。
- 按步骤给练习分，解释失分原因，提供变式题；区分独立答对、提示后答对和看过解答。
- 按课程保存进度、错题和待答题，支持后续继续复习。
- 生成模拟卷与分开的答案；需要时调用宿主已有的文档工具导出资料。

## 安装到 Codex

将本仓库文件放进 Codex 的个人 Skills 目录，文件结构应为：

```text
~/.codex/skills/textbook-exam-coach/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── coaching.md
    └── course-state.md
```

如果设置了 `CODEX_HOME`，使用该目录下的 `skills`。可以下载 GitHub ZIP，解压后将文件夹改名为 `textbook-exam-coach` 再复制；已存在同名 Skill 时先保留原版本，不直接覆盖。

也可以使用 Git 安装。

macOS / Linux：

```sh
git clone https://github.com/heydreamie/textbook-exam-coach.git "$HOME/.codex/skills/textbook-exam-coach"
```

Windows PowerShell：

```powershell
git clone https://github.com/heydreamie/textbook-exam-coach.git "$env:USERPROFILE\.codex\skills\textbook-exam-coach"
```

安装后在下一轮对话中使用 `$textbook-exam-coach`；如果当前客户端尚未刷新 Skills 列表，再新开一个对话。

## 开始复习

在支持附件的 Codex 聊天中添加教材，或提供可访问的本地文件路径，然后发送：

> 用 $textbook-exam-coach 帮我准备高数期末。我上传了教材和老师题纲，还有 10 天，每天 1 小时，目标 80 分。先梳理考试范围，再一题一题教我。

只有教材也能开始。课件、老师划定的范围和历年卷可以帮助安排优先级；缺少这些资料时，不会把推测包装成“必考题”。

继续学习可以说：

> 继续上次的复习，先练错题，再学下一节。

## 文件和环境

这是一套 Skill 指令与参考规则，不是独立网站或题库服务。基础辅导使用当前 Codex 对话模型，不要求另配模型 API Key。PDF、扫描件、Word 和幻灯片的读取依赖宿主现有工具；无法识别的内容应标明并补充清晰材料。使用宿主模型服务不等于离线处理。

课程记录保存在用户指定目录，或工作区中的 `exam-prep/课程简称/`，不应保存到本 Skill 仓库。仓库不包含教材、学生答案或个人学习记录。

## 验证与边界

已进行 Skill 结构校验和样例教学验证，包括缺少考纲、只提交最终答案、扫描材料不可读、考试日期未知的场景。尚未针对所有教材格式或课程开展实测；不保证押题、考试分数或扫描识别成功率。

本仓库的指令为原创编写，未引入第三方项目代码或复制其 Skill 文本。调研参考包括 [exam-review-helper](https://github.com/daxueren666/exam-review-helper)、[ProjectSchola](https://github.com/OJ102/ProjectSchola) 和 [DeepTutor](https://github.com/HKUDS/DeepTutor)。它们不是本 Skill 的必需依赖。
