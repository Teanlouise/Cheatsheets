

# Setup 
- install perl
- Add to PATH on control panel if error 'Recipe terminated with fatal error: spawn latexmk ENOENT'
-  install MikTeX for Windows
-  `latexmk` : run this to check
- https://mg.readthedocs.io/latexmk.html

# Preamble

## 1. Create a document
```
\documentclass[a4 paper, 12pt]{article}
```
- types: book, report, beamer (presentation)
- font: default font is 10pt
- page size: default to US paper size

## 2. Create a title
```
\title{An amazing title}
\author{Tean}
\date{\today}
```

## 3. Imports
```
\usepackage{pagkage_name}
```

## 4. State any global variables
- `\newtheorem{theorem}{Theorem_Name}` : creates a theorem


# Body

## 1. Start document
```
\begin{document}

% everything else goes in here

\end{document}
```

## 2. Create title
```
\maketitle
```

## 3. Table of contents
```
\tableofcontents
```

## 4. Add any other settings

### Margins
- set new margins (default is very large)
```
\usepackage{geometry}

\geometry{margin=2cm}
```

### Bibliography
```
\include{name.tex} 

\input{name.tex} 
```
- `\include`: smarter
- `\input` : just puts text in


## 5. Create sections
```
\section{Section 1}

\subsection{Subsection 1}
```
- also subsubsection, chapter, part...

## 6. Environments

### Alignment
```
\begin{alignment}
    % text goes here
\end{alignment}
```
- {flushleft}
- {flushright}
- {center} 

or 
```
\begin{environment}
    \centering
    % text goes here
\end{environment}
```
- `\centering` : if already in an environment

### Images
```
\usepackage{graphicx}
\usepackage{float}


\begin{figure} [H]
    \includegraphics[width=0.6\textwidth]
        {test.jpg}
    \caption{This is a wonderful image!}
\end{figure}
```
- float: put images where placed
- [H]: makes the figure go where its suppose to

or
```
\begin{center}
\includegraphics{name.png}
\end{center}
```

### Code
```
\usepackage{listings}


\begin{lstlisting}[language=python]
    def hello_world():
        print("Hello World!")
\end{lstlisting}
```
- `\lstinginputlisting[language=python]{test.py}` : adds code from other files

### Ordered List
```
\begin{enumerate}
    \item Item1
    \item Item2
\end{enumerate}
```

### Unordered List
```
\begin{itemize}
    \item Item
    \item Item
\end{itemize}
```

### Table
```
\begin{tabular}{c|c|c} 
    Heading1 & Heading2 & Heading3 \\    
    a & b & c \\
    d & e & f
\end{tabular}
```
- `{c|c|c}` : number of columns, letter is alignment (c,l,r), | puts lines between


# Formatting

### Text
```
\textbf{The text is bold}
\textit{The text is italic}
\underline{The text is underlined}
```

### New lines
```
\bigskip
\smallskip
\newline
\\
```

### Footnotes
```
This is text that needs a footnote. \footnote{Note for the footnote}
```


# Math
```
\usepackage{amsmath, amssymb, amsthm}


math is $display in-line here$
\[display math on own line\]


\begin{align*}
    numbers &= big_numbers \\
    small_numbers &= lots_numbers
\end{align*}
```

- `+` : addition
- `-` : subtrtaction
- `\times` : multiplication
- `\exp` or `x^{2}`: exponent (**)
- `x_{2}` : subscript
- `sqrt{z}` : square root
-  `\frac{a}{b}` : fraction
- `\left(\frac{a}{b}\right)` : fraction with brackets all over
- `\int_{-\infty}^{\infty}]8792347` : integral from -infinity to infinity
- `\sin`, `\cos`, `\tan`
- `\log x`, `\ln x`
- `\delta`, `\alpha`, `\Delta`
- `mathbb{R}` : real numbers
% texnique.xyz/

### Theorem
```
\begin{theorem}
    This is a theorem
\end{theorem}

\begin{proof}
    This is a proof
\end{proof}
```