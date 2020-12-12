
<!-- README.md is generated from README.Rmd. Please edit that file -->

<!-- Use snippet 'render_markdown' for it -->

# yamlme

<!-- badges: start -->

[![Travis build
status](https://travis-ci.com/kamapu/yamlme.svg?branch=master)](https://travis-ci.com/kamapu/yamlme)
[![Codecov test
coverage](https://codecov.io/gh/kamapu/yamlme/branch/master/graph/badge.svg)](https://codecov.io/gh/kamapu/yamlme?branch=master)
<!-- badges: end -->

## Installing yamlme

For installing this package use `devtools`:

``` r
library(devtools)
install_github("kamapu/yamlme", build_vignettes = TRUE)
```

## Create and modify a document

This package aims to save documents with their respective settings
(yaml-head) in R-objects.

``` r
my_document <- write_rmd(title = "Mi First Document", author = "My Name",
        output = "html_document", append = "# This is a comment in head",
        body = txt_body(
                "# Starting a working day",
                "",
                "At the beginning of every day I will do:",
                "",
                "- Say everyone \"Good morning!\"",
                "- Start the coffe mashine",
                "- Start the computer",
                "- Read mails"))
cat(my_document)
#> ---
#>  title: Mi First Document
#>  author: My Name
#>  output: html_document
#>  # This is a comment in head
#>  ---
#> 
#>  # Starting a working day
#>  
#>  At the beginning of every day I will do:
#>  
#>  - Say everyone "Good morning!"
#>  - Start the coffe mashine
#>  - Start the computer
#>  - Read mails
#> 
```

By this way it is possible to produce documents from plain R-code. This
document can be then rendered by the function `render_rmd()`.

``` r
render_rmd(input = my_document, output_file = "my_document")
```

For more details, take a look on the vignette.

``` r
vignette("yamlme-intro")
```
