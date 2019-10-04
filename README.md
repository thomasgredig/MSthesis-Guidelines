# MSthesis-Guidelines
 guidelines for writing an M.S. thesis


# M.S. Thesis

You should be familiar with writing and if not refresh your memory with a book, such as "A Manual for Writers of Research Papers, Theses and Dissertations" by Kate L. Turabian. It contains general information. In the following, we will add some specific approaches towards writing a physics M.S. thesis in experimental condensed matter.

# Software Packages

 Familiarize yourself with the following tools

 * [Zotero](https://www.zotero.org/) for references, see [Zotero Documentation](https://www.zotero.org/support/)
 * [R](https://www.r-project.org/) for graphs and tables, see [R scientific reproducibility](https://swcarpentry.github.io/r-novice-gapminder/)
 * [LaTeX](https://www.latex-project.org/) for Thesis, learn how to use on [OverLeaf](https://www.overleaf.com/learn)



# Comprehensive Powerpoint File

Keep a lengthy comprehensive powerpoint file. It should include data more or less in chronological order. It is not important to keep it tidy, but rather it is important to keep it clean and update this file regularly. It should contain 100 - 300 slides. The slides can include photos of samples, reviews and snippets of literature, graphs from results, calculations from the analysis, schematics and plans. Use the *notes* section to add folder, filenames, and other information pertinent to the graph.


# File System

All files are in a shared [Dropbox](https://www.dropbox.com/) folder. The structure includes the following folders:

- **Abstracts**: any abstracts submitted for presentations or poster events,
- **Figs**: self-drawn figures
- **Figs-Generated**: all figures generated by R code
- **Presentations**: all presentations (defense, posters, conferences, etc.)
- **R**: Graph generating files using data from the RAW folder and saving results in Figs-Generated or Results-Generated
- **RAW**: all unaltered data files from machines
- **Results**: Manually recorded results and tables
- **Results-Generated**: results and tables generated from R code
- **Thesis**: LaTeX documents with entire thesis (except for generated figures and tables)

Since the files in Figs-Generated and Results-Generated are computed from R code, all files therein can be deleted. The first part of the generated file contains the file name of the R code. For example, the files MvsH-H1.png, MvsH-H2.png were generated by MvsH.R in the R folder.



## Sample and Data File Conventions

#### Sample Naming Convention

 * two initials of the person who makes the samples (example: TG)
 * date in format yyyy/mm/dd (example: 20190724)
 * if more than one sample is created in any one day by one author, then additional information is appended, which distinguishes the samples, such as Si1, Si2, for two samples made on silicon substrates, or rpm1, rpm2, for two samples created with two different spin speeds.

 Examples for sample names include: **TG20190724** or **TG20190723Si1**; sample names should not be too long. The processing details are separately recorded in the log book.

#### Data File Naming Convention

**RAW data** filenames must be *unique* and cannot be altered. The date should represent the starting date of the data collection. The project name is given to you at the beginning by the mentor.

There are no sub-folders in the RAW folder; i.e. the RAW folder has a flat structure. If the data file is in a compressed or proprietary format (such as XRD), it must also be converted into a text file in ASCII format and both files should be saved.

The format is as follows:

- **Date_Project_Initials_Tool_Sample_RunInfo.csv**

Example:
20170501_BiThermal_SF_VSM_SF20170426_MvsH-5K.DAT

This means that the data was collected on May 1, 2017. It belongs to the project "BiThermal" (note the capitalization), and was recorded by user S.F. on the instrument VSM for sample SF20170426. The *RunInfo* makes the data file unique in case several measurements are made on the same sample on the same day with the same machine. As additional data, it is noted that magnetization versus applied field (MvsH) is measured at 5K. Do NOT use underscore(\_) other than to separate the elements. Make sure to follow the order exactly. The extension can be .csv, .txt, .asc, etc.

The instruments/tools most commonly used are:

- **XRD**: x-ray diffraction
- **VSM**: vibration sample magnetometer
- **AFM**: atomic force microscopy
- **Camera**: photo camera, digital image, phone camera, etc.
- **NTE**: nanomaster thermal evaporator
- **Spectrometer**: photo-spectrometer data, optical data
- **SpinCoater**: spin-coater
- **Sputter**: sputtering machine
- **Sample**: text file on how the sample was created

Note that a user can work on several projects, and/or several users can work on the same project.


# References

 Use [Zotero](https://www.zotero.org/)  to manage your bibliography and all related articles along with a plugin for Chrome browser. You can install Zotero here:

 - [Zotero Install](https://www.zotero.org/)

## Better BibTeX

 Also install the extension: Better BibTeX for Zotero:

 - [Better BibTeX for Zotero](https://retorque.re/zotero-better-bibtex/installation/)

You need to configure the extension as follows: Go to **Preferences** -> **Better BibTeX** -> **Citation Keys**, and enter the following into the “Citation key format”:
 ```R
 [auth]_[Title:skipwords:select,1,1:ascii:nopunct]_[year]
 ```

 Each paper is then labeled with the author, first word of the title followed by the year. This should be unique in most cases, but in rare events, single letters are appended to distinguish separate papers; however that could be a duplicate, so make sure to eliminate duplicate references from your library periodically.

 More information is found at [Better BibTeX on GitHub](https://github.com/retorquere/zotero-better-bibtex).  A complete list of [citation keys](http://retorque.re/zotero-better-bibtex/citing/) is provided for reference.

 In particular the QuickCopy format is "LaTeX" and the Citation key format is should be used, so that you can use Ctrl-Shift-C to copy a citation into your LaTeX file.

## Publication Labeling

 Papers should be stored in the format Author_FirstWordTitle_Year.pdf

 Example: **Gentry_Asymmetric_2009.pdf** for the paper [Gentry, Gredig, Schuller](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.80.174118), "Asymmetric grain distribution in phthalocyanine thin films" published in Phys. Rev. B 80 (2009).

 Note that this is the same as for citations, so in LaTeX you would cite:

 ```LaTeX
 \cite{Gentry_Asymmetric_2009}
 ```

All publications and documents are stored in the *Papers* folder using the file naming convention above. The advantage of this labeling system are that you can search for the paper by typing the first author name and search for PDF files on your computer, once you have the PDF filename you can also easily cite the work, plus there is no confusion about the year it was published.

# R


Data analysis and results graphing should be done using `R` language, so that it is reproducible.

Organize yourself in the following way.

- Make a file called `make-thesis-graphs.R` and include all subroutines that generate graphs there.
- Make a file called `myConfig.R` and define all folders in there that will be used, so that the files can be run on different systems.


## LaTeX

The [M.S. thesis template](https://github.com/thomasgredig/MSthesis-template) is available as a LaTeX document. Here is a list of useful commands in LaTeX:

#### Proper Spacing for SI units

```LaTeX
\usepackage{siunitx}		
\sisetup{detect-weight=true, detect-family=true} % bold font support
\DeclareSIUnit\oersted{Oe}

\SI{e-7}{\meter} is \SI{0.1}{\micro\meter}

# for units only use
\si{\nano\meter}
```

#### Changing the name / capitalization of the Table of Contents

For longer documents KOMA class is useful, but it is not compatible with all the other commands. A typical document [KOMA script](http://texdoc.net/texmf-dist/doc/latex/koma-script/scrguien.pdf) would start with:

```LaTeX
\documentclass[12pt,oneside,letterpaper,
    chapterprefix=on,numbers=noenddot]{scrbook}
```

The table of contents can be changed, even if you are using the babel pacakge, since `\renewcommand{\contentsname}{Table of Contents}` may not work in that environment.

```LaTeX
\usepackage[english]{babel}  
\addto\captionsenglish{\def\contentsname{TABLE OF CONTENTS}}
\KOMAoptions{toc=chapterentrydotfill} % dotted chapter entries
\setkomafont{chapterentry}{} % make chapter titles not bold
\addtokomafont{chapterentrypagenumber}{\mdseries} % make page numbers not bold
```


#### Common Widths for Graphs

```LaTeX
\newcommand{\FIGwide}{0.9\textwidth}

\begin{figure}
    \centering    % note: file extension not needed
    \includegraphics[width=\FIGwide]{imagefile}  
    \caption[short caption for TOC]
      {Long and detailled caption that appears under figure.}
    \label{fig:mylabel}
\end{figure}
```

#### Angles

```LaTeX
\ang{6.8}
```

Whenever possible, LaTeX tables should be generated using `R` and saved in the Results-Generated folder, then use (note that the file that generates is the same, such as sample-table.R, or sample.R)

```LaTeX
\input{../../Results-Generated/sample-table.tex}
```
If a table is not generated in `R`, then save an Excel spreadsheet or CSV spreadsheet in the `Results` folder and use [Table Generator Online](https://www.tablesgenerator.com/latex_tables) and include the filename in the LaTeX document, so that it can be easily updated, if needed.



#### Bibliography

For bibliography, you can use the [natbib](https://www.ctan.org/pkg/natbib) or [apacite](https://www.ctan.org/pkg/apacite) packages, here is an example:

```LaTeX
\usepackage[square,sort,comma,numbers,sort&compress]{natbib}
# \usepackage[apaciteclassic,nodoi]{apacite}

\cite{Gredig_Substrate-controlled_2012}

# for author names
\citeauthor{Gredig_Substrate-controlled_2012}

# for displaying the year of the article
\citeyear{Gredig_Substrate-controlled_2012}

\bibliographystyle{plainnat}
# \bibliographystyle{apacite}

\bibliography{myBib}
```
It is sometimes needed to make the bibliography smaller, since it may contain many citations, which are not used. You can use this `main.R` to accomplish this: [LaTeX Trim BibTeX](https://github.com/thomasgredig/LaTeX-trim-BibTeX)


## Useful Commands in R

First few lines of your `R` code should load the libraries and also some common data:

```R
library(ggplot2)
source('myConfig.R')
```

Creating relative file paths:

```R
# generates ../RAW or ..\RAW depending on the OS
my.path = file.path('..','RAW')
```

Basic plot using [ggplot2](https://ggplot2.tidyverse.org/):

```R
library(ggplot2)
d = read.csv(file.path(path.RAW,'data.csv'))
ggplot(d, aes(x,y, col=type)) +
  geom_point(size=2) +
  xlab('T (K)') +
  ylab(expression(paste('M'[sat],' (10'^-6,' emu)'))) +
  theme_bw(base_size = 18)
ggsave(file.path(path.FIGS,'MvsH-data.png'), width=6, height=4, dpi=220)
```

There are some libraries that are useful to analyze the following data:

- VSM: see [Quantum Design PPMS package](https://github.com/thomasgredig/quantumPPMS)
- XRD: see [Rigaku XRD package](https://github.com/thomasgredig/rigakuXRD)
- AFM: see [AFM package](https://github.com/thomasgredig/nanoscopeAFM)

Here is how you could load these packages:


```R
# this needs to be installed only once:
install.packages("devtools")
devtools::install_github("thomasgredig/nanoscopeAFM")
devtools::install_github("thomasgredig/quantumPPMS")
devtools::install_github("thomasgredig/rigakuXRD")

# libraries must be loaded each time:
library(nanoscopeAFM)
library(quantumPPMS)
library(rigakuXRD)
```
