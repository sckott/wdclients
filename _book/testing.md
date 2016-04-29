
# Testing

## testthat

### Skipping tests

You should skip any tests on CRAN via `testthat::skip_on_cran()` that call web resources, whether they be an API, FTP, flat file, or URL. This is because those web resources can be down when the test is run - at which point CRAN maintainers will complain to you that your tests are failing. 

There are likely a subset of unit tests you can run for functions that call web resources - e.g., you can test failure modes if the function call does not actually make a web request, but rather is testing parameter inputs, etc.

If you skip tests on CRAN, you should still run tests on your continuous integration system. But those can be skipped as well via `testthat::skip_on_travis()`.

### Test if web resource is up

One approach to web resources is to safely test if the web service is up or not before running further tests. This way you can still run your test suite if the web resourcs is up, but avoid failures if it is not up.

## Mocking web requests

A commonly used solution in test suites in other programming languages is to mock web requests. That is, you can store the results of a web request (usually as JSON data) in files in your test suite directory, then test expections use those cached files instead of doing real web requests. This requires that web requests are matched against the available cached files.

This approach of course requires libraries that provide the infrastructure to do make this easy - two approaches are described below with two R packages ported from the Ruby programming language.

### vcr

`vcr` takes the approach of storing cached requests in specifically named files, or _cassettes_. You insert a cassette to use it, do web requests, then eject the cassette when done. After ejection, the file is still there, but you are no longer writing to it. 

Note: It is still in early development, so expect changes.

## webmockr

`webmockr` takes a different approach than `vcr`. It doesn't require you to set up certain files to write to, but rather caches responses to web requests in the Ruby session during interactive use. Of course, for usage in a test suite, the responses are written to files, that then are used in subsequent test suite runs.  
