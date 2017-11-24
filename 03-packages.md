> LaTeX-Tutorial.com

Search

News
Installation
Editors
Quick Start
Tutorials 
Tools 
Symbols 
About 
Downloads
Home»Tutorials»03 Packages
Using LaTeX packages
Use packages in LaTeX to add more functions. Demonstration of amsmath package and basic math typesetting.



 
[Open document online]

Install a package
Purpose of packages
Using / Including a package
LaTeX offers a lot of functions by default, but in some situations it can become in handy to use so called packages. To import a package in LaTeX, you simply add the \usepackage directive to the preamble of your document:

\documentclass{article}

\usepackage{PACKAGENAME}

\begin{document}
...
Install a package

When using Linux or Mac, most packages will already be installed by default and it is usually not necessary to install them. In case of Ubuntu installing texlive-full from the package manager would provide all packages available. The MiKTeX bundle in Windows, will download the package if you include it to your document.

Purpose of packages

There are countless packages, all for different purposes in my tutorials I will explain some of the most useful. To typeset math, LaTeX offers (among others) an environment called equation. Everything inside this environment will be printed in math mode, a special typesetting environment for math. LaTeX also takes care of equation numbers for us:

\documentclass{article}

\begin{document}

\begin{equation}
  f(x) = x^2
\end{equation}

\end{document}
This will result in the following output: 
f
(
x
)
=
x
2
f(x)=x2 (1)

Using / Including a package

The automatic numbering is a useful feature, but sometimes it's necessary to remove them for auxiliary calculations. LaTeX doesn't allow this by default, now we want to include a package that does:

\documentclass{article}

\usepackage{amsmath}

\begin{document}

\begin{equation*}
  f(x) = x^2
\end{equation*}
Now we get the same output as before, only the equation number is removed: 
f
(
x
)
=
x
2
f(x)=x2
Summary

Packages add new functions to LaTeX
All packages must be included in the preamble
Packages add features such as support for pictures, links and bibliography
Next Lesson: Lesson 4


 
Top ↑ Oct. 7, 2017
design and content © 2017 Claudio Vellage
This website makes use of cookies to enhance browsing experience and provide additional functionality. Details Allow cookies
