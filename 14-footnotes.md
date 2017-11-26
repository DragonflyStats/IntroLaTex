LaTeX Footnotes - Quick Explanation
==============================
Learn how to create footnotes in LaTeX and how to refer to them, using the builtin commands footnote, label and ref.



 
One of the benifits of using LaTeX is how easy footnotes can be added and referred to. So how to use footnotes? LaTeX offers the \footnote command and referencing works using the \label and \ref commands.

The following code shows some example text and how to add a footnote with a label:

...
This is some example text\footnote{\label{myfootnote}Hello footnote}.
...
After compilation you will see the footnote appearing on the bottom of your page. It's imperative, that the label is contained within the footnote itself, otherwise the label will refer to the section (or subsection). Footnotes are numbered automatically. If you want to refer to them later on, you can use the \ref command as follows:

...
I'm referring to footnote \ref{myfootnote}.
...
### Summary

Create footnotes with the \footnote command and label them with \label
Make sure that the label is contained within the braces of the footnote command
Use the \ref command to refer to footnotes
