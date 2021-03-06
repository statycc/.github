---
title: StATyCC
subtitle: "Static Analyses of Program Flows: Types and Certificates for Complexity"
lang: en
keywords:
    - Computer Science
    - Compiler Optimization
    - Undergraduate Research
    - Augusta University
    - University Paris 13
documentclass: scrartcl
papersize: letter
geometry: margin=1in
bibliography: bib.bib
link-citations: true
csl: theoretical-computer-science.csl
header-includes:
 - \newcommand{\website}{\href{https://spots.augusta.edu/caubert/research/statyc/}{spots.augusta.edu/caubert/research/statyc/}}
 - \usepackage{titling}
 - \makeatletter\def\@maketitle{\centering{\usekomafont{title}{\huge \@title\par}\vskip .3em \usekomafont{subtitle}{\@subtitle\par}\vskip .3em}}\makeatother
 - \addtokomafont{section}{\centering}
 - \usepackage{xcolor}
 - \definecolor{links}{HTML}{2e4683}
 - \hypersetup{colorlinks=true, allcolors=links}
 - \linespread{1.1}
 - \usepackage{lastpage}
 - \usepackage{fancyhdr}
 - \pagestyle{fancy}
 - \fancypagestyle{plain}{
        \lfoot{\website}
        \cfoot{}
        \rfoot{Page\ \thepage\ of\ \protect\pageref{LastPage}}
        \lhead{}
        \rhead{}
        \renewcommand{\headrulewidth}{0pt}
    }
 - \lhead{\textbf{Presentation}}
 - \rhead{\thetitle}
 - \lfoot{\website}
 - \cfoot{}
 - \rfoot{Page\ \thepage\ of\ \protect\pageref{LastPage}}
 - \renewcommand{\footrulewidth}{0.4pt}
 - \renewcommand{\headrulewidth}{0.4pt}
 - \renewcommand{\linethickness}{0.4pt}
---

# Presentation

StATyCC stands for "Static Analyses of Program Flows: Types and Certificates for Complexity".
This is a two-year international collaborative project funded by the [Thomas Jefferson Fund](https://face-foundation.org/higher-education/thomas-jefferson-fund/previous-projects/) and involving the [School of Computer Science](https://www.augusta.edu/ccs/) of the University of Augusta and the [Northern Paris Computer Science Lab](https://lipn.univ-paris13.fr/en/home/) of the University of Paris 13.

The project aims at providing new static analysis tools based on theoretical results from Implicit computational complexity, building on previous work of Moyen, Rubiano and Seiller [@Moyen2017].
It revolves around certified compositional analysis of source code, loop optimization through an original dependency model.
Application to parallel optimization and intermediate representation are currently being investigated.


# Members

This project is carried out by

- American Partner
    - [Cl??ment Aubert](https://spots.augusta.edu/caubert/)
    - [Neea Rusch](https://nkrusch.github.io/)
    - Assya Sellak (until 03/21)

- French Partner
    - [Thomas Seiller](https://www.seiller.org/)
    - [Thomas Rubiano](https://people.irisa.fr/Thomas.Rubiano/)

![Gathering at [Schloss Dagstuhl](https://www.dagstuhl.de/en/program/calendar/evhp/?semnr=21453), Nov. 2021. ?? Schloss Dagstuhl - LZI GmbH ](pictures/dagstuhl_2021/reduced_01.jpg)
    
# Papers

We currently have two papers accepted, and one article under revision.

## Accepted

- Cl??ment Aubert, Thomas Rubiano, Neea Rusch, Thomas Seiller. mwp-Analysis Improvement and Implementation: Realizing Implicit Computational Complexity. [FSCD 2022](https://www.cs.tau.ac.il/~nachumd/FSCD/) 2022, [10.4230/LIPIcs.FSCD.2022.26](https://doi.org/10.4230/LIPIcs.FSCD.2022.26)
- Cl??ment Aubert, Thomas Rubiano, Neea Rusch, Thomas Seiller. Realizing Implicit Computational Complexity. 2022. [???hal-03603510v1???](https://hal.archives-ouvertes.fr/hal-03603510v1), accepted to [Types 2022](https://types22.inria.fr/).

## Under Revision

- Cl??ment Aubert, Thomas Rubiano, Neea Rusch, Thomas Seiller.  A Novel Loop Fission Technique Inspired by Implicit Computational Complexity. 2022. [???hal-03669387???](https://hal.archives-ouvertes.fr/hal-03669387)


<!--
- Cl??ment Aubert, Thomas Rubiano, Neea Rusch, Thomas Seiller. An extended and more practical mwp flow analysis. 2021. [???hal-03269096v2???](https://hal.archives-ouvertes.fr/hal-03269096)
- Cl??ment Aubert, Thomas Rubiano, Neea Rusch, Thomas Seiller. An implementation of flow calculus for complexity analysis (tool paper). 2021. [???hal-03269121v2???](https://hal.archives-ouvertes.fr/hal-03269121)
-->

# Tools

- A refined implementation of the original optimization [@Moyen2017] is available [on github](https://github.com/statycc/LQICM_On_C_Toy_Parser).
- An experimental implementation of the mwp-analysis for C code is available [on github](https://github.com/statycc/pymwp).

# Presentations / Events

## Types 2022 {#types2022}

We had [an abstract](https://hal.archives-ouvertes.fr/hal-03603510) accepted the [28th International Conference on Types for Proofs and Programs](https://types22.inria.fr).

<details>
<summary>Details</summary>

### Abstract

> **Realizing Implicit Computational Complexity**
>
> This abstract aims at presenting an ongoing effort to apply a novel typing mechanism stemming from Implicit Computational Complexity (ICC), that tracks dependencies between variables in three different ways, at different stages of maturation. The first and third projects bend the original typing discipline to gain finer-grained view on statements independence, to optimize loops by hoisting invariant and by splitting loops "horizontally" to parallelize them more efficiently. The second project refines and implements the original analysis to obtain a fast, modular static analyzer. All three projects aims at pushing the original type system, inspired from ICC, to its limits, to assess how ICC can in practice leads to original, sometimes orthogonal, approaches. 

Neea's slides are available [on-line](slides/TYPES_2022.pdf).

</details>

## Graduate Research Day 2022 {#grd2022}

Neea Rusch had her abstract accepted to Augusta University's [Graduate Research Day](https://www.augusta.edu/gradschool/grd.php).

<details>
<summary>Details</summary>

### Abstract

> **Semantic-preserving optimization algorithm for automatic program parallelization**
>
> Advanced and resource-intensive computation relies on continuous rise in processing power. Since the 1970s, Moore's law accurately predicted this growth would be achieved through hardware improvements, but this observation is becoming progressively obsolete. Alternative approaches are needed to maintain increase in efficiency. Parallelization is a technique in which larger computational problem is divided into smaller tasks, which are then executed simultaneously, reducing overall time to completion. Specialized software and algorithms are required to enable parallelization.
>
> This research presents a novel algorithm for automatic program parallelization based on loop splitting. In programming, loop statements are used for carrying out repeated computation, but when used extensively or carelessly, will produce performance inefficiencies. Using a graph-based variable dependency analysis, the algorithm detects opportunities for splitting loops into smaller, parallelizable loops; then automatically applies this optimization. Additionally, the algorithm guarantees the preservation of program semantics post-transformation. We hypothesize this algorithm, when combined with OpenMP--an existing state-of-the-art multiprocessing tool--will provide noticeable performance gains for resource-intensive computational tasks. An open-source tool, pyalp, implementing this algorithm on C programs, is currently being developed to demonstrate and measure its efficiency in practice.


Neea's poster is available [on-line](poster/2022_GRD_Neea.pdf).

![Pavan Poudel, Neea, Cl??ment, Ahmed Aleroud and Nour Alhussien at Graduate Research Day](pictures/graduate_research_day_2022/grd_2022.jpg)

</details>

## Dagstuhl's Seminar

We organized a seminar at [Dagstuhl](https://www.dagstuhl.de/) November 7 ??? 12 , 2021, called ["Static Analyses of Program Flows: Types and Certificates for Complexity"](https://www.dagstuhl.de/en/program/calendar/evhp/?semnr=21453).

## Graduate Research Day 2021 {#grd2021}

Both Assya Sellak and Neea Rusch had their abstract accepted to Augusta University's [Graduate Research Day](https://www.augusta.edu/gradschool/grd.php).

<details>
<summary>Details</summary>

### Abstract

> **Certifying the complexity and correctness of critical software**  
> Software powers our everyday lives: from phones to daily interactions to our homes. At the same time software is fraught with bugs causing systems to behave in undesirable ways. When discussing critical software responsible for sustaining human life???such as airplanes, ventilators, and nuclear reactors???being able to guarantee correct behavior is necessary. Compilers play a vital role in the software development process by transforming programmer's source code to executable programs. They perform analysis, transformations, and optimizations to improve the performance and reliability of the resulting program. But compilers???since they are themselves pieces of software???may contain bugs. To build reliable software, we must establish the correct behavior of these intermediate tools.
There is a colossal push to prove the correctness of such tools using mathematical abstractions such as dependency analysis, formal methods, and proof assistants. Proving the correctness allows eradicating bugs in programs and drives programmers to specify formally the intended behavior of programs while building trust and confidence in the end-result. Using dependency analysis inspired by Implicit Computational Complexity, we apply those techniques to program transformations. Among these techniques is ensuring program's variables grow within reasonable bounds thus providing a certification in term of memory footprint and possibly run-time, in addition to certifying its behavior. Implementing this analysis is one of the goals of our research.

Neea's presentation is available [on-line](https://www.youtube.com/watch?v=J8QtGZgTOQM).
</details>

## 2020 Georgia Undergraduate Research Conference {#gurc2020}

Assya Sellak made a presentation to the [2020 Georgia Undergraduate Research Conference](https://www.westga.edu/academics/research/our/GURC_Program.php).

A similar presentation was accepted to the [2021 National Conference on Undergraduate Research](https://apps.cur.org/ncur2021/search/display_ncur.aspx?id=110859).

<details>
<summary>Details</summary>

### Abstract

> **Optimization Method on Programs Using Dependency Analysis and Loop Peeling Transformations**  
> Computer programs are written in high-level languages and translated
into machine-code using compilers. Compilers perform a series of program
transformation and optimizations to improve memory usage and reduce the
run time of the program execution. Programs consist of commands and
statements such as conditionals and loops. Loops are an extremely
powerful tool for programmers used to repeatedly run a sequence of
commands until a specified condition is met. However, when used
carelessly, loops can lead to never-halting or extremely slow programs:
for this reason, many compilers and program optimizations focus on these
structures. Loops can contain commands that perform unneeded residual
operations instead of only being executed when necessary. This excessive
performance results in an avoidable increase in run time which may arise
intentionally or unintentionally either because of the programmer or
other automatic transformations. Detecting which operations could have
been performed fewer times than the loop requires is complex, but some
optimizations try to detect this and extract portions of code that only
needed to run once and successively move commands that need to run more
than once, but not as many times as the loop runs. These fall short on
some structures, mainly because they limit the scope of the analysis to
individual operations, rather than considering sequences of operations
as a whole. Thanks to quasi-interpretation [@Moyen2017] coming from Implicit Computational
Complexity, new ways of detecting invariant sequences of commands inside
loops have been developed. We extend this work along two axes: We allow
for more structures, including `for`{.md}, `do...while`{.md}, loops with
`break`{.md}, to be peeled. By analyzing the dependencies within the
loop, we hope to allow for some parallel optimization. This allows to:
> 
> - consider more programs
> - possibly significantly speed-up programs that are distributed, i.e.,
    executed in parallel on multiple computers.

The [slides](gurc/Presentation.pdf) as well as the [abstract](gurc/Abstract.pdf) are available to download.
[The program of the conference](gurc/GURC2020Program.pdf) is available as well.
</details>


# References

::: {#refs}
:::


# Miscellaneous{.unlisted}

 * Download [a `pdf` version](index.pdf) of this page. 
 * Contact: [caubert@augusta.edu](mailto:caubert@augusta.edu)
 * Created with [debian](https://www.debian.org/), [pandoc](https://pandoc.org/) and [latex](https://www.latex-project.org/).
<!--,
 [HTML5](https://validator.w3.org/check/referer) and [CSS3](https://jigsaw.w3.org/css-validator/check/referer) valid,
https://stackoverflow.com/q/46982187/2657549
https://webmasters.stackexchange.com/q/109954/54133
-->
 * All my documents are under [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). Sources are available upon motivated request.
 * You will need a `pdf` reader to consult some of the documents: I recommend choosing [an open-source `pdf` reader](https://pdfreaders.org/).
