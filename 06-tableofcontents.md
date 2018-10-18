Generate a table of contents in LaTeX
=======================================================
LaTeX offers features to automatically generate a table of contents, a list of figures and a list of tables. 

* Table of contents
* List of figures
* Table of contents

Generating a table of contents can be done with a few simple commands. LaTeX will use the section headings to create the table of contents and there are commands to create a list of figures and a list of tables as well. I will give a small example code to create a table of contents first:
<pre><code>
\documentclass{article}

\begin{document}

\tableofcontents
\newpage

\section{Section}

Dummy text

\subsection{Subsection}

Dummy text

\end{document}
</code></pre>
After compiling the .tex file two times, you will get the following table of contents:

toc.png

#### List of figures / tables

The generation of a list of figures and tables works the same way. I added a dummy figure and table and put the lists in the appendix of my document:

<pre><code>
\begin{document}
...
\begin{figure}
  \caption{Dummy figure}
\end{figure}

\begin{table}
  \caption{Dummy table}
\end{table}
...
\begin{appendix}
  \listoffigures
  \listoftables
\end{appendix}

\end{document}
</code></pre>
After compiling two times again, the lists will be generated like this:

toc2.png

### Summary

* Autogenerate a table of content using \tableofcontents
* Create lists of your figures and tables with \listoffigures and \listoftables
* Always compile twice to see the changes
