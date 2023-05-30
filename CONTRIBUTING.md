# 贡献指南

man-page-translation-plan 是一个自发性的项目。欢迎、鼓励和赞赏您的贡献。这对于项目的发展也是必不可少的。

首先，请花点时间回顾一下我们的行为准则。

这些指导方针是为了更好地解决大量悬而未决的问题和拉取请求。请仔细阅读。

最重要的是，好心地去寻找。这样可以确保你的贡献没有被覆盖。


## 格式(重要！！！)

```
type(scope)!: subject
```

- `type`: 提交的类型如下:

  - `create`: 新增文档.
  - `create to exist`: 新增同名文档.
  - `update`: 更新文档.
  - `delete`: 删除文档

- `scope`: 提交更改的代码库部分。如果它对许多部分进行了更改，或者如果没有特别修改任何部分，则保留空白而不带括号
  Examples:

  - Commit that changes the `git` plugin:
  ```
  feat(git): add alias for `git commit`
  ```

  - Commit that changes many plugins:
  ```
  style: fix inline declaration of arrays
  ```

  For changes to plugins or themes, the scope should be the plugin or theme name:

  - ✅ `fix(agnoster): commit subject`
  - ❌ `fix(theme/agnoster): commit subject`

- `!`: this goes after the `scope` (or the `type` if scope is empty), to indicate that the commit
  introduces breaking changes.

  Optionally, you can specify a message that the changelog tool will display to the user to indicate
  what's changed and what they can do to deal with it. You can use multiple lines to type this message;
  the changelog parser will keep reading until the end of the commit message or until it finds an empty
  line.

  Example (made up):

  ```
  style(agnoster)!: change dirty git repo glyph

  BREAKING CHANGE: the glyph to indicate when a git repository is dirty has
  changed from a Powerline character to a standard UTF-8 emoji. You can
  change it back by setting `ZSH_THEME_DIRTY_GLYPH`.

  Fixes #420

  Co-authored-by: Username <email>
  ```

- `subject`: a brief description of the changes. This will be displayed in the changelog. If you need
  to specify other details, you can use the commit body, but it won't be visible.

  Formatting tricks: the commit subject may contain:

  - Links to related issues or PRs by writing `#issue`. This will be highlighted by the changelog tool:
    ```
    feat(archlinux): add support for aura AUR helper (#9467)
    ```

  - Formatted inline code by using backticks: the text between backticks will also be highlighted by
    the changelog tool:
    ```
    feat(shell-proxy): enable unexported `DEFAULT_PROXY` setting (#9774)
    ```



----