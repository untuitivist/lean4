

## 1. 重新打开安装指南
这个指南总是可以通过打开一个空的文件重新打开。单击右上角的$\forall$符号并选择"Documentation...">'Setup: Show Setup Guide'
![[images/Pasted image 20240602141959.png]]

## 2. 书籍和文档

使用右侧的资源学习lean4
[[lean4入门资料]]

## 3. 安装所需的依赖项

安装 Git. 

### 安装所需的依赖项
[Git](https://git-scm.com/ "https://git-scm.com/") 是一种常用的[版本控制系统](https://en.wikipedia.org/wiki/Version_control "https://en.wikipedia.org/wiki/Version_control")，lean使用它来帮助管理不同版本的lean形式化包和软件包。

1. 安装[Git](https://git-scm.com/download/win "https://git-scm.com/download/win")。您可以将安装程序中的所有设置保留为默认值。
2. 等到安装完成。
3. 重新启动 VS Code 并重新打开本指南。

 ### 受限环境
 
如果您所处的环境无法安装 Git 并且尚未安装，例如在受限的大学计算机上，则目前没有使用本地安装来尝试 Lean 4 的选项。无论如何，如果你想尝试lean4，你可以阅读lean数学([Mathematics in Lean](https://leanprover-community.github.io/mathematics_in_lean/ "https://leanprover-community.github.io/mathematics_in_lean/"))，并使用[Gitpod托管的lean4在线实例](https://gitpod.io/#/https://github.com/leanprover-community/mathematics_in_lean "https://gitpod.io/#/https://github.com/leanprover-community/mathematics_in_lean")进行练习。这样做需要创建一个 GitHub 帐户。或者，您也可以[玩自然数游戏](https://adam.math.hhu.de/#/g/hhu-adam/NNG4 "https://adam.math.hhu.de/#/g/hhu-adam/NNG4")或[在网络浏览器中尝试单文件版本的lean](https://live.lean-lang.org/ "https://live.lean-lang.org/")4。

## 4. 安装lean版本管理器

安装lean版本管理器Elan![[images/Pasted image 20240602143800.png]]

### Elan

[Elan](https://github.com/leanprover/elan "https://github.com/leanprover/elan") 自动管理 Lean 的所有不同版本，并确保在打开项目时使用正确的版本。

点击[此链接](command:lean4.setup.installElan "command:lean4.setup.installElan") 将下载 [Elan 设置脚本](https://github.com/leanprover/elan/blob/master/elan-init.ps1 "https://github.com/leanprover/elan/blob/master/elan-init.ps1") 并执行它。

如果脚本执行时没有显示错误，则 Elan 和当前稳定版本的 Lean 4 都已安装。如果显示了你不理解的错误，请点击左侧的“问题与故障排除”步骤。

## 5. 设置lean 4 项目

通过单击右侧的选项之一来设置lean 4 项目。

### 创建项目

下面，你会找到一些链接，这些链接可以为你创建新的项目或下载现有项目。创建或下载项目后，你可以通过点击右上角的 ∀-符号，选择“Open Project…” “Open Local Project…”并选择你创建的项目来重新打开该项目。
完成项目创建过程并选择打开新项目将关闭本指南。你可以稍后点击右上角的$\forall$符号并选择“Documentation…” “Setup: Show Setup Guide”重新打开本指南。
![[images/Pasted image 20240602144616.png]]
如果你想创建一个新项目，请点击以下链接之一：

- 创建一个新的独立项目
    独立项目不依赖于任何其他 Lean 4 项目。如果你想将 Lean 4 用作通用编程语言或程序验证，此选项适合你。  
    可以通过修改新项目中的“lakefile.lean”文件来添加依赖项，如[此处](https://github.com/leanprover/lean4/blob/master/src/lake/README.md#adding-dependencies "https://github.com/leanprover/lean4/blob/master/src/lake/README.md#adding-dependencies")所述。你可能需要将[Lean 的标准库](https://github.com/leanprover/std4 "https://github.com/leanprover/std4")添加到依赖列表中。
- 使用 Mathlib 创建一个新项目
    创建的项目将依赖于 [Mathlib](https://github.com/leanprover-community/mathlib4 "https://github.com/leanprover-community/mathlib4")，即 Lean 4 的数学库。如果你想将 Lean 4 用于数学形式化项目，此选项适合你。  
    创建项目后，要更新 Mathlib，你可以点击右上角的 ∀-符号并选择“Project Actions…” “Project: Update Dependency…”。

如果你想打开一个现有项目，请点击以下链接之一：

- [下载一个现有项目](command:lean4.project.clone "command:lean4.project.clone")  
    如果你想为另一个 Lean 4 项目（如 [Mathlib](https://github.com/leanprover-community/mathlib4 "https://github.com/leanprover-community/mathlib4")）做贡献，此选项适合你。
- [打开一个现有的本地项目](command:lean4.project.open "command:lean4.project.open")  
    如果你从其他人（如导师）那里获得了一个本地 Lean 4 项目，此选项适合你。

### 复杂项目设置

使用其构建系统和包管理器 Lake，Lean 4 支持比上述描述的更复杂的项目设置。你可以在 [Lean 4 GitHub 仓库](https://github.com/leanprover/lean4/blob/master/src/lake/README.md "https://github.com/leanprover/lean4/blob/master/src/lake/README.md")中了解更多关于 Lake 的信息。


## 6. 在 VS Code 中使用 Lean 4 

学习如何与 VS Code 扩展一起使用 Lean 

### 在 VS Code 中使用 Lean 4

[[lean4inVSCode_manual_zh|Lean 4 VS Code 扩展手册]]涵盖了在 VS Code 中使用 Lean 4 时的各种重要工具。即使您已经熟悉其他编程语言和 VS Code，您可能会发现手册中“与 Lean 文件交互”部分的前五个小节非常有帮助。

## 7. 问题和疑难解答

如果您对上述任何步骤有任何疑问或遇到问题，请访问我们的 [Lean Zulip](https://leanprover.zulipchat.com/)聊天，以便我们为您提供帮助。

### 收集VS Code输出

如果您在使用Lean或此VS Code扩展时遇到问题，复制“Lean: Editor”输出面板中的输出对于其他人帮助您可能会很有帮助。您可以通过单击VS Code窗口右上角的∀符号并选择“Troubleshooting: Show Output”来打开“Lean: Editor”输出面板。
![[images/Pasted image 20240602184450.png]]