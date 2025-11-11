<!---
{
  "id": "66726805-4497-4dce-a1ba-ccf930a721f8",
  "teaches": "Inserting Figures in LaTeX",
  "depends_on": [
    "00650b50-14de-471d-a347-246f47ffadde", 
    "05894bad-a8de-413a-86ce-166579682bbc"
  ],
  "author": "Stephan Bökelmann",
  "first_used": "2025-06-02",
  "keywords": ["LaTeX", "figures", "floats", "images", "vim"]
}
--->

# Inserting Figures in LaTeX

> In this exercise you will learn how to insert images into LaTeX documents using the `figure` environment. Furthermore we will explore captions and basic placement options.

### Introduction

Visual content such as images, diagrams, and plots are essential components of technical and scientific documents. In LaTeX, images are inserted using the `figure` environment together with the `graphicx` package.

Captions are added with the `\caption{...}` command inside the `figure` environment. This provides numbered captions and ensures consistency throughout the document.

Before using images, the `graphicx` package must be loaded in the preamble with:

```latex
\usepackage{graphicx}
```

Images should be provided in supported formats such as PDF, PNG, or JPG. They are typically placed in a `figures/` subdirectory.

### Further Readings and Other Sources

* [Overleaf: Inserting Images](https://www.overleaf.com/learn/latex/Inserting_Images)
* [LaTeX Wikibook - Floats, Figures and Captions](https://en.wikibooks.org/wiki/LaTeX/Floats,_Figures_and_Captions)
* [YouTube - LaTeX Figures Tutorial](https://www.youtube.com/watch?v=_pZbVoj-csI)
* [The Not So Short Introduction to LaTeX (Figures Section)](https://tobi.oetiker.ch/lshort/lshort.pdf)

---

## Tasks

### Prepare Assets

We will follow a clean directory structure which separates source files (`src/`) from figures (`figures/`). This structure is common for larger projects and helps to keep all files organized and maintainable, especially as the number of images and source files grows.

First, create the necessary directories:

```bash
mkdir -p src figures
```

Download the image files into the `figures/` subdirectory using `curl`:

```bash
curl -o figures/picture.png https://raw.githubusercontent.com/STEMgraph/66726805-4497-4dce-a1ba-ccf930a721f8/master/assets/picture.png
curl -o figures/chart.png https://raw.githubusercontent.com/STEMgraph/66726805-4497-4dce-a1ba-ccf930a721f8/master/assets/chart.png
```

Then, create an empty LaTeX source file inside `src/` with the touch command:

```bash
touch src/main.tex
```

For now, you can simply store the empty file. We will build up its content step by step.

Your directory structure should now look like this:

```text
.
├── figures
│   ├── chart.png
│   └── picture.png
└── src
    └── main.tex
```

### Task 2: Insert a Simple Figure

Open `src/main.tex` again and insert the following minimal structure and simple figure:

```latex
\documentclass{article}
\usepackage{graphicx}

\begin{document}

\section{Simple Figure}

\begin{figure}
  \centering
  \includegraphics[width=0.5\textwidth]{figures/picture.png}
  \caption{A simple diagram}
\end{figure}

\end{document}
```

Compile with:

```bash
pdflatex src/main.tex
```

Verify that the image is inserted with a caption.

### Task 3: Insert Another Figure with Placement Option

Extend your file with another section:

```latex
\section{Another Figure}

\begin{figure}[h]
  \centering
  \includegraphics[width=0.7\textwidth]{figures/chart.png}
  \caption{A sample chart}
\end{figure}
```

Recompile and observe where LaTeX positions the figure.

### Task 4: Insert Multiple Figures

Add a third section to practice multiple figures:

```latex
\section{Multiple Figures}

\begin{figure}
  \centering
  \includegraphics[width=0.4\textwidth]{figures/picture.png}
  \caption{First appearance of picture}
\end{figure}

\begin{figure}
  \centering
  \includegraphics[width=0.4\textwidth]{figures/chart.png}
  \caption{Second appearance of chart}
\end{figure}
```

Recompile and observe the layout.

---

## Questions

1. Why is the `graphicx` package necessary for including images?
2. What happens if you omit `\centering` inside a `figure`?
3. How does LaTeX number the figures automatically?
4. Why is separating figures into their own folder helpful?

---

## Advice

Always place images in a separate subdirectory to keep your project organized. Use captions consistently so that all figures are numbered automatically. Try not to worry too much about exact positioning yet; the main goal is to build good habits in structuring your documents. Later, you will learn how to reference figures properly and gain more control over their placement.
