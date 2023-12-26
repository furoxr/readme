
# 如何贡献文档

非常感谢您对 StarRocks 文档的贡献！您的帮助对于改进文档非常重要！

在投稿之前，请仔细阅读本文，以快速了解其中的技巧、写作流程和文档模板。

## 技巧

1. 语言：请至少使用一种语言，中文或英文。双语版本是高度首选。
2. 索引：添加主题时，还需要在目录（TOC）文件中添加该主题的条目，例如，`[introduction](../docs/en/introduction/what_is_starrocks.md)`。**主题的路径必须是从`docs`目录开始的相对路径。**该TOC文件最终将被渲染为我们官方网站上文档的侧边导航栏。
3. 图片：图片必须首先放入**assets**文件夹中。在文档中插入图片时，请使用相对路径，例如 `![测试图片](../../assets/test.png)`。
4. 链接：对于内部链接（指向我们官方网站上的文档的链接），请使用文档的相对路径，例如 `[test md](./data_source/catalog/hive_catalog.md)`。对于外部链接，格式必须是 `[链接文本](链接URL)`。
5. 代码块：您必须为代码块添加语言标识符，例如 `sql`。
6. 目前不支持特殊符号。

## 写作流程

1. **编写阶段**：根据以下模板编写主题（Markdown），如果是新添加的主题，则需要将主题的索引添加到 TOC 文件中。

   - *由于文档是用 Markdown 编写的，我们建议您使用 markdown-lint 来检查文档是否符合 Markdown 语法。*
   - *添加主题索引时，请注意其在 TOC 文件中的分类。例如，“**Stream Load**”主题属于“**Loading**”章节。

2. **提交阶段**：创建一个 pull request，将文档更改提交到 GitHub 上的文档仓库，英文文档位于 [StarRocks repository](https://github.com/StarRocks/starrocks) 的 `docs/` 文件夹（针对英文版本）和 [Chinese documentation repository](https://github.com/StarRocks/docs.zh-cn)（针对中文版本）。

      > **注意**
      > 您的 PR 中的所有提交都应该签名。要签署提交，您可以添加 `-s` 参数。例如：
      > `git commit -s -m "更新 MV 文档"`

3. 设置列表

   像这样的长设置列表在搜索中索引效果不佳，即使读者输入设置的确切名称也可能找不到信息：

   ```markdown
   - setting_name_foo
   
     foo 的详细信息
   
   - setting_name_bar
     bar 的详细信息
   ...
   ```

   相反，请使用节标题（例如 `###`）作为设置名称，并移除文本的缩进：

   ```markdown
   ### setting_name_foo
   
   foo 的详细信息
   
   ### setting_name_bar
   bar 的详细信息
   ...
   ```

   |带有长列表的搜索结果：|使用 H3 标题的搜索结果：|
|---|---|
   |![图片](https://github.com/StarRocks/starrocks/assets/25182304/681580e6-820a-4a5a-8d68-65852687a0df)|![图片](https://github.com/StarRocks/starrocks/assets/25182304/8623e005-d6e1-4b73-9270-8bc86a2aa680)|

4. **审核阶段**：

   审核阶段包括自动检查和人工审核。

   -  自动检查：检查提交者是否已签署贡献者许可协议（CLA）以及文档是否符合 Markdown 语法。
   -  人工审核：Committer 会阅读文档并与您沟通。文档将被合并到 StarRocks 文档仓库中，并在官方网站上更新。

## 文档模板

- [Functions](https://github.com/StarRocks/docs/blob/main/sql-reference/sql-functions/How_to_Write_Functions_Documentation.md)
- [SQL 命令模板](https://github.com/StarRocks/docs/blob/main/sql-reference/sql-statements/SQL_command_template.md)
- [加载数据模板](https://github.com/StarRocks/starrocks/blob/main/docs/loading/Loading_data_template.md)
