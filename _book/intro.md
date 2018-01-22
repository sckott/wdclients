

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
1. Download and install RStudio, <https://www.rstudio.com/download>.
1. Install needed packages (see below).

### R packages


```r
pkgs <- c(
  "jsonlite", "knitr", "curl", "httr", "crul"
)
install.packages(pkgs)
```

You'll also need to install some R packages. An R _package_ is a collection of functions, data, and documentation that extends the capabilities of base R. Using packages is key to the successful use of R. To install all the packages used in this book open RStudio and run:

R will download the packages from CRAN and install them in your system library. If you have problems installing, make sure that you are connected to the internet, and that you haven't blocked <https://cran.rstudio.com> in your firewall or proxy.

You will not be able to use the functions, objects, and help files in a package until you load it with `library()`. After you have downloaded the packages, you can load any of the packages into your current R session with the `library()` command, e.g.


```r
library(crul)
```

You will need to reload the package every time you start a new R session.

## Acknowledgements

xxx

## Colophon

This book was built with:


```r
devtools::session_info(pkgs)
#> Session info -------------------------------------------------------------
#>  setting  value                                      
#>  version  R version 3.4.3 Patched (2018-01-01 r74017)
#>  system   x86_64, darwin15.6.0                       
#>  ui       X11                                        
#>  language (EN)                                       
#>  collate  en_US.UTF-8                                
#>  tz       America/Los_Angeles                        
#>  date     2018-01-21
#> Packages -----------------------------------------------------------------
#>  package   * version    date       source                            
#>  crul        0.5.0      2018-01-20 local (ropensci/crul@8e42db2)     
#>  curl        3.1        2017-12-12 CRAN (R 3.4.3)                    
#>  digest      0.6.14     2018-01-14 CRAN (R 3.4.3)                    
#>  evaluate    0.10.1     2017-06-24 CRAN (R 3.4.1)                    
#>  glue        1.2.0      2017-10-29 CRAN (R 3.4.2)                    
#>  graphics  * 3.4.3      2018-01-02 local                             
#>  grDevices * 3.4.3      2018-01-02 local                             
#>  highr       0.6        2016-05-09 CRAN (R 3.4.0)                    
#>  httpcode    0.2.0.9000 2018-01-11 local (sckott/httpcode@f6aa4e3)   
#>  httr        1.3.1      2017-08-20 CRAN (R 3.4.1)                    
#>  jsonlite    1.5        2017-06-01 CRAN (R 3.4.0)                    
#>  knitr       1.18       2017-12-27 cran (@1.18)                      
#>  magrittr    1.5        2014-11-22 CRAN (R 3.4.0)                    
#>  markdown    0.8        2017-04-20 CRAN (R 3.4.0)                    
#>  methods     3.4.3      2018-01-02 local                             
#>  mime        0.5        2016-07-07 CRAN (R 3.4.0)                    
#>  openssl     0.9.9      2017-11-10 CRAN (R 3.4.2)                    
#>  R6          2.2.2      2017-06-17 CRAN (R 3.4.0)                    
#>  Rcpp        0.12.14    2017-11-23 CRAN (R 3.4.3)                    
#>  stats     * 3.4.3      2018-01-02 local                             
#>  stringi     1.1.6      2017-11-17 CRAN (R 3.4.2)                    
#>  stringr     1.2.0.9000 2017-12-29 Github (tidyverse/stringr@c8bbc0d)
#>  tools       3.4.3      2018-01-02 local                             
#>  triebeard   0.3.0      2016-08-04 CRAN (R 3.4.0)                    
#>  urltools    1.6.0      2016-10-17 CRAN (R 3.4.0)                    
#>  utils     * 3.4.3      2018-01-02 local                             
#>  yaml        2.1.16     2017-12-12 CRAN (R 3.4.3)
```

[imdb]: https://www.omdbapi.com/
[sw]: https://swapi.co/
[datagov]: https://www.data.gov/
