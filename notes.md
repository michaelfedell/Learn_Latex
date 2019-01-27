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

## Basic Formatting

### Abstracts

There's a preset abstract environment for LaTeX documents available via `\begin{abstract}`

This places the text at the top of the document using a special format

### Paragraphs

Paragraphs are separated by blank lines

To start a new line without starting a new paragraph, insert a _break line_ point by using `\\` or `\newline`

Care should be taken that multiple \\ or \newlines are not used to "simulate" paragraphs with larger spacing between them, as this can interfere with LATEX's typesetting algorithms

- `\vspace{5mm}` or other units to create vertical space
- `\smallskip` to create a small space
- `\medskip` to create a medium space
- `\bigskip` to create a large space

### Chapters and Sections

Sectioning is the easiest way to organize a document

- `\part{part}`
  - `\chapter{Chapter Name}`
    - `\section{Section Name}`
      - `\subsection{subsection}`
        - `\subsubsection{subsub}`
          - `\paragraph{para}`
            - `\subparagraph{subpara}`
    - `section*{Unnumbered Section}`
    - etc etc
*_part and chapter only available in `report` and `book` document classes_

[More info on sections/chapters](https://www.overleaf.com/learn/Sections_and_chapters)

### Tables

```latex
\begin{center}
\begin{tabular}{ l c r }
 cell1 & cell2 & cell3 \\
 cell4 & cell5 & cell6 \\  
 cell7 & cell8 & cell9
\end{tabular}
\end{center}
```

Will create a table with three columns, the first left-aligned, the second centered, and the third right-aligned

`&` separates columns in a line and `\\` moves to the next row

Complexity can be added to the tables via borders and spacing

`|` can be used around the column declarations to add vertical borders

`\hline` adds horizontal borders between rows

`[0.5ex]` adds vertical space between rows

More advanced example:

```latex
Table \ref{table:data} is an example of referenced \LaTeX{} elements.
\begin{table}[h!]
    \centering
    \begin{tabular}{||c c c c||}
        \hline
        Col1 & Col2 & Col2 & Col3 \\ [0.5ex]
        \hline\hline
        1 & 6 & 87837 & 787 \\
        2 & 7 & 78 & 5415 \\
        3 & 545 & 778 & 7507 \\
        4 & 545 & 18744 & 7560 \\
        5 & 88 & 788 & 6344 \\ [1ex]
        \hline
    \end{tabular}
    \caption{Table to test captions and labels}
    \label{table:data}
\end{table}
```

### Table of Contents

This is super easy in LaTeX!

Just add `\tableofcontents` to the beginning of your document to auto generate the TOC

Items can be manually added to the TOC by placing `\addcontentsline{toc}{\<level\>}{\<name of item\>}` in the document where the TOC reference should point to