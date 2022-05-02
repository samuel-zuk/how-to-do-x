# LaTeX General Instructions

## Comments

#### Add a comment

For single-line comments, start a line with the "%" character.

```tex
\somecommand
% I am a comment
\begin{something}
...
```

#### Add a multiline comment

You can use the "comment" package for multiline comments.
In the document preamble, add:
```tex
\usepackage{comment}
```

Then:
```tex
\somecommand
\begin{comment}
    I am a comment and this won't be rendered
    Neither will this
    Hahahahahahaha
\end{comment}
\par{blah blah blah...}
```

Alternatively, a more hack-y solution is to add a new commmand that takes an input and does nothing with it. ([thanks ntjess on StackExchange!](https://tex.stackexchange.com/questions/87303/multi-line-block-comments-in-latex))
In the document preamble, add:
```tex
\newcommand{\comment}[1]{}
```

Then:
```tex
\somecommand
\comment{
    I am a comment and this won't be rendered
    Neither will this
    Hahahahahahaha
}
\par{blah blah blah...}
```

## Paragraph formatting

#### Add an indent at the start of a paragraph

In the document preamble, add:
```tex
\setlength\parindent{<LENGTH>}

% Example:
\setlength\parindent{0.5in}
```

#### Add spacing in between paragraphs

Use the "parskip" package.
In the document preamble, add:
```tex
\usepackage{parskip}
```

## Images

Use the "graphicx" package; point it at the folder with your images in it (relative to the directory the .tex file is in).
In the document preamble, add:
```tex
\usepackage{graphicx}
\graphicspath{{<PATH>}}

% Example:
\graphicspath{{./imgs/}}
```

#### Add an image

Add this to the place in the document where the image should be. The name of the file is its name relative to the path you specified with `\graphicspath`.

```tex
\includegraphics{filename}
```

#### Resize an image to fit a certain width
To make an image fit a certain width or height, add this argument to the `\includegraphics` directive. This can be in any unit or as a proportion of a predefined LaTeX length.

```tex
\includegraphics[width=<WIDTH>]{filename}
\includegraphics[height=<HEIGHT>]{filename}

% Examples:
\includegraphics[width=\textwidth]{filename}
\includegraphics[width=128px]{filename}
\includegraphics[height=0.5\textheight]{filename}
```

Here are some useful default lengths:

| Shorthand      | Description                      |
| -------------- | -------------------------------- |
| `\columnwidth` | Width of the current column      |
| `\linewidth`   | Width of the current line        |
| `\paperwidth`  | Width of the document page       |
| `\paperheight` | Height of the document page      |
| `\textwidth`   | Width of the current text block  |
| `\textheight`  | Height of the current text block |
