# UHK thesis Latex template

This is an unofficial Latex version of [UHK](https://www.uhk.cz/) thesis template written in docx. This template is based on 
[xdobro4/uhk-thesis-latex-template](https://github.com/xdobro4/uhk-thesis-latex-template)
which already provided great start for thesis (thanks!). Unfortunately, some aspects of the template had to be reworked or modified to match it 
with the official MS Word template styling and all content requirements. It is mainly focused on theses written in czech
language but there is already some support for other languages, but supporting other languages is
currently not a goal of this template. 

An example of thesis built with this template can be found [here](https://github.com/lukashornych/uhk-bachelor-thesis/blob/master/thesis.pdf).

## How to start writing

1. install Latex (e.g. [TeX Live](https://www.tug.org/texlive/))
2. install Latex editor (e.g. [IntelliJ IDEA](https://www.jetbrains.com/idea/) with [TeXiFy IDEA](https://plugins.jetbrains.com/plugin/9473-texify-idea) plugin)
3. open this template with the editor
4. try to build it with pdfLaTeX
    - in case of IntelliJ IDEA, there is run icon next to `\begin{document}` in [main.tex](main.tex)
    - if there is some problem, you have probably installed or configured the TeX or pfdLaTeX incorrectly (e.g. check paths to pdfLaTeX and bibTeX) 
5. if success resolve all of the `TODO WRITER:` todos and write your thesis 🙂

## Explanation of files

- [fim-uhk-thesis.cls](fim-uhk-thesis.cls) - commands
- [bibstyle.bst](bibstyle.bst) - bibliography style and available properties for source literature
- [main.tex](main.tex) - main document combining all parts together to ultimately build final thesis
- [content.tex](content.tex) - contains main text of your thesis
- [acronyms.tex](acronyms.tex) - contains definitions of acronyms used in the main content
- [literature.bib](literature.bib) - contains definitions of literature sources for your main content

## Examples

Sections:
```
\section{Introduction}
Some text...
```
```
\subsection{Something important}
Some text...
```
```
\subsubsection{Detail}
Some text...
```
```
\nlparagraph{More detail}
\noindent Some text...
```

List of items:
```
\begin{itemize}
   \item fotografie/avatar,
   \item kategorizační štítky,
   \item popisek.
\end{itemize}
```

Image with caption and source:
```
\cntcapfigure{picture_file}{10cm}{Some caption.}{\cite{source}}
```

Code block with caption and source:
```
\begin{codeblock}
   \begin{verbatim}
@Mapper
public interface AccountDao {
  @Select({
    "select *",
    "from " + Account.TABLE_NAME,
    "where email = #{email}"
  })
  Optional<Account> findByEmail(String email);
}
   \end{verbatim}
   \captionsource{Some caption.}{[author]}
\end{codeblock}
```

Table (not tested):
```
\begin{table}[hbt!]
    \captionsource{Ukázková tabulka.}{[autor]}
    \centering
    \begin{tabular}{| l | r | r | r | }
        \hline
        &        psnr &      ssim &      doba  \\
        model &       (db)    &           & gen. (s) \\
        \hline
        bik. int. & 28.3155 & 0.8566 & 0.0322 \\
        nn1000    & 30.1461 & 0.9043 & 0.8109 \\
        nn1001    & 30.0324 & 0.9023 & 0.7486 \\
        nn1002    & \textbf{30.1886} & \textbf{0.9046} & 1.1731 \\
        nn1003    & 30.0390 & 0.9030 & 1.1320 \\
        nn1004    & 24.9772 & 0.7172 & 4.4367 \\
        nn1005    & 26.1629 & 0.8004 & 4.0475 \\
        nn1006    & 27.9129 & 0.8438 & 4.0683 \\
        nn1007    & 27.5834 & 0.8360 & 4.2082 \\
        \hline
    \end{tabular}
\end{table}
```

Separation of new text to new page:
```
\newpage
```

Acronym declaration:
```
\DeclareAcronym{URL}{
  short=URL,
  long=Uniform Resource Locator
}
```

Web article source:
```
@webarticle{hibernate_docs,
	author = {Vlad Mihalcea and Steve Ebersole and Andrea Boriero and Gunnar Morling and Gail Badner and Chris Cranford and Emmanuel Bernard and Sanne Grinovero and Brett Meyer and Hardy Ferentschik and Gavin King and Christian Bauer and Max Rydahl Andersen and Karel Maesen and Radim Vansa and Louis Jacomet},
	title = {Hibernate ORM 6.0.0.Final User Guide},
	url = {https://docs.jboss.org/hibernate/orm/6.0/userguide/html_single/Hibernate_User_Guide.html},
	urlvisited = {2022-04-15},
	journal = {Hibernate},
}
```

Book source:
```
@book{ddd_quickly,
	author = {Abel Avran and Floyd Marinescu},
	title = {Domain-Driven Design Quickly},
	year = {2006}
}
```

## Contributions

PRs with fixes or new features are welcome, but remember, the goal is to make it easy to write theses in Latex without any difficult installation and configuration.
