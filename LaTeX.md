[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

![latex](./images/title_latex.png)

# Table of Contents
**[SETUP](#Setup)**
- [VSCode](#VSCode)
- [Basic-Format](#Basic-Format)


**[PREAMBLE](#Preamble)**
- [1. Create a document](#1.-Create-a-document)
- [2. Create a title](#2.-Create-a-title)
- [3. Imports](#3.-Imports)
- [4. Global variables](#4.-Global-variables)
- [5. Document Formatting](#5.-Document-Formatting)
    - [Margins](#Margins)
    - [Paragraph Format](#Paragraph-Format)
    - [List Spacing](#List-Spacing)
    - [Headers and Footers](#Headers-and-Footers)
- [Global-Preamble](#Global-Preamble})


**[BODY](#BODY)**
- [1. Start document](#1.-Start-document)
- [2. Create title](#2.-Create-title)
- [3. Table of contents](#3.-Table-of-contents)
- [4. Create sections](#4.-Create-sections)
- [5. Environments](#5.-Environments)
    - [Alignment](#Alignment)
    - [Text style](#Text-style)
    - [Images](#Images)
    - [Code](#Code)
    - [Numbered List](#Ordered-List)
    - [Bullet List](#Unordered-List)
    - [Table](#Table)
    - [Columns](#Columns)
- [6. Include other files](#6.-Include-other-files)
    - [Other TEX](#Other-TEX) 
    - [PDF](#PDF)
- [7. References](#7.-References)
- [8. Appendix](#8.-Appendix)



**[FORMATTING](#FORMATTING)**
- [Text style](#Text-style)
- [Font Size](#Font-Size)
- [New lines](#New-lines)
- [Links](#Links)
- [Text color](#Text-color)
- [Border](#Border)
- [Footnotes](#Footnotes)
- [Symbols](#Symbols)

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

### Basic Format
```
% PREAMBLE
\documentclass[a4 paper, 12pt]{article}

% Title
\title{Title text}
\author{Author text}
\date{\today}

% Custom Packages
\usepackage{myCustomPreamble}

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% DOCUMENT
\begin{document}

% Title
\maketitle

% Table of contents
\pagebreak
\tableofcontents
\listoffigures

% Header and Footer
\fancyhf{}
\rhead{Tean-louise Cunningham (42637460)}
\lhead{INFS3200 - Practical 3}

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

### Headers and footers
```
\usepackage{fancyhdr}
\pagestyle{fancy}
\setlength{\headheight}{40pt}

\fancyhf{}
\rhead{Header text for the right alignment}
\lhead{Header text for the left alignment}
\cfoot{\thepage}
```
- `\rfoot` footer in the right (also `\lfoot`)
- `\chead` header in the center
- be sure to load geometry margin first

## GLOBAL PREAMBLE
- Using MikTek

1. Create 'myCustomPreamble.sty' file.
2. Setup following by adding date and purpose.
```
\NeedsTeXFormat{LaTeX2e}
\ProvidesPackage{myCustomPreamble}[2020/30/06 Tean's Custom LaTeX Preamble]
```
3. Add all packages and accompanying settings. 
- Instead of `\usepackage{name}` replace with `\RequiredPackage{name}`
- See 'myPreamble.sty' for list of 

4. End the file
```
\endinput
```
5. In terminal, find directory of packages. 
- I found it at: `C:\Users\username\AppData\Local\Programs\MiKTeX 2.9\tex\latex\`
6. Make a new directory.
```
mkdir -p my_preamble
```
7. Create local repository.
- A bunch of stuff will download, took about 10minutes
```
miktexsetup --verbose --local-package-repository='C:\Users\username\AppData\Local\Programs\MiKTeX 2.9\tex\latex\my_preamble' --package-set=complete download
```
8. Move 'myPreamble.sty' into this folder.
9. Run `texhash`
10. Call within tex file.
```
\usepackage{myPreamble}
```

The steps were followed from a combination of these resources:
- https://tex.stackexchange.com/questions/77/how-to-make-a-standard-preamble-into-a-package
- https://www.overleaf.com/learn/latex/Writing_your_own_package#General_structure
- https://miktex.org/howto/local-repository 
- https://tex.stackexchange.com/questions/1137/where-do-i-place-my-own-sty-or-cls-files-to-make-them-available-to-all-my-te
- Can set as a class instead of package: Change to class -> .cls, \LoadClass, call with \documentclass{}




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

## 3. Table of contents & Figures
```
\tableofcontents
\listoffigures
```

## 4. Create sections
```
\section{Section Name}

\subsection{Subsection Name}
```
- also subsubsection, chapter, part...
- `\section*{Section Name}` : to remove numbers from section names
- `\setcounter{section}{1}` : set the section number

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
\usepackage[export]{adjustbox}
\setlength{\intextsep}{5pt plus 2pt minus 2pt}
\setlength\belowcaptionskip{-1ex}
\usepackage[font=small,skip=2pt]{caption}

\begin{figure} [H]
    \includegraphics[width=0.6\textwidth, frame]
        {test.jpg}
    \caption{This is a wonderful image!}
\end{figure}
```
- float: put images where placed
- [H]: makes the figure go where its suppose to
- `adjustbox` and `frame` is to add a border
- `\intextsep`: reduce whitespace between figure and paragraph

or
```
\begin{center}
\includegraphics{name.png}
\end{center}
```

### Caption
```
\usepackage[font=small,skip=5pt]{caption}
```
- reduce space between figure and caption




### Code
```
\usepackage{listings}


\begin{lstlisting}[language=python]
    def hello_world():
        print("Hello World!")
\end{lstlisting}
```
- `\lstinputlisting[language=python]{test.py}` : adds code from other files

### Ordered List
```
\begin{enumerate}
    \item Item1
    \item Item2
\end{enumerate}
```
- `\begin{enumerate}[resume]` : to continue counter from previous enum environment
`\setlist[enumerate]{font=\bfseries}`: make numbers only bold

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

### Columns
```
\usepackage{multicol}

\begin{multicols}{#cols}
    ....
    \columnbreak
    ....
\end{multicols}
```
- `columnbreak`: manually set where to split columns, otherwise auto is equal
- `\setlength{\columnsep}{6cm}`: before begin multicols
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


## 7. References
```
\addcontentsline{toc}{section}{References}
\includepdf[pagecommand=\section*{References}, 
            offset=0 0cm]
            {References.pdf}
```

## 8. Appendix
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

### Symbols
```
\usepackage{amssymb}

% In text
$\symbol$

% With lists
\renewcommand{\labelitemi}{$symbol$}

\begin{itemize}
    \item[$\symbol$] .....
\end{itemize}
```
- `\renewcommand{\labelitemi}{$symbol$}`: set new default for list bullet points in env
- `\item[$symbol$]`: set specific \item with this symbol as bullet point
- symbols (http://milde.users.sourceforge.net/LUCR/Math/mathpackages/amssymb-symbols.pdf)
    - `\blacksquare`
    - `\square`
    - `$\leq$`: Less than or equal to
    - `$\leqslant$`: Less than or equal to slanted
    - `$\geq$`: Greater than or equal to
    - `$\geqslant$`: Greater than or equal to slanted
    - `$>$`: Greater than
    - `$<$`: Less than
    - `$\neg$`: Negation


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
