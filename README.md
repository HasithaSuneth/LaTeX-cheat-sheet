# LaTeX-cheat-sheet
```
% Document will be printed on a4 paper, using the 12pt default font
% Define that we want to use the report class template
% Other classes : article, book, letter, slides and others
% In the preamble we define document wide rules
% Commands start with a name [optional arguments] {required arguments}
% twocolumn : 2 column pages
% titlepage : \maketitle generates a title page
% legno : Puts equation numbers on the left side
% flegn : Left align equations versus center
% twoside : Print on both sides of paper
% openright : If twoside is used chapters begin on right hand page
% landscape : If listed it displays in landscape

% --- Paper Types ---
% Paper type : letterpaper (11 x 8.5 in), a4paper (29.7 x 21 cm)
% legalpaper (14 × 8.5 in), a5paper (21×14.8 cm), 
% executivepaper (10.5×7.25 in), and b5paper (25×17.6 cm)
\documentclass[a4paper,12pt]{book}

% Change the font family to sans serif
% \renewcommand{\familydefault}{\sfdefault}

% --- LANDSCAPE, 2 COLUMNS & CUSTOM MARGINS ---

% \documentclass[a4paper,12pt, landscape, twocolumn]{book}

% You can define custom margins
% \usepackage[a4paper, inner=1.7cm, outer=2.7cm, top=2cm, 
% bottom=2cm, bindingoffset=1.2cm]{geometry}

% --- END LANDSCAPE ---

% --- PACKAGES ---

% You can import packages to add functionality
% Get more info on any package by typing texdoc PackageName in
% the terminal or command line

% Define that we want to use English hyphenation
% http://mirrors.rit.edu/CTAN/macros/latex/required/babel/base/babel.pdf
% Page 18 for list of languages
\usepackage[english]{babel}

% Use Helvetica instead of the normal sans serif font
% Others : 
% mathpazo (Palatino (Roman))
% mathptmx (Times (Roman))
% avant (Avant Garde (Sans Serif))
% courier (Courier (Typewriter))
% chancery (Zapf Chancery (Roman))
% bookman (Bookman (Roman) Avant Garde (Sans Serif) Courier (Typewriter))
% newcent (New Century, Avant Garde, Courier)
% charter (Charter (Roman))
\usepackage[scaled=.92]{helvet}

% Improve justification document wide
% \usepackage{microtype}

% Used to create filler text
\usepackage{blindtext}

% Used to include pictures
\usepackage{graphicx}

% Used to wrap text around pictures
\usepackage{wrapfig}

% Used to compact lists
\usepackage{enumitem}

% Used to customize the page layout of your LaTeX documents
\usepackage{fancyhdr}

% Improve output of math formulas 
\usepackage{amsmath}

% ----- Custom Commands -----

% You can define your own commands
% Anytime you type \NTT\ New Think Tank will show
\newcommand{\NTT}{New Think Tank}

% Or, New Think Tank in bold 
\newcommand{\NTTB}{\textbf{New Think Tank}}

% We can add styling to whatever text is passed
\newcommand{\typew}[1]{\texttt{#1}}


% ----- End of Custom Commands -----

% Used to create an index
\usepackage{index}
\makeindex

% Preamble ends here and the document begins
% This block is called the environment
\begin{document}
\title{\Large{\textbf{LaTeX Tutorial}}}
\author{By Derek Banas}
\date{December 21, 2018}
% Prints the title, author and date
\maketitle
\let\cleardoublepage\clearpage
% Print a table of contents using info in section headings
% Run Typeset twice to create it
\tableofcontents
% Use roman numeral page numbering
% \pagenumbering{roman}
% Start numbering with page 2
% \setcounter{page}{2}

\pagestyle{fancy}
% Clear default headers & footers
\fancyhf{}

% Draw a decorative line at the top & bottom of the page
\renewcommand{\headrulewidth}{2pt}
\renewcommand{\footrulewidth}{1pt}

% Use different headers for even & odd pages
% leftmark : Chapter title, number, LE - left side on even pages
% Uppercase by default
\fancyhead[LE]{\leftmark}

% rightmark : Chapter title, number, RO - right side on odd pages
% Make lowercase
\fancyhead[RO]{\nouppercase{\rightmark}}

% Use the same footer for pages
\fancyfoot[LE,RO]{\thepage}

% Define the page style for all pages going forward
\chapter{Chapter Name}
\blindtext
\section{A Section}

% If you want to include formulas in the blind text use this
\blindmathtrue

% Squeeze another line on to the previous page
\enlargethispage{\baselineskip}

% Create a block of random text [Define repetition]
\blindtext[2]

% Create different lists
\blinditemize
\blindenumerate
\blinddescription

% Add a page break and stretch text to fill the page
% \pagebreak

% Add a page break, but don't stretch text
\newpage

\blindtext

% --- Using Pictures ---
% Define where we want the image placed
% h : Here, t : Top of page, b : Bottom, p : Separate Page
\begin{figure}[ht]
\centering

% Include picture and define width (height automatically scales)
% Also scale=0.5 (Scales by half)
% angle=90 (Rotate 90 degrees)
\includegraphics[width=8cm]{pic.png}
\end{figure}
\blindtext

\newpage

\section*{Wrap Image}

% Group the text and image
\begingroup

% Set space above and below float to 0
\setlength{\intextsep}{0pt}

% Set distance between columns
\setlength{\columnsep}{15pt}

% Text wraps around images
% Position image to the right with r
% Also can use l : Left, i : Inside Edge and o : Outside Edge
% 0.45\textwidth : Size image width relative to the text width
\begin{wrapfigure}{r}{0.45\textwidth}
\centering
% Place image
  \includegraphics[width=\linewidth]{pic.png}
  % I can assign a label I can refer to later
  \caption{Pretty Picture}\label{fig:prettypic}
\end{wrapfigure}

\blindtext

\endgroup

% ----- Spacing -----
\section*{Spacing}
% \LaTeX\  is a built in command
% \\ creates a line break
% \nolinebreak prevents line breaks \nolinebreak[1] - [4] requests stronger
This is our first \LaTeX\ document. It is quite amazing. The 1st line isn't indented.\\

% Add a 10 pts of space between this line and the next
The second line is indented. If      we     use    multiple spaces     it    won't    matter\\[10pt]

% Cancel the indent
% Eliminate paragraph indents with \usepackage{parskip}
\noindent Special characters can be escaped \% \$ \& \_ \textbackslash

% Increase the line spacing : singlespacing, onehalfspacing,
% doublespacing
% \usepackage[onehalfspacing]{setspace}

% --- Bulleted Lists ---

% Create a bulleted list
% You can add an abbreviated name for the table of contents between []
\section[Smoothie]{Smoothie Recipe}
\begin{itemize}
	\item 1 Cup Spinach
	\item 1 Cup Frozen Blueberries
	\item 2 Bananas
	\item 1.5 Cups Almond Milk
	\item Powders
	% Create a list in a list
	\begin{itemize}
		\item 1 Tbs PB2
		\item 1 Tsp Ambla Powder
	\end{itemize}
	\item 6 Dates
\end{itemize}

% Create a numbered list
% Nesting numbering goes from 1 to a to i. to A.
% \item[customNumbering] allows for any numbering scheme

% You can compact the list by replacing enumerate with compactenum
% and itemize with compactitem and add \usepackage{paralist}

% You can compact lists with this
\setlist{nolistsep}

% --- Numbered Lists ---

\section{Perfect Meal Recipe}

% You can change the numbering \arabic*, \alpha*, \Alph*, \roman*
% You can change the font just for the numbering
\begin{enumerate}[label=\Roman*, font=\bfseries]
	\item Add the following and cook for 2 minutes
	\begin{itemize}
		\item 1 tsp Olive Oil
		\item 1 Cup Onion, diced
		\item 3 cloves Garlic, minced
		\item 1 tsp Salt
		\item 1 Cup chopped Portobello Mushrooms
	\end{itemize}
	\item Add the following and stir for 2 minutes
	\begin{itemize}
		\item 2 TBs Curry Powder
		\item 1 tsp Fresh Minced Ginger
		\item 2 TBs Tomato Paste
	\end{itemize}
	\item Add the following and simmer for 15 minutes
	\begin{itemize}
		\item 1 cup uncooked Lentils
		\item 4 cups Vegetable Broth
	\end{itemize}
	\item Add the following and simmer for 20 minutes
	\begin{itemize}
		\item 2 cups chopped Carrots
		\item 4 Cups cubed Yams
	\end{itemize}
	\item Add the following and cook for 10 minutes
	\begin{itemize}
		\item 2 cups boiled diced Collard Greens
		\item 1 cup frozen diced Spinach
	\end{itemize}
\end{enumerate}

% Another way to add space between paragraphs
\bigskip

% --- Definition Lists ---

\begin{description}
	\item[Philtrum] The vertical groove on the median line of the upper lip
	\item[Darkle] Becoming cloudy or dark
	\item[Pogonotrophy] Growing and grooming a beard or other facial hair
	\item[Interrobang] A punctuation mark designed for use especially at the end of an exclamatory rhetorical question; usually written as ?!
\end{description}

% --- Tabbing ---

\begin{tabbing}

% On setup row define where tabs occur and the space to set aside
Customer  \= Name \hspace*{1.5cm} \= Street \hspace*{1.5cm} \= City \\

% \> Jumps to the next tab
\> Derek Banas \> 123 Main St \> Pittsburgh \\
\end{tabbing}

% --- Tables, Type Emphasis & Fonts ---

% Wrap a table around tabular to make captions
\begin{table}
% Define a table with 3 left aligned columns (Use c (Center) or r (Right)
% The center | creates a vertical line
\begin{tabular}{l|l|l}

% Draw horizontal line
% \usepackage{booktabs} provides different line thicknesses
% \toprule, \midrule, \bottomrule
\hline

% & Defines the breaks in the table
\textbf{Name} & \textbf{Command} & \textbf{Sample Text} \\
\hline
% \verb| | allows you to type commands
emphasize & \verb|\emph| & \emph{abcdefgh} \\
italic & \verb|\textit| & \textit{abcdefgh} \\
slanted & \verb|\textbf| & \textbf{abcdefgh} \\
bold & \verb|\emph| & \emph{abcdefgh} \\
small capped & \verb|\textsc| & \textsc{abcdefgh} \\
medium & \verb|\textmd| & \textmd{abcdefgh} \\
upright & \verb|\textup| & \textup{abcdefgh} \\
roman family & \verb|\textrm| & \textrm{abcdefgh} \\
sans serif & \verb|\textsf| & \textsf{abcdefgh} \\
typewriter & \verb|\texttt| & \texttt{abcdefgh} \\
combo & \verb|\textup{\textbf{}}| & \textit{\textbf{abcdefgh}} \\
\end{tabular}
\caption{Ways to emphasize text}
\end{table}

% Leave some columns blank & merge others
% Create 3 columns
\begin{tabular}{@{}*3l@{}}

% Take up to columns with Name and 1 with age
\multicolumn{2}{c}{Name} &
\multicolumn{1}{c}{Age}\\

% Add headers with the last left blank
First & Last & \\
\hline
Derek & Banas & 44\\
Sally & Smith & 42\\
\end{tabular}//

% ----- Accent Characters -----
% These is a package that allows you to enter accented characters
% \usepackage[utf8]{inputenc} on Linux/MacOS and 
% \usepackage[latin1]{inputenc} on Windows
\'{a} \^{e} `{o} \"{u} \.{a} \={o} \~{n} \u{a} \H{a} \v{e} \t{oo} \c{c} \d{n} \b{i}

