
# 如何贡献文档

非常感谢您对 StarRocks 文档的贡献！您的帮助对于改善文档至关重要！

在投稿前，请仔细阅读本文，以快速理解相关技巧、写作流程和文档模板。

你好世界~

## 提示

1. 语言：请至少使用一种语言，中文或英文。高度推荐双语版本。
2. 索引：当您添加一个主题时，您也需要在目录（TOC）文件中为该主题添加一个条目，例如，`[介绍](../docs/en/introduction/what_is_starrocks.md)`。**您的主题路径必须是从 `docs` 目录开始的相对路径。** 这个 TOC 文件最终会被渲染成我们官方网站上文档的侧边导航栏。
3. 图片：必须先将图片放入 **assets** 文件夹中。在文档中插入图片时，请使用相对路径，例如 `![测试图片](../../assets/test.png)`。
4. 链接：对于内部链接（指向我们官方网站上的文档链接），请使用文档的相对路径，例如 `[测试 md](./data_source/catalog/hive_catalog.md)`。对于外部链接，格式必须为 `[链接文本](链接URL)`。
5. 代码块：您必须为代码块添加一个语言标识符，例如，`sql`。
6. 目前不支持特殊符号。

## 写作过程

1. **写作阶段**：根据以下模板编写主题（使用 Markdown ），如果主题是新添加的，请将主题索引加入到 TOC 文件中。

   - *因为文档是用Markdown编写的，我们建议您使用markdown-lint来检查文档是否符合Markdown语法。*
   - *添加主题索引时，请注意* *其在TOC文件中的* *类别。* *例如，* ***Stream Load*** *主题* *属于* ***Loading*** *章节。*

2. **提交阶段**：创建一个拉取请求，以将文档更改提交到我们在GitHub上的文档仓库，英文文档位于[StarRocks仓库](https://github.com/StarRocks/starrocks)的`docs/`文件夹中（英文版本），中文文档位于[中文文档仓库](https://github.com/StarRocks/docs.zh-cn)中（中文版本）。

      > **注意**
      > 您的 PR 中的所有提交都应该进行签名。要签名一个提交，您可以添加 `-s` 参数。例如：
      > `commit -s -m "更新MV文档"`

3. 设置列表

   像这样的长长的设置列表在搜索中索引效果不佳，即使读者输入了设置的确切名称，他们也无法找到信息：

   ```markdown
   - setting_name_foo
   
     Details for foo
   
   - setting_name_bar
     bar 的详细信息
   ...
   ```

   相反，使用一个节标题（例如，`###`）作为设置名称，并移除文本的缩进：

   ```markdown
   ### setting_name_foo
   
   Details for foo
   
   ### setting_name_bar
   Details for bar
   ...
   ```

   |带有长列表的搜索结果：|带有 H3 标题的搜索结果|
|---|---|
   |![图片](https://github.com/StarRocks/starrocks/assets/25182304/681580e6-820a-4a5a-8d68-65852687a0df)|![图片](https://github.com/StarRocks/starrocks/assets/25182304/8623e005-d6e1-4b73-9270-8bc86a2aa680)|

4. **审查阶段**：

   审查阶段包括自动检查和人工审查。

   -  自动检查：提交者是否已签署贡献者许可协议（CLA），以及文档是否符合Markdown语法。
   -  人工审核：审核者将阅读并与您就文档内容进行沟通。之后，文档将被合并到 StarRocks 的文档仓库，并在官方网站上更新。

## 文档模板

- [函数](https://github.com/StarRocks/docs/blob/main/sql-reference/sql-functions/How_to_Write_Functions_Documentation.md)
- [SQL 命令模板](https://github.com/StarRocks/docs/blob/main/sql-reference/sql-statements/SQL_command_template.md)
- [加载数据模板](https://github.com/StarRocks/starrocks/blob/main/docs/loading/Loading_data_template.md)
- 审核阶段包括自动检查和人工审核。

这是因为 HTML 规范只允许[少数特定元素](https://html.spec.whatwg.org/multipage/syntax.html#void-elements)省略闭合标签，最常见的是 `<input>` 和 `<img>`。对于所有其他元素，如果你省略了闭合标签，原生 HTML 解析器会认为你从未结束过开放标签。例如，以下代码片段：
