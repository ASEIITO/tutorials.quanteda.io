---
title: "Install packages"
weight: 5
draft: false
---

## RStudio

**quanteda** runs solely on [base R](https://cran.r-project.org/), but [RStudio](https://www.rstudio.com/products/rstudio/download/) makes it easy to write your code and inspect your objects. You will need to have [base R](https://cran.r-project.org/) installed, and we also recommend to install the latest version of [RStudio](https://www.rstudio.com/products/rstudio/download/).

## Quanteda

First, you need to have **quanteda** installed. You can do this from inside RStudio, from the Tools > Install Packages, or executing a command.


```r
install.packages("quanteda")
```

Since the release of **quanteda** version 3.0, `textstat_*`, `textmodel_*` and `textplot_*` functions are available in separate packages. We will use several of these functions in the chapters below and strongly recommend to install these packages.


```r
install.packages("quanteda.textmodels")
install.packages("quanteda.textstats")
install.packages("quanteda.textplots")
```


If you are feeling adventurous, you can install the latest build of **quanteda** from its [GitHub code page](https://github.com/quanteda/quanteda).

Note that on **Windows platforms**, it is also recommended that you install the [RTools suite](https://cran.r-project.org/bin/windows/Rtools/), and for **OS X** that you install [XCode](https://itunes.apple.com/gb/app/xcode/id497799835?mt=12) from the App Store.

{{% notice info %}}
If you use the **quanteda** package in your research, please cite:  
Benoit, Kenneth, Kohei Watanabe, Haiyan Wang, Paul Nulty, Adam Obeng, Stefan Müller, and Akitaka Matsuo. 2018 ["quanteda: An R package for the quantitative analysis of textual data."](https://www.theoj.org/joss-papers/joss.00774/10.21105.joss.00774.pdf) _Journal of Open Source Software_ 3(30), 774. https://doi.org/10.21105/joss.00774.  
{{% /notice %}}


## Other packages

We will use the **readtext** package to read in different types of text data in these tutorials. Again, you can do this using RStudio menu (Tools > Install Packages), or executing the following command.


```r
install.packages("readtext")
```

We will also use extra datasets in tutorials that are available in **quanteda.corpora**. This package is not on CRAN, but can be installed with the `install_github()` function from the **devtools** package


```r
install.packages("devtools") # get devtools to install quanteda.corpora
devtools::install_github("quanteda/quanteda.corpora")
```


{{% notice note %}}
If you already have **quanteda** and other packages installed, run Tools > Check for Package Updates to install the latest versions. We recommend to update all the packages using `update.packages()` to avoid errors caused by dependencies.
{{% /notice %}}


## Additional packages

The tutorials do not cover syntactical analysis, but you should install **spacyr** for  part-of-speech tagging, entity recognition, and dependency parsing. It provides an interface to the spaCy library and works well with **quanteda**. Note that you need to have Python installed to use the **spacyr** package. See the [package description](https://github.com/quanteda/spacyr/blob/master/README.md) for more information.


```r
install.packages("spacyr")
```

Finally, we show how to use **newsmap** to [classify documents](https://tutorials.quanteda.io/machine-learning/newsmap/) based on "seed words" in dictionaries and the **seededlda** package to run topic models. You can download the packages from [CRAN](https://cran.r-project.org/package=newsmap).


```r
install.packages("newsmap")
install.packages("seededlda")
```

To sum up, you need to load the following packages to run all examples: 


```r
require(quanteda)
require(quanteda.textmodels)
require(quanteda.textstats)
require(quanteda.textplots)
require(readtext)
require(devtools)
require(quanteda.corpora)
require(newsmap)
require(seededlda)
```

{{% notice note %}}
With `quanteda_options()` you can get or set global options affecting functions across **quanteda**. One very useful feature is changing the number of threads to use in parallelised functions. By default, **quanteda** uses two threads, but depending on the RAM of your machine, you can use more than two threads. 
For instance, `quanteda_options("threads" = 10)` will use ten threads which massively reduces the time to execute the parallelised functions.
{{% /notice %}}

