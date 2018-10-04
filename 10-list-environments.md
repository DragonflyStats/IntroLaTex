List structures
=============================

Lists often appear in documents, especially academic, as their purpose is often to present information in a clear and concise fashion. List structures in LaTeX are simply environments which essentially come in three types:

1. itemize for a bullet list
2. enumerate for an enumerated list and
3. description for a descriptive list.

All lists follow the basic format:
<pre><code>
\begin{list_type}  
\item The first item 
\item The second item 
\item The third etc \ldots 
\end{list_type}
</code></pre>

All three of these types of lists can have multiple paragraphs per item: just type the additional paragraphs in the normal way, with a blank line between each. So long as they are still contained within the enclosing environment, they will automatically be indented to follow underneath their item.


Try out the examples below, to see what the lists look like in a real document.
<pre><code>
\documentclass{article}
\usepackage{blindtext}
\begin{document}
\begin{itemize}
\item \blindtext
\item \blindtext
\end{itemize}
\begin{enumerate}
\item \blindtext
\item \blindtext
\end{enumerate}
\begin{description}
\item [Ant] \blindtext
\item [Elephant] \blindtext
\end{description}
\end{document}
</code></pre>
Sample output of lists in LaTeX. Itemize, enumerate, and description.

LaTeX will happily allow you to insert a list environment into an existing one (up to a depth of four, more levels are available using packages). Simply begin the appropriate environment at the desired point within the current list. Latex will sort out the layout and any numbering for you.
<pre><code>
\begin{enumerate}
\item The first item
\begin{enumerate}
\item Nested item 1
\item Nested item 2
\end{enumerate}
\item The second item
\item The third etc \ldots
\end{enumerate}
</code></pre>

### Some special lists
Sometimes you feel the need to better align the different list items. If you are using a KOMA-script class (or package scrextend), the labeling environment is handy. It takes a mandatory argument that contains the longest of your labels.
<pre><code>
\documentclass[twocolumn]{article}
\usepackage{blindtext}
\usepackage{scrextend}
\addtokomafont{labelinglabel}{\sffamily}
\begin{document}
\blindtext
\begin{labeling}{alligator}
\item [ant] really busy all the time
\item [chimp] likes bananas
\item [alligator] very dangerous animal, sharp teeth, long
muscular tail and a bit of text that is longer than one
line and shows the alignment of text quite nicely
\end{labeling}
\end{document}
</code></pre>

If you are on tight space limitations and only have short item descriptions, you may want to have the list inline. Please note that the example also shows how to change the font.
<pre><code>
\documentclass[twocolumn]{article}
\usepackage{blindtext}
\usepackage[inline]{enumitem}
\usepackage{xcolor}
\begin{document}
\blindtext Coco likes fruit. Her favorites are:
\begin{enumerate*}[label={\alph*)},font={\color{red!50!black}\bfseries}]
\item bananas
\item apples
\item oranges and
\item lemons.
\end{enumerate*}
\blindtext
\end{document}
</code></pre>



If you want a horizontal list, package tasks can be handy. In combination with a package like exsheets, you can prepare exam papers for students.
<pre><code>
\documentclass[12pt]{article}
\usepackage{tasks}
\usepackage{exsheets}
\SetupExSheets[question]{type=exam}
\begin{document}
\begin{question}
	Which one of the entries does not fit with the others?
	\begin{tasks}(4)
		\task mercury
		\task iron
		\task lead
		\task zinc
	\end{tasks}
\end{question}
\settasks{
	counter-format=(tsk[r]),
	label-width=4ex
}
\begin{question}
	What is a funkyton?
	\begin{tasks}(2)
		\task A dancing electron
		\task A dancing proton
		\task A dancing neutron
		\task A Dixie Dancing Duck
	\end{tasks}
\end{question}
\end{document}
</code></pre>
### Customizing lists
Especially when dealing with lists containing of just a few words per item, the standard lists take up too much space and you want to customize the appearance. Package enumitem helps you by providing a simple interface.

You can change the appearance of lists globally in the preamble, or just for single lists using the optional argument of the environment. Have a look at the following example where the list on the right is more compact using noitemsep.
<pre><code>
\documentclass[twocolumn]{article}
\usepackage{blindtext}
\usepackage{enumitem}
\begin{document}
\blindtext
\begin{itemize}
\item more work
\item more responsibility
\item more satisfaction
\end{itemize}
\blindtext
\newpage
\blindtext
\begin{itemize}[noitemsep]
\item more work
\item more responsibility
\item more satisfaction
\end{itemize}
\blindtext
\end{document}
</code></pre>
An example for alignment and the width of the label.
<pre><code>
\documentclass[twocolumn]{article}
\usepackage{blindtext}
\usepackage{enumitem}
\begin{document}
\blindtext Coco likes fruit. Her favourites are:
\begin{description}[align=left]
\item [Kate] some detail
\item [Christina]some detail
\item [Laura]some detail
\end{description}
\begin{description}[align=right]
\item [Kate] some detail
\item [Christina]some detail
\item [Laura]some detail
\end{description}
\begin{description}[align=right,labelwidth=3cm]
\item [Kate] some detail
\item [Christina]some detail
\item [Laura]some detail
\end{description}
\blindtext
\end{document}
</code></pre>
The documentation of package enumitem goes into more detail with respect to what can be changed and how. You can even define your own lists. 

Environments like labeling and tasks can be changed differently, details can be found in the package documentation respectively.

### Easylist package
The easylist package allows you to create list using a more convenient syntax and with infinite nested levels. It is also very customizable.

Load the package with the control character as optional argument:

\usepackage[ampersand]{easylist}
The easylist environment will default to enumerations.

<pre><code>
\begin{easylist}
& Main item~:
&& Sub item.
&& Another sub item.
\end{easylist}
</ocde></pre>
It features predefined styles which you can set as optional argument.

\begin{easylist}[itemize]
% ...
\end{easylist}