% There are numerous fonts here
% http://www.tug.dk/FontCatalogue/

% --- More Type Emphasis --- 

% Abbreviate listing in table of contents to just Type and make sans serif font
% I use label here so I can refer to this section later
\section[Type]{\textsf{Type Emphasis \& Sizing}} \label{sec:typeemp}

If you want font changes to continue \itshape italic, \slshape slanted, \scshape small caps, \upshape upright, \normalfont back to normal\\

% As you change text size that size remains after the command
Get Smaller : \normalsize{normal}, \small{small}, \footnotesize{footnote}, \scriptsize{script}, \tiny{tiny}

Get Bigger : \large{large}, \Large{larger}, \LARGE{larger}, \huge{huge}, \Huge{Hugest}

% Apply sizing change over a block of text
\begin{LARGE}
I want to use a big font
\end{LARGE}

\normalsize{Back to normal}

\section{\textsf{Font Families}}
We can {\sffamily temporarily change} a font family, \ttfamily or change it for the rest of the document \sffamily

% Create quotes
\begin{quote}
``I like long walks, especially when they are taken by people who annoy me.'' 
- Fred Allen
\end{quote} 

% --- Math Formulas ---
% Using this package : \usepackage{amsmath}
\section{Math Formulas}
% LaTeX excels at typesetting math formulas

