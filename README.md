# LaTeX Format Writing Codex Skill

这个项目提供了一个 skill：`latex-format-writing`。

它的作用很简单：在写作、翻译、讲解或编辑文本时，只有数学公式、变量、数学符号等内容会被转成 LaTeX 格式；普通文字、标点和非数学内容保持不变，同时，这些格式可以通过MathType插件的一键转换正确的渲染为数学公式。

##使用前提

已经在Word中安装好MathType插件，这个插件的获取和安装并不复杂，在此并不赘述。后面也提供了可参考的下载地址

## 规则

- 行内数学表达式使用 `$...$`。
- 行间公式使用 `\[...\]`。
- 只处理数学内容，不改普通正文。

## 额外说明

以上规则本质上你可以使用【Word】的【替换】功能实现，大部分AI复制下来的公式（比如DeepSeek），其行间公式是正确用\[.....\],但行内公式为\(.....\),使得MathType无法识别（本质上是一个TeX而非Latex格式的区别），你可以自行替换即可。



## 项目结构

```text
latex-format-writing-skill/
  README.md
  LICENSE
  skills/
    latex-format-writing/
      SKILL.md
      agents/
        openai.yaml
```

## 安装到 Codex 全局 skills

Windows PowerShell：

```powershell
$target = Join-Path $HOME ".codex\skills\latex-format-writing"
New-Item -ItemType Directory -Force -Path (Split-Path $target) | Out-Null
Copy-Item -Recurse -Force ".\skills\latex-format-writing" $target
```

安装后，Codex 会在全局 skill 目录中发现它：

```text
%USERPROFILE%\.codex\skills\latex-format-writing
```

如果你的环境设置了 `CODEX_HOME`，全局目录通常是：

```text
$CODEX_HOME\skills
```

## 调用 skill

可以显式调用：

```text
使用 $latex-format-writing，把下面内容中的数学公式按 LaTeX 格式输出，普通文字不要改。
```

也可以作为默认写作习惯使用：当文本里出现公式、变量、希腊字母、上下标、积分、求和、矩阵等数学内容时，Codex 会按该 skill 的规则输出。

## 配合 MathType 一键转公式

推荐流程：

1. 先安装 MathType。
2. 在 Codex 中调用 `$latex-format-writing`，让它把文档里的数学内容整理成 LaTeX：行内用 `$...$`，行间用 `\[...\]`。
3. 把生成的内容粘贴到 Word、PowerPoint 或 WPS。
4. 使用 MathType 的 TeX/LaTeX 转换功能，把 LaTeX 文本批量转换为可编辑公式。

MathType 官方下载入口：

- MathType 下载总页：https://store.wiris.com/en/products/mathtype/download
- Windows 中文版下载页：https://store.wiris.com/zh/products/mathtype/download/windows

说明：不同版本和语言界面中的按钮名称可能略有不同，常见名称包括 `Convert Equations`、`转换公式`、`Toggle TeX`、`TeX/LaTeX` translator。使用前建议先备份文档，因为批量转换通常不容易逐项撤销。

## Skill 内容摘要

`latex-format-writing` 告诉 Codex：

- 只给数学公式和数学字符加 LaTeX 定界符。
- 行内数学表达式使用 `$...$`。
- 行间公式使用 `\[...\]`。
- 普通文字、说明文字、非数学标点、非数学代码块保持原样。

## License

MIT
