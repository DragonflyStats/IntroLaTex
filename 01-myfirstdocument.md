Your first LaTeX document
=============================================================
Demonstration of how to create a basic LaTeX document and title page using LaTeX. The basic file layout explained.



 
Basic layout
Title pages
This tutorial assumes that you have chosen and installed an editor. 
If not you can use the great online editor of my partner overleaf.com:

[Open document online]

You will find a link like this in all of the following lessons.

### The basic layout of a LaTeX file

Creating documents with LaTeX is simple and fun. In contrast to Word, you start off with a plain text file (.tex file) 
which contains LaTeX code and the actual content (i.e. text). LaTeX uses control statements, which define how your 
content should be formatted. Before you can see what the final result looks like, the LaTeX compiler will take your .tex file and compile it into a .pdf file. A basic example document can be created with the following code:
<pre><code>
\documentclass{article}
\begin{document}
  Hello World!
\end{document}
<code></pre>
Once you translated this code into a PDF document, you will find the text:
<pre><code>
Hello World!
Hello World!
</code><pre>
along with the page number at the bottom, which is added automatically when using the article class.

Let us now take a closer look at how the magic happens. As you can see, you will find a few statements 
beginning with a backslash \ in the code example above. This tells LaTeX that this is not actual text, that you want to see printed in your document, but instead is an instruction or command for the LaTeX compiler. All commands share the following structure: \commandname{option}. The first part indicates the name of the command and the second part in braces sets an option for this command. The options vary from command to command and you will learn some of them later on in this tutorial.

Most of the time, the commands are pretty self-explanatory:  ``\documentclass{article}`` and what's even greater, 
you don't have to remember all of them, because you can later just copy and paste them from previous documents. Now let's take a little closer look at the command ``\documentclass{article}`` The command is obviously named documentclass and it does exactly that, it sets the document class (to article).

LaTeX uses document classes, to influence the overall layout of your document. For instance, there's one class to layout articles, one class to layout books (called book) and many more, which we probably don't need. In my tutorials, I will always use the class article. Feel free to play around and try different document classes anyway and see what happens!

This second example differs slightly from the first one, since this command involves a \begin and \end statement. In fact this is not a command, but defines an environment. An environment is simply an area of your document where certain typesetting rules apply. It is possible (and usually necessary) to have multiple environments in a document, but it is imperative the document environment is the topmost environment. The following code shows how environments can be used:
<pre><code>
% Valid:

\begin{document}
  \begin{environment1}
    \begin{environment2}
    \end{environment2}
  \end{environment1}
\end{document}
</code></pre>
<pre><code>
%Invalid:

\begin{document}
  \begin{environment1}
    \begin{environment2}
  \end{environment1}
    \end{environment2}
\end{document}
</code></pre>
% Invalid:

\begin{document}
  \begin{environment1}
\end{document}
  \end{environment1}

% Also invalid:

\begin{environment}
  \begin{document}
  \end{document}
\end{environment}
Adding a title page

There are numerous choices for environments and you will most likely need them as soon as you introduce large parts of mathematics or figures to your document. While it is possible to define your own environments, it is very likely that the environment you desire already exists. LaTeX already comes with a few predefined environments and even more come in so called packages, which are subject to another lesson later on.

Let's try out a few more commands to make our document more interesting:
<pre><code>
\documentclass{article}

\title{My first document}
\date{2013-09-01}
\author{John Doe}

\begin{document}
  \maketitle
  \newpage

  Hello World!
\end{document}
</code></pre>
Obviously the statements \title, \date and \author are not within the the document environment, so they will not directly show up in our document. The area before our main document is called preamble. In this specific example we use it to set up the values for the \maketitle command for later use in our document. This command will automagically create a titlepage for us. The \newpage command speaks for itself.

If we now compile again, we will see a nicely formatted title page, but 
we can spot a page number at the bottom of our title page. What if we decide, that actually, we don't want to 
have that page number showing up there. We can remove it, by telling LaTeX to hide the page number for our first page. 
This can be done by adding the **\pagenumbering{gobble}** command and then changing it back to **\pagenumbering{arabic}** on the next page numbers like so:
<pre><code>
\documentclass{article}

\title{My first document}
\date{2013-09-01}
\author{John Doe}

\begin{document}
  \pagenumbering{gobble}
  \maketitle
  \newpage
  \pagenumbering{arabic}

  Hello World!
\end{document}
</code></pre>
That's it. You've successfully created your first LaTeX document. The following lessons will cover how to structure your document and we will then proceed to make use of many features of LaTeX.

### Summary

A document has a preamble and document part
The document environment must be defined
Commands beginning with a backslash \, environments have a begin and end tag
Useful settings for pagenumbering:
gobble - no numbers
arabic - arabic numbers
roman - roman numbers
