## Morsel

[![Build Status](https://travis-ci.org/JuliaWeb/Morsel.jl.svg?branch=master)](https://travis-ci.org/JuliaWeb/Morsel.jl)
[![Coverage Status](https://coveralls.io/repos/JuliaWeb/Morsel.jl/badge.svg?branch=master)](https://coveralls.io/r/JuliaWeb/Morsel.jl?branch=master)
[![Morsel on Julia release](http://pkg.julialang.org/badges/Morsel_release.svg)](http://pkg.julialang.org/?pkg=Morsel&ver=release)

Morsel is a Sinatra-like micro framework for declaring routes and handling requests.
It is built on top of [HttpServer.jl](https://github.com/JuliaWeb/HttpServer.jl)
and [Meddle.jl](https://github.com/JuliaWeb/Meddle.jl).

**Installation**: `Pkg.add("Morsel")`

## Examples

Here is a brief example that will return a few different messages for different routes,
if you run this and open `localhost:8000` you will see "This is the root" for GET, POST or PUT requests.
The line `get(app, "/about") do ...` is shorthand for only serving GET requests through that route.

```julia
using Morsel

app = Morsel.app()

route(app, GET | POST | PUT, "/") do req, res
    "This is the root"
end

get(app, "/about") do req, res
    "This app is running on Morsel"
end

start(app, 8000)
```

[Here](https://bitbucket.org/jocklawrie/skeleton-webapp.jl) is an example that:

- Reads data from a csv
- Runs a linear regression
- Produces some interactive charts that can be viewed in your browser

The accompanying documentation is written for data scientists who have never written a web app before.


---

```julia
:::::::::::::
::         ::
:: Made at ::
::         ::
:::::::::::::
     ::
Hacker School
:::::::::::::
```
