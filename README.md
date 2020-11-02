chimpr
======



[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![cran checks](https://cranchecks.info/badges/worst/chimpr)](https://cranchecks.info/pkgs/chimpr)
[![R-check](https://github.com/sckott/chimpr/workflows/R-check/badge.svg)](https://github.com/sckott/chimpr/actions?query=workflow%3AR-check)
[![codecov.io](https://codecov.io/github/sckott/chimpr/coverage.svg?branch=master)](https://codecov.io/github/sckott/chimpr?branch=master)
[![rstudio mirror downloads](https://cranlogs.r-pkg.org/badges/chimpr)](https://github.com/metacran/cranlogs.app)
[![cran version](https://www.r-pkg.org/badges/version/chimpr)](https://cran.r-project.org/package=chimpr)

[Mailchimp API docs][docs]
[API reference][apiref]

## Authentication

Get a Mailchimp API key at <https://mailchimp.com/developer/>

Keep this key private. You can pass the key in to each function via the
`key` parameter, but it's better to store the key as an environment
variable (`MAILCHIMP_KEY`).

## Read only for now

We're sticking to read only (i.e., `GET`) methods for now.

## Package API

The `R6` classes `ChmpCampaigns`, `ChmpList`, and `ChmpReports` have methods on them that 
you can call for various API routes under each high level topic. Generally an id is 
required (e.g., campaign id, list id, report id), but there are some methods that don't 
require an id.

* `chmp_ping` - ping 
* `chmp_root` - API root
* `chmp_lists`/`chmp_lists_` - get all lists
* `ChmpCampaigns` - methods for campaigns
* `ChmpList` - methods for individual lists
* `ChmpReports` - methods for reports

## High vs. Low level package APIs

__High level API__

parse to a list or data.frame

__Low level API__

just get some JSON

## Rate Limiting

...

## Install

Development version


```r
remotes::install_github("sckott/chimpr")
```


```r
library("chimpr")
```

## lists

all lists


```r
# JSON
chmp_lists_()
# parse to data.frame where possible
chmp_lists()
# parse to a list
chmp_lists(parse = FALSE)
```

## Meta

* Please [report any issues or bugs](https://github.com/sckott/chimpr/issues).
* License: MIT
* Get citation information for `chimpr` in R doing `citation(package = 'chimpr')`
* Please note that this project is released with a [Contributor Code of Conduct][coc]. By participating in this project you agree to abide by its terms.

[docs]: https://mailchimp.com/developer/
[apiref]: https://mailchimp.com/developer/guides/get-started-with-mailchimp-api-3/

[coc]: https://github.com/sckott/chimpr/blob/master/CODE_OF_CONDUCT.md
