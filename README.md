# MSthesis-Guidelines
 guidelines for writing an M.S. thesis


# M.S. Thesis

You should be familiar with writing and if not refresh your memory with a book, such as "A Manual for Writers of Research Papers, Theses and Dissertations" by Kate L. Turabian. It contains general information. In the following, we will add some specific approaches towards writing a physics M.S. thesis in experimental condensed matter.

# Comprehensive Powerpoint File

Keep a lengthy comprehensive powerpoint file. It should include data more or less in chronological order. It is not important to keep it tidy, but rather it is important to keep it clean and update this file regularly. It should contain 100 - 300 slides. The slides can include photos of samples, reviews and snippets of literature, graphs from results, calculations from the analysis, schematics and plans. Use the *notes* section to add folder, filenames, and other information pertinent to the graph.


# File System

All files are in a shared [Dropbox](https://www.dropbox.com/) folder. The structure includes the following folders:

- **Abstracts**: any abstracts submitted for presentations or poster events,
- **Thesis**: LaTeX documents with entire thesis (except for generated figures and tables)


# Software Packages

 Familiarize yourself with the following tools

 * [Zotero](https://www.zotero.org/) for references
 * [R](https://www.r-project.org/) for graphs and tables
 * [LaTeX](https://www.latex-project.org/) for Thesis


## Labeling

 Samples are labeled as follows:

 * two initials of the person who makes the samples (example: TG)
 * date in format yyyy/mm/dd (example: 20190724)
 * if more than one sample is created in any one day by one author, then additional information is appended, which distinguishes the samples, such as Si1, Si2, for two samples made on silicon substrates, or rpm1, rpm2, for two samples created with two different spin speeds.

 Examples for sample names include: **TG20190724** or TG20190723Si1

Data files are labeled as follows:


.... add later

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
The advantage of this labeling system are that you can search for the paper by typing the first author name and search for PDF files on your computer, once you have the PDF filename you can also easily cite the work, plus there is no confusion about the year it was published.
