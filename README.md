# A Manual for BASS created with Bookdown

## About Bookdown


From bookdown.org:

The [bookdown](https://www.bookdown.org/) package is an open-source [R](https://www.r-project.org/) package that facilitates writing books and long-form articles/reports with R Markdown. Features include:

- Generate printer-ready books and ebooks from R Markdown documents.
- A markup language easier to learn than LaTeX, and to write elements such as section headers, lists, quotes, figures, tables, and citations.
- Multiple choices of output formats: PDF, LaTeX, HTML, EPUB, and Word.
- Possibility of including dynamic graphics and interactive applications (HTML widgets and Shiny apps).
- Support a wide range of languages: R, C/C++, Python, Fortran, Julia, Shell scripts, and SQL, etc.
- LaTeX equations, theorems, and proofs work for all output formats.
- Can be published to GitHub, bookdown.org, and any web servers.
- Integrated with the RStudio IDE.
...


There is quite an extensive documentation about Bookdown, i recommend starting at [chapter 2.1 Markdown Syntax](https://bookdown.org/yihui/bookdown/markdown-syntax.html).

## Local installation and setup


### RStudio IDE

You will need RStudio IDE and a recent version of R installed. You will also need Git installed, for instance GitHub Desktop.

Download RStudio IDE from [https://posit.co/products/open-source/rstudio/](https://posit.co/products/open-source/rstudio/).

### R (the language)

Download the language R from the local CRAN mirror in Umeå (https://mirror.accum.se/mirror/CRAN/)[https://mirror.accum.se/mirror/CRAN/]

Currently (2024-06-09) installing R on MacOS with brew will give an old version (3.5 or so). Bookdown needs R version 4.4, so download R from the R-project website.

### Git - in RStudio IDE (try this first)

The manual is change tracked via git on GitHub. To work with the files locally, you will need to clone the repository to your computer. Git will download all the files and changes from this very repo to a folder your computers filesystem.

Since the manuals repository is public (visible to anyone on the internet), you don't need to login to clone the repo, but to be able to *push* changes back to GitHub, you need to be authenticated.

There is a Git mode in the RStudio IDE, if you want, try it out.

### GitHub Desktop (separate program)

Download and install [GitHub Desktop](https://desktop.github.com/) to your computer.

When starting the program, you will want to *clone* the repository (File -> Clone a repository). The program will now ask for you GitHub credentials and you will be able to select the manual.

### Git from command line

If you are using the command line, you can just `cd` to where ever you prefer to have your code and do

`git clone https://github.com/brjann/manual`

Now git will download all the files and change history from GitHub. When done, all the files will be found in the folder `manual`. In this folder, there is a hidden folder, `.git` where all editing history of the repo is stored as different edits, patches, of all files in the repo.

## Editing the manual

If we leave Git and the versioning aside for a little while, how do we edit the manual?

The idea is to edit the files `00-Basics.Rmd` - `13-Refererences.Rmd` and bibliographies, images etc. The build step described below, but in short, Bookdown takes all the .Rmd-files and calculates internal references, numberings, renders mathematics etc. Then it outputs HTML files which ends up in the folder `docs`. Don't edit things directly in the docs-folder, since every new build will wipe all your changes there.

For instance, open the `08_Particiants.Rmd` in RStudio IDE. You will see the markdown with some syntax highlighting. You will also see images inlined in the document for reference.

Make some change in this file - add a new bogus header, like ### Adding Test Header. Also add some text below this header.

In the RStudio IDE, there is a tab "Build" with a small button "Build Book". Press Build Book. A lot of build steps occurs. A simple Web Browser-like window is opened, and the manual is shown there. Navigate to `10 Participants` (RStudio renumbers the chapters) and you should see your new header in the document.

## Commit changes

What has changed now?

If you go to the Git tab in RStudio IDE, you'll see a large number of files that has changed, bot 09-Instruments.Rmd (which was the file we changed), but also a lot of files under docs/, mostly html files, but also `.tex`, `.pdf` etc. All these files are changed (or re-created) during the build step.

Just commit the change in 09-Instrument.rmd by selecting this file, and the press the button `commit`. You will se a window where all additions are highlighted in green, and you are supposed to write a commit message telling the world what this change means.

A good commit message in this case would be "Testing out the new BASS manual workflow", press commit.

This is now stored in git, locally on you computer.

## Push changes

Try to push your change to GitHub. If you look on the repo website, you will see that the file `09-Instruments.Rmd` was changed a few seconds ago. Success.

But the manual on the internet is not updated with your new header yet. How come?

## Build (or render) the manual

We have already built the manual locally. We did chose to not commit these changes files in the /docs folder. When we commit tfiles to the /docs folder and pushes them, these are the files that are shown on the bass manual website.

## Release a new version of the manual (not automated yet)

It could be a good idea to release a new version of the manual in a somewhat structured manner. The build process has to be done locally, and all the /docs files should be commited and pushed.

The files in docs/ is actually the files served online via https://bass-manual.github.io/manual/ or https://brjann.github.io/manual/