% Quadratic Equation
% flalign* with formula surrounded with &s makes it left justified
\begin{flalign*}
	& ax^2 + bx + c = 0 &\\
\end{flalign*}

% Place a formula in text
This \( ax^2 + bx + c = 0 \) is the quadratic equation \\

% I prefer the $ TeX shortcut
% Quadratic Formula
$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$ \\

% List of LaTeX Symbols http://www.rpi.edu/dept/arc/training/latex/LaTeX_symbols.pdf

Greek letters $\alpha \beta \gamma \delta \epsilon \zeta \eta \theta 
\vartheta  \iota \kappa \lambda \Lambda \mu \nu \xi \Xi \pi \Pi
\rho \varrho \sigma \Sigma \tau \upsilon \Upsilon \phi \varphi \Phi
\chi \psi \Psi \Omega \omega $ \\ 

Script letters $\mathcal{A}, \mathcal{B}$

Subscript $t_0$ \\ 

Superscript $x^2$ \\ 

Vectors $\vec{a}\cdot\hat{x}=a_x$

Matrices
$\begin{pmatrix} 
1 & 2 \\ 
3 & 4 
\end{pmatrix}$

Integrals $\Delta x=\int_{t_0}^{t_1} v(t)dt$ \\

Limits $\lim_{x\to0} \frac 1 x = \infty$ \\ 

