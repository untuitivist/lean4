这是 Lean 4 的数学库 [mathlib4](https://github.com/leanprover-community/mathlib4)，它是 Lean 定理证明器的用户维护库，包含了编程基础设施、数学以及利用前者并允许开发后者的策略。

### 安装

你可以在[我们的网站](https://leanprover-community.github.io/get_started.html)上找到详细的安装 Lean、mathlib 和支持工具的说明。

### 使用 `mathlib4` 作为依赖项

请参考 [https://github.com/leanprover-community/mathlib4/wiki/Using-mathlib4-as-a-dependency](https://github.com/leanprover-community/mathlib4/wiki/Using-mathlib4-as-a-dependency)

### 实验

安装好了吗？为什么不从 [教程项目](https://leanprover-community.github.io/install/project.html) 开始呢？

有关更多指针，请参阅 [Learning Lean](https://leanprover-community.github.io/learn.html)。

### 文档

除了上面的安装指南和[Lean的一般文档](https://leanprover.github.io/documentation/)之外，mathlib的文档包括：

- [mathlib4文档](https://leanprover-community.github.io/mathlib4_docs/index.html)：从源`.lean`文件[自动生成的文档](https://github.com/leanprover/doc-gen4)。
- [当前涵盖的理论](https://leanprover-community.github.io/theories.html)的描述，以及数学家的[概述](https://leanprover-community.github.io/mathlib-overview.html)。
- 一些不特定于mathlib的[额外Lean文档](https://leanprover-community.github.io/learn.html)（参见“其他主题”）
- 为希望[为mathlib做贡献的人](https://leanprover-community.github.io/contribute/index.html)提供的文档

mathlib周围的大部分讨论发生在一个[Zulip聊天室](https://leanprover.zulipchat.com/)中，欢迎加入，或者不注册就可以阅读。欢迎所有水平的用户提问！我们还提供了一个[公开讨论的归档](https://leanprover-community.github.io/archive/)，这对快速查找信息很有用。

### 从Lean 3迁移

对于熟悉Lean 3并想在Lean 4中提升速度并迁移其现有Lean 3代码的用户，我们有：

- Lean 3用户的[生存指南](https://github.com/leanprover-community/mathlib4/wiki/Lean-4-survival-guide-for-Lean-3-users)
- 在其他项目上运行`mathport`的[说明](https://github.com/leanprover-community/mathport#running-on-a-project-other-than-mathlib)。 `mathport`是社区用于将整个`mathlib`从Lean 3迁移到Lean 4的工具。

### 贡献

关于对`mathlib`的完整贡献文档位于[社区指南](https://leanprover-community.github.io/contribute/index.html)

该过程与其他项目不同，不应该fork存储库。而是应通过[Zulip](https://leanprover.zulipchat.com)请求非主分支的写入权限，介绍自己，提供GitHub句柄以及您计划做出的贡献。您可能希望订阅`mathlib4`流

- 要获取预编译的`olean`文件，请运行`lake exe cache get`。（跳过此步骤将导致下一步非常缓慢。）
- 要构建`mathlib4`，请运行`lake build`。
- 要构建和运行所有测试，请运行`make`。
- 您可以使用`lake build Mathlib.Import.Path`构建特定文件，例如`lake build Mathlib.Algebra.Group.Defs`。
- 如果您添加了新文件，请运行以下命令以更新`Mathlib.lean`

  ```shell
  find Mathlib -name "*.lean" | env LC_ALL=C sort | sed 's/\.lean//;s,/,.,g;s/^/import /' > Mathlib.lean
  ```

### 准则

mathlib有以下必须遵循的准则和约定

- [样式指南](https://leanprover-community.github.io/contribute/style.html)
- 关于[命名约定](https://leanprover-community.github.io/contribute/naming.html)的指南
- [文档样式](https://leanprover-community.github.io/contribute/doc.html)

### 下载缓存的构建文件

您可以运行`lake exe cache get`来下载由`mathlib4`的自动化工作流计算出的缓存构建文件。
如果`tar`终止时出现错误，则表示您可能已经得到损坏的文件。
在这种情况下，请运行`lake exe cache get!`来覆盖它们（`get`不会尝试重新下载相同的文件）。

调用`lake exe cache`以查看其帮助菜单。

### 构建HTML文档

在本地构建HTML文档很简单，但可能需要一些时间：

```shell
lake -Kdoc=on build Mathlib:docs
```

然后可以在`build/doc`中找到HTML文件。

### 依赖项

如果您是mathlib的贡献者并且想要更新依赖项，请使用`lake update -Kdoc=on`。
这将正确更新`lake-manifest.json`文件。
在提交对此文件的更改后，您需要发起PR。

## 维护者:

有关更详细信息的列表，请参见 https://leanprover-community.github.io/teams/maintainers.html