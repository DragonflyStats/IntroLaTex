Using LaTeX paragraphs and sections
Learn how to structure your document using sections and paragraphs in LaTeX. A brief introduction to headings and the basic file layout.



 
[Open document online]

* Sectioning elements (sections, subsections, paragraphs etc.)
* Example output of sections and subsections
* Hierarchy of sectioning elements
* Sectioning elements (sections, subsections, paragraphs etc.)

We have created a very basic document in the previous lesson, but when writing a paper, it's necessary to structure the content into logic units. To achieve this, LaTeX offers us commands to generate section headings and number them automatically. The commands to create section headings are straightforward:

* \section{}
* \subsection{}
* \subsubsection{}
* \paragraph{}
* \subparagraph{}

Example output of sections and subsections

The section commands are numbered and will appear in the table of contents of your document. Paragraphs aren't numbered and won't show in the table of contents. Here an example output using sections:

Image

In order to get this output, we just have to add a few lines to our program from lesson 1:
<pre><code>
\documentclass{article}

\title{Title of my document}
\date{2013-09-01}
\author{John Doe}

\begin{document}

\maketitle
\pagenumbering{gobble}
\newpage
\pagenumbering{arabic}

\section{Section}

Hello World!

\subsection{Subsection}

Structuring a document is easy!

\end{document}
</code></pre>
### Hierarchy of sectioning elements

The following picture shows the hierarchical structure of all elements:

Image

I have used the following code to get this output:
<pre><code>
\documentclass{article}

\begin{document}

\section{Section}

Hello World!

\subsection{Subsection}

Structuring a document is easy!

\subsubsection{Subsubsection}

More text.

\paragraph{Paragraph}

Some more text.

\subparagraph{Subparagraph}

Even more text.

\section{Another section}

\end{document}
</code></pre>
It's very easy to structure documents into sections using LaTeX. This feature also exists in Word, but most people don't use it properly. In LaTeX it is very effortless to have consistent formatting throughout your paper. In the next lesson I will give a short introduction to packages and show some basic math typesetting. This is where LaTeX really excels.

#### Summary

LaTeX uses the commands ``\section``, ``\subsection`` and ``\subsubsection`` to define sections in your document
The sections will have successive numbers and appear in the table of contents
Paragraphs are not numbered and thus don't appear in the table of contents

