
# Table of Contents
**[SETUP](#Setup)**
- [VSCode](#VSCode)
- [Custom ](#Custom)

**[PREAMBLE](#Preamble)**
- [1. Create a document](#1.-Create-a-document)
- [2. Create a title](#2.-Create-a-title)
- [3. Imports](#3.-Imports)
- [4. Global variables](#4.-Global-variables)
- [5. Document Formatting](#5.-Document-Formatting)
    - [Margins](#Margins)
    - [Paragraph Format](#Paragraph-Format)
    - [List Spacing](#List-Spacing)

**[BODY](#BODY)**
- [1. Start document](#1.-Start-document)
- [2. Create title](#2.-Create-title)
- [3. Table of contents](#3.-Table-of-contents)
- [4.Create sections](#4.-Create-sections)
- [5. Environments](#5.-Environments)
    - [Alignment](#Alignment)
    - [Text style](#Text-style)
    - [Images](#Images)
    - [Code](#Code)
    - [Numbered List](#Ordered-List)
    - [Bullet List](#Unordered-List)
    - [Table](#Table)
- [6. Include other files](#6.-Include-other-files)
    - [Other TEX](#Other-TEX) 
    - [PDF](#PDF)
- [7. Appendix](#7.-Appendix)


**[FORMATTING](#FORMATTING)**
- [Text style](#Text-style)
- [Font Size](#Font-Size)
- [New lines](#New-lines)
- [Links](#Links)
- [Text color](#Text-color)
- [Border](#Border)
- [Footnotes](#Footnotes)

**[MATH](#MATH)**


# SETUP
- install perl
- Add to PATH on control panel if error 'Recipe terminated with fatal error: spawn latexmk ENOENT'
-  install MikTeX for Windows
-  `latexmk` : run this to check
- https://mg.readthedocs.io/latexmk.html

### VSCode
- `LaTeX Workshop` : extension to use LaTex
- `Spell Right` : spell checker (use ctrl+. for shortcut to see spelling suggestions) 

### Custom
```
% PREAMBLE
% Setup
\documentclass[a4 paper, 12pt]{article}

% Title
\title{DECO2500 - INDIVIDUAL REPORT \\ Feedback 1}
\author{Tean-louise Cunningham (42637460)}
\date{17 April 2020}

% Margins
\usepackage{geometry}
\geometry{margin=2cm}

% Paragraph
\setlength{\parindent}{2em}
\setlength{\parskip}{1em}

% Text Formatting
\usepackage[utf8]{inputenc}
\usepackage[english]{babel}

% List spacing
\usepackage{enumitem}
\setlist{noitemsep, topsep=0pt}
\setlist[enumerate]{parsep=5pt} 

% Text Color
\usepackage{xcolor}

% Hyperlinks
\usepackage{hyperref}
\hypersetup{
    colorlinks=true,
    linkcolor=black,
    filecolor=black,      
    urlcolor=blue,
}

% Appendix
\usepackage{appendix}

% Include pdf
\usepackage{standalone}
\usepackage{pdfpages}

% Borders
\usepackage{mdframed}

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% DOCUMENT
\begin{document}

% Title
\maketitle

% Table of contents
\pagebreak
\tableofcontents

% Body
\pagebreak
\section{Introduction}
% Other text goes here

% Appendix
\pagebreak
\appendix
\addappheadtotoc
\appendixpage
\section{Appendix Name}

\end{document}
```
# PREAMBLE

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

## 4. Global variables
- `\newtheorem{theorem}{Theorem_Name}` : creates a theorem


## 5. Document Formatting

### Margins
- set new margins (default is very large)
```
\usepackage{geometry}
\geometry{margin=2cm}
```

### Paragraph Format
```
\setlength{\parindent}{2em}
\setlength{\parskip}{1em}
```

### List spacing
```
\usepackage{enumitem}

\setlist{noitemsep, topsep=0pt}
\setlist[enumerate]{parsep=5pt} 
```
- `setlist` : with no parameters applies to all or add [list_type] for just that list
- `noitemsep` : no spacing between list items
- `topsep=0pt` : removes some of the spacing added by parskip
- `parsep` : adds spacing between list items 


# BODY

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

## 4. Create sections
```
\section{Section Name}

\subsection{Subsection Name}
```
- also subsubsection, chapter, part...
- `\section*{Section Name}` : to remove numbers from section names

## 5. Environments

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

Or to center text vertically
```
\begin{center}
    \vspace*{\stretch{1}}
    % text here
    \vspace*{\stretch{1}}
\end{center}
```

### Text style
```
\begin{itshape}
    % this text will all be italic
\end{itshape}
```

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


## 6. Include other files

### Other TEX
```
\include{file_name} 
OR
\input{file_name} 
```
- `\include`: smarter, outs on new page
- `\input` : just puts text in
- file needs to be in same or lower directory {Lower/file_name}

### PDF
```
\usepackage{standalone}
\usepackage{pdfpages}

\includepdf[pages=1,pagecommand=\subsection{Section Name}, offset=0 -1.5cm]{File_name.pdf}
```
- pdf gets put on new page
- `pages=1` : select pages, `-` means all, `2-` is page 2 till the end
- `pagecommand=\subsection{Section Name}` : if including pdf in Appendix this will put the section name with pdf so its on the same page as each other   
- `offset=0 -1.5cm` : How far pdf starts from top of the page, otherwise overlaps


## 7. Appendix
```
\usepackage{appendix}

\appendix
\appendixpage
\addappheadtotoc
\section{Appendix 1 Name}
```
- `\appendixpage` : adds 'Appendices' title, can add as many time as want
- `\addappheadtotoc` : adds appendix list to table of contents



# FORMATTING

### Text style
```
\textbf{The text is bold}
\textit{The text is italic}
\underline{The text is underlined}
```

### Font Size
```
\Huge
\Large
\Small
```

### New lines
```
\bigskip
\smallskip
\newline
\\
```
- can use `\\` in text to split text over 2 lines eg. {Title \\ Name}

### Links
```
\usepackage{hyperref}
\hypersetup{
    colorlinks=true,
    linkcolor=black,
    filecolor=black,      
    urlcolor=blue,
}

\href{https://youtu.be/BRX7kF7ynSQ}{text to display}
```

### Text color
```
\usepackage{xcolor}

\textcolor{color_name}{Text goes here}
```
- black, blue, brown, cyan, darkgray, gray, green, lightgray, lime, magenta, olive, orange, pink, purple, red, teal, violet, white, yellow

### Border
```
\usepackage{mdframed}

\begin{mdframed}[linewidth=2pt]
    % text here or include tex file
\end{mdframed}
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
- `-` : subtraction
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