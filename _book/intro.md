
# Introduction



xxxx

## What you will learn

xxxxx

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
#>  version  R version 3.2.4 Patched (2016-03-16 r70355)
#>  system   x86_64, darwin13.4.0                       
#>  ui       X11                                        
#>  language (EN)                                       
#>  collate  en_US.UTF-8                                
#>  tz       America/Los_Angeles                        
#>  date     2016-04-04
#> Packages ------------------------------------------------------------------
#>  package  * version date       source        
#>  curl       0.9.6   2016-02-17 CRAN (R 3.2.3)
#>  digest     0.6.9   2016-01-08 CRAN (R 3.2.3)
#>  evaluate   0.8.3   2016-03-05 CRAN (R 3.2.3)
#>  formatR    1.3     2016-03-05 CRAN (R 3.2.3)
#>  highr      0.5.1   2015-09-18 CRAN (R 3.2.2)
#>  httr       1.1.0   2016-01-28 CRAN (R 3.2.3)
#>  jsonlite   0.9.19  2015-11-28 CRAN (R 3.2.2)
#>  knitr      1.12.3  2016-01-22 CRAN (R 3.2.3)
#>  magrittr   1.5     2014-11-22 CRAN (R 3.2.0)
#>  markdown   0.7.7   2015-04-22 CRAN (R 3.2.0)
#>  mime       0.4     2015-09-03 CRAN (R 3.2.0)
#>  openssl    0.9.2   2016-02-26 CRAN (R 3.2.3)
#>  R6         2.1.2   2016-01-26 CRAN (R 3.2.3)
#>  stringi    1.0-1   2015-10-22 CRAN (R 3.2.2)
#>  stringr    1.0.0   2015-04-30 CRAN (R 3.2.0)
#>  yaml       2.1.13  2014-06-12 CRAN (R 3.2.0)
```
