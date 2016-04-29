
# Package Automation

Writing bespoke R clients can be lots of fun, and is often necessary
beacuse any two randomly chosen REST APIs do not use the same patterns.
However, there are some ways to automate package creation.

## API Specifications

Some REST APIs have machine readable specifications for their API. Most
small operations don't have time for this, so you usually see this in larger
companies. These specifications allow a definition of the API, but can
also be used to programmatically create a client.

The `apispecs` repo [https://github.com/ropenscilabs/apispecs](https://github.com/ropenscilabs/apispecs)
holds an increasing set of API specifications targeting smaller scientifically
useful APIs that don't already have specifications. We are using the OpenAPI
specification.

xxx...

## Package generator

`apipkgen` [https://github.com/ropenscilabs/apipkgen](https://github.com/ropenscilabs/apipkgen)
is a package that can be used to generate R clients from API specs.

The following is a brief example


```r
devtools::install_github("ropenscilabs/apipkgen")
library("apipkgen")
```

Generate a package using the function `generate_pkg()`


```r
template <- system.file('examples', 'template_crossref.yml', package = "apipkgen")
apipkgen::generate_pkg("../crpkg", template_path = template)
```

The package created doesn't have any exported functions, just internal functions for
your to build user facing functions.

Let's write a user facing functions. The Crossref API template above specified for the
`works` route that parameters are `query` and `rows`. So let's work with those.


```r
crossref_works <- function(query = NULL, rows = NULL, ...) {
  works(query = query, rows = rows, ...)
}
```

In addition, it's a good idea to always allow users to pass in curl options. Beginners
can ignore it, but power curl users will want/have to play with curl options. The
function builder builds in `...` as a parameter so in the user facing function above
all you have to do is add that as well for users to access.

Now install the new package. Go to the new directory, and in R/RStudio run
`devtools::document()` and `devtools::install()` (or equivalent).

Now you can use the package. Call the function. The package builder gives back plain
text, so you have to parse it yourself.


```r
res <- crossref_works(query = "science")
jsonlite::fromJSON(res)
#> $status
#> [1] "ok"
#>
#> $`message-type`
#> [1] "work-list"
#>
#> $`message-version`
#> [1] "1.0.0"
#>
#> $message
#> $message$query
#> $message$query$`search-terms`
#> [1] "science"
#>
#> $message$query$`start-index`
#> [1] 0
#>
#>
#> $message$`items-per-page`
#> [1] 20
#>
#> $message$items
#>     indexed.date-parts    indexed.date-time indexed.timestamp reference-count
#> 1        2015, 12, 27 2015-12-27T23:37:50Z      1.451259e+12               0
#> 2        2015, 12, 24 2015-12-24T22:03:23Z      1.450995e+12               0
#> 3        2015, 12, 25 2015-12-25T19:17:30Z      1.451071e+12               0
#> 4        2015, 12, 27 2015-12-27T19:35:51Z      1.451245e+12               0
```

## Keeping up to date

xxxx
