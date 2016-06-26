
# Easy HTTP Requests

For interactive use in R, the package `request` (<https://github.com/sckott/request>)
makes http requests quite simple.


* The web is increasingly a JSON world, so we assume applications/json by default, but give back other types if not
* The workflow follows logically, or at least should, from, hey, I got this url, to i need to add some options, to execute request
* Whenever possible, we transform output to data.frame's - facilitating downstream manipulation via dplyr, etc.
* We do GET requests by default. Specify a different type if you don't want GET
* You can use non-standard evaluation to easily pass in query parameters without worrying about &'s, URL escaping, etc. (see api_query())
* Same for body params (see api_body())
