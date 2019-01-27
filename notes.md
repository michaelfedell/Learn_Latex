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

### Formatting

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