Summations $e^x=\sum_{n=0}^\infty\frac{x^n}{n!}$ \\

Operators $\arccos, \arcsin, \arctan, \arg, \cos, \cosh, \cot, \coth, \deg, 
\det, \dim, \exp, \gcd,\\ \hom, \inf, \ker, \lim, \lg, \liminf, \limsup, \ln, \log, 
\max, \min, \Pr, \sec, \sin, \sinh, \sup, \tan, \tanh$ \\

Arrows $\leftarrow, \Leftarrow, \rightarrow, \Rightarrow, \leftrightarrow, \rightleftharpoons,
 \uparrow, \downarrow, \Uparrow, \Downarrow, \Leftrightarrow, \Updownarrow, \mapsto, \longmapsto, 
 \nearrow, \searrow, \swarrow, \nwarrow, \leftharpoonup, \rightharpoonup, \leftharpoondown, \rightharpoondown$ \\
 
 Relational Operators $ \geq, \gg, \leq, \ll, \neq $ \\

Binary Operation/Relation Symbols $ \approx, \asymp, \bowtie, \cong, \dashv, \doteq, 
\equiv, \frown, \mid, \models, \parallel, \perp, \prec, \preceq, \propto, \sim, \simeq, \smile, 
\succ, \succeq, \vdash $ \\

% ----- Custom Commands -----

\section{\textsf{Custom Commands}}

You can use custom commands : \NTT\ or \NTTB\

Style to \typew{typewriter}.

% ----- Text Boxes & Justification -----
\section{\textsf{Text Columns}}

% You can center text
{\centering
Get in the middle of me\\
Okay\\[10pt]
}

% Create a fully justified column 4cm wide
% \parbox{4cm}{I used to think I was indecisive, but now I'm not too sure.}
% [t]{2cm} aligns to top, [b] aligns to bottom, [s] stretches vertically, [c] centers
% \quad adds horizontal spacing between the boxes
\quad\parbox{2cm}{I used to think I was indecisive, but now I'm not too sure.}
% You can define hyphenation with\-
\quad\parbox{2cm}{Always re\-mem\-ber that you're unique. Just like everyone.}
% raggedright eliminates justification and hyphenation (Justifies Left)
% You can do this document wide if typed in the preamble
\quad\parbox{2cm}{\raggedright I always wanted to be somebody, but I should have been more specific.}
% raggedleft eliminates justification and hyphenation (Justifies Right)
\quad\parbox{2cm}{\raggedleft When I was a kid my parents moved a lot, but I always found them. }

% Minipages are blocks of text that will maintain size restrictions
\begin{minipage}{5cm}

One advantage of talking to yourself is that you know at least somebody's listening.

\end{minipage}

% --- Referencing Content ---

\section{Referencing}

% You can add footnotes and override the numbering 
% Add a 5 pts of space between this line and the next
The answer you're looking for is inside of you, but it's wrong.\footnote[2]{author unknown} \\[2pt]

% You can get the section with \ref and the page with \pageref
There is a great table on Type Emphasis is in this section~\ref{sec:typeemp} on page~\pageref{sec:typeemp}\\[2pt]
There is a pretty picture in section~\ref{fig:prettypic} on page~\pageref{fig:prettypic}\\[2pt]

% Listing references in a bibliography
How I learned my ABCs \cite{ABCAFR}. 

\begin{thebibliography} {books}
\bibitem{ABCAFR} Walter Abish \emph{The Alphabetical Africa}, 1974
\end{thebibliography}

% Create some index references
When I was born I was so ugly the doctor slapped my mother - {\index{Rodney}Rodney Dangerfield} \\[2pt]
\blindtext
\subsection{A Subsection}

% You can refer to other parts of your document
\blindtext

% Create the index (Typeset -> Make index}
\clearpage

% Add the index to the table of contents and print index
\addcontentsline{toc}{chapter}{Index}
\printindex

\end{document}

\documentclass[a4paper,12pt, landscape, twocolumn]{book}
\usepackage{blindtext}
\usepackage[a4paper, inner=1.7cm, outer=2.7cm, top=2cm, 
bottom=2cm, bindingoffset=1.2cm]{geometry}
\begin{document}
\title{\Large{\textbf{LaTeX Tutorial}}}
\author{By Derek Banas}
\date{December 21, 2018}
\maketitle
\blindtext[5]
\end{document}
```

Source: [NewThinkTank](https://www.newthinktank.com/2019/01/latex-tutorial/)
