---
title: Setup
---

> ## Before the workshop starts
> 1. Get the latest version of R.
> 2. Get the latest version of Bioconductor.
> 3. Install the specific Bioconductor packages we will be using.
> 4. Download the large genomics files that we will use.
{: .checklist}

## Software

This workshop will be conducted in R. You should have the most recent version
of R installed from [CRAN](https://cloud.r-project.org/).  I highly recommend
also installing the free version of
[RStudio Desktop](https://rstudio.com/products/rstudio/) to make R easier to
work with.

You should also install the latest version of
[Bioconductor](https://bioconductor.org/install/).  As of October 2020, you can
install Bioconductor with the following commands at the R prompt:

``` r
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install(version = "3.12")
```

The version number changes every six months.  If asked about updating packages,
I recommend selecting 'a' to update all, and not compiling packages from source.
If some packages fail to install, close RStudio, reopen it, and run the last
`install` command again.  Because of all the dependencies, even if you are doing
everything correctly it can take a few rounds.

Additionally, you should run code to install packages that we will need.

``` r
BiocManager::install(c("VariantAnnotation", "snpStats", "GenomicFeatures",
                       "airway", "scater"))
```

From CRAN, we'll install `magrittr`, which will let us use the `%>%` (pipe)
symbol to make some code more readable, as well as `ggplot2` for making some
graphs, and `dplyr` for some data frame manipulation.

``` r
install.packages(c("magrittr", "ggplot2", "dplyr"))
```

To make sure it worked, run the code

``` r
library(VariantAnnotation)
library(snpStats)
library(GenomicFeatures)
library(scater)
library(dplyr)
library(ggplot2)
```

Please complete all of the above installations at least a few hours before the
workshop begins, and email the instructor if you encounter any errors.

## Make a project in RStudio

In RStudio, go to File --> New Project --> New Directory --> New Project.
Name the project `variant_analysis_2020` or something that makes sense to you,
and put it in a folder of your choosing on your computer.  Once that is done,
in the lower right pane click "New Folder" and make a folder called "data".

If you have never made an RStudio project before and are confused, don't worry,
I will do a quick demonstration at the beginning of the workshop.  Please
still download the data files below, and save them somewhere that you can quickly
find them.

## Data

We will work with some public data from maize.  There are four files that you
need to download and save to the `data` folder in your project directory.

### For the December 2020 workshop

In the **[Box folder](https://uofi.box.com/s/3t9e9uq7bf2eqto01uy9my66igj6v8qx)**
for this workshop, download the four files in the `data`
folder.  See below for the origins of these files.

### Otherwise

Download the following two files
to your computer and unzip them (using `gunzip` on Linux or Mac, or
[7-Zip](https://www.7-zip.org/) on Windows):

[B73 v4 reference genome](https://download.maizegdb.org/Zm-B73-REFERENCE-GRAMENE-4.0/Zm-B73-REFERENCE-GRAMENE-4.0.fa.gz)

[B73 v4 gene annotations](https://download.maizegdb.org/Zm-B73-REFERENCE-GRAMENE-4.0/Zm-B73-REFERENCE-GRAMENE-4.0_Zm00001d.2.gff3.gz)

You should also download the
[example VCF](https://github.com/HPCBio/variant-analysis-workshop/raw/gh-pages/_episodes_rmd/data/hmp321_agpv4_chr1_subset.vcf.bgz)
that we'll be working with.  It is derived from a
[panel of 1210 maize lines](http://cbsusrv04.tc.cornell.edu/users/panzea/download.aspx?filegroupid=34)
([Bukowski et al., 2018](https://doi.org/10.1093/gigascience/gix134])).

Lastly, there is a small
[CSV to download](https://raw.githubusercontent.com/HPCBio/variant-analysis-workshop/gh-pages/_episodes_rmd/data/sig_hits.csv).

## R Code

You will learn the most if you follow along by typing the code yourself.
Mistakes are a good thing!  You find what you did wrong and remember it for next
time, and probably learn something new about R in the process.  However, I also
don't want anyone falling 15 minutes behind while tracking down one misplaced
parenthesis.  Therefore, I recommend downloading the RMarkdown files, which you
can use to quickly get caught up.

### For the December 2020 workshop

Download the one `.md` and four `.Rmd` files from the "Lessons_and_code" folder
on [Box](https://uofi.box.com/s/3t9e9uq7bf2eqto01uy9my66igj6v8qx).  Note that
exercise solutions have been deleted from these files.

### Otherwise

Go to the [_episodes_rmd](https://github.com/HPCBio/variant-analysis-workshop/tree/gh-pages/_episodes_rmd)
folder on GitHub.  From there, you can click on an individual episode and click
"Raw".  Save the `.Rmd` file to your computer.  (If you see raw text in your web
browser, right click on it and select "Save Page As".) Save the files into your
project directory.


{% include links.md %}
