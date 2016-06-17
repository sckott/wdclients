
# Introduction



R is a powerful language for working with data. There is an immense amount 
of data on the internet. This book goes over the individual parts of working with data on the web, and teaches you how to make packages to get data on 
the web.

## What you will learn

There are many components to working with data on the web. This book won't 
be the most detailed in any of them, but will lay a foundation for doing 
each component well.

You'll learn about File Transfer Protocl (FTP), and how to work with it in R.
Many government organizations provide data this way. It's a great method for
large data.

Much of the book will cover working with web Application Programming Interfaces (APIs). Public APIs are all over the place now: there's on for [IMDB][imdb], for [Star Wars][sw], for many [US government departments][datagov], and a lot more.

Finally, we'll cover how to write R packages to work with data on the web, 
whether the data is from FTP, scraped from website, or through a web API.

## Prerequisites

To run the code in this book, you will need to install both R and the RStudio IDE, an application that makes R easier to use. Both are open source, free and easy to install:

1. Download and install R, <https://www.r-project.org/alt-home/>.
1. Download and install RStudio, <http://www.rstudio.com/download>.
1. Install needed packages (see below).

### R packages


```r
pkgs <- c(
  "jsonlite", "knitr", "httr"
)
install.packages(pkgs)
```

You'll also need to install some R packages. An R _package_ is a collection of functions, data, and documentation that extends the capabilities of base R. Using packages is key to the successful use of R. To install all the packages used in this book open RStudio and run:

R will download the packages from CRAN and install them in your system library. If you have problems installing, make sure that you are connected to the internet, and that you haven't blocked <https://cran.rstudio.com> in your firewall or proxy.

You will not be able to use the functions, objects, and help files in a package until you load it with `library()`. After you have downloaded the packages, you can load any of the packages into your current R session with the `library()` command, e.g.


```r
library(httr)
```

You will need to reload the package every time you start a new R session.

## Acknowledgements

xxx

## Colophon

This book was built with:


```r
devtools::session_info(pkgs)
#> Session info --------------------------------------------------------------
#>  setting  value                                      
#>  version  R version 3.3.0 Patched (2016-05-09 r70593)
#>  system   x86_64, darwin13.4.0                       
#>  ui       X11                                        
#>  language (EN)                                       
#>  collate  en_US.UTF-8                                
#>  tz       America/Los_Angeles                        
#>  date     2016-06-17
#> Packages ------------------------------------------------------------------
#>  package  * version date       source                      
#>  curl       0.9.7   2016-04-10 CRAN (R 3.3.0)              
#>  digest     0.6.9   2016-01-08 CRAN (R 3.3.0)              
#>  evaluate   0.9     2016-04-29 CRAN (R 3.3.0)              
#>  formatR    1.4     2016-05-09 CRAN (R 3.3.0)              
#>  highr      0.6     2016-05-09 CRAN (R 3.3.0)              
#>  httr       1.2.0   2016-06-15 CRAN (R 3.3.0)              
#>  jsonlite   0.9.22  2016-06-15 CRAN (R 3.3.0)              
#>  knitr      1.13.1  2016-06-17 Github (yihui/knitr@ce40cbf)
#>  magrittr   1.5     2014-11-22 CRAN (R 3.3.0)              
#>  markdown   0.7.7   2015-04-22 CRAN (R 3.3.0)              
#>  mime       0.4     2015-09-03 CRAN (R 3.3.0)              
#>  openssl    0.9.4   2016-05-25 CRAN (R 3.3.0)              
#>  R6         2.1.2   2016-01-26 CRAN (R 3.3.0)              
#>  stringi    1.1.1   2016-05-27 CRAN (R 3.3.0)              
#>  stringr    1.0.0   2015-04-30 CRAN (R 3.3.0)              
#>  yaml       2.1.13  2014-06-12 CRAN (R 3.3.0)
```

[imdb]: http://www.omdbapi.com/
[sw]: https://swapi.co/
[datagov]: https://www.data.gov/
