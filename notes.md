# Learn LaTeX in 30 minutes

## What is LaTeX

Latex is a tool used for producing standard-format, professional quality documents based on templating rules, separating the content creation from the document design process.

Great for creating research documents, reports, books, and even snippets for markdown documents

Highly extensible through libraries and packages

Can also pull from a large number of available templates

## Essentials

### Common elements

1. Class
    The first clause is typically the `\documentclass{article}`. `article` is the most common/basic type of document class, but many others are available for resumes, scientific papers, etc
2. Begin
    Start of document marked by the `\begin{document}` clause
3. Body

### Preamble

\documentclass[settings]{class} allows the user to specify `settings` like fontsize, papersize, etc whereas `class` defines the type of document to be created

[more options for page size and margins](https://www.overleaf.com/learn/Page_size_and_margins)

`\usepackage[utf8]{inputenc}` specifies the encoding type to use - this line should always be added unless you specifically need another

`\title{title}` can be used to add a title
`\author{author \thanks{ack}}` adds an author and acknowledgement
`\date{Month 2019}` adds a date to the paper

`\maketitle` can be added to the _body_ to insert the title

### Comments

Comments are prefaced with `%` and not printed in the document output

### Style

To format a block of text, you lead with a `\text` tag and then place the block of text in `{}`s.

- **Bold**: `\textbf{}`
- _Italic_: `\textit{}`
- __Underline__: `underline{}`
- `\emph{}` will emphasize some piece of text depending on the context

### Images

Images are not supported by base LaTeX but can be easily included by using the `graphicx` package.

This is done by inlcluding `\usepackage{graphicx}` in the **preamble**

Images can be included in the document by then using `\includegraphics{...}`

Images will be searched for in the directory set by `\graphicspath{...}`

It is best to leave out the image extension and let LaTeX find it on its own.

### Captions, Labels, and References

Images can be given captions, labels, and references by means of the `figure` environment.

```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.25\textwdith]{mesh}
    \caption{a nice plot}
    \label{fig:mesh}
\end{figure}

As you can see in the figure \ref{fig:mesh},
the function grows near 0, Also, in the page \pageref{fig:mesh}
is the same example
```

For the most part, images should always be placed in a `figure` environment so that latex knows how to position, style, and reference the image

### Creating lists in latex

Lists are creating using an _environment_ (surrounded wiht `\begin` and `\end` tags)

List items are always prefaced with the `\item` tag (like `<li>` in html)

Unordered lists are begun with `\begin{itemize}` whereas ordered lists are begun with `\begin{enumerate}`

## Adding math to LaTeX

Inline expressions are surrounded by `$` tags  
alternatively, `\( ... \)` or `\begin{math} ... \end{math}` can be used

_Displayed_ mode has two versions, numbered and unnumbered

_Unnumbered_ equations are placed on their own line surrounded by `\[ ... \]`

_Numbered_ equations are wrapped in an _equation environment_
e.g.

```latex
\begin{equation}
...
\end{equation}
```

Many more math commands are available with the inclusion of the **amsmath** package

- [Mathematical expressions](https://www.overleaf.com/learn/Mathematical_expressions)
- [Subscripts and superscripts](https://www.overleaf.com/learn/Subscripts_and_superscripts)
- [Brackets and Parentheses](https://www.overleaf.com/learn/Brackets_and_Parentheses)
- [Fractions and Binomials](https://www.overleaf.com/learn/Fractions_and_Binomials)
- [Aligning Equations](https://www.overleaf.com/learn/Aligning_equations_with_amsmath)
- [Operators](https://www.overleaf.com/learn/Operators)
- [Spacing in math mode](https://www.overleaf.com/learn/Spacing_in_math_mode)
- [Integrals, sums and limits](https://www.overleaf.com/learn/Integrals,_sums_and_limits)
- [Display style in math mode](https://www.overleaf.com/learn/Display_style_in_math_mode)
- [List of Greek letters and math symbols](https://www.overleaf.com/learn/List_of_Greek_letters_and_math_symbols)
- [Mathematical fonts](https://www.overleaf.com/learn/Mathematical_fonts)
