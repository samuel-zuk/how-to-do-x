# LaTeX General Instructions

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
