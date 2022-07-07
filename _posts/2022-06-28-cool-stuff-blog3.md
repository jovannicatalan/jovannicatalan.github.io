Cool Stuff
================
Jovanni Catalan Hurtado
2022-06-28

``` r
## Render Code

rmarkdown::render("./Rmd/2022-06-28-cool-stuff-blog3.Rmd", 
                  output_format = "github_document",
                  output_dir = "./_posts",
                  output_options = list(
                    html_preview= FALSE
                    )
)  
```

## Prompt Response

I think it was really cool that we got to call an API we selected from a
list and learned how to parse it and create graphical and numerical
summaries for it.

Below is an example of calling an API to retrieve information on weather
a coordinate(longitude and latitude) is on water or not.

The basic endpoint is:
<https://api.onwater.io/api/v1/results/%5Blatitude%5D>,\[longitude\]?access_token=\[your_token\]

## Basic Example

``` r
library(httr)
## Make API call
apiURL <- paste("https://api.onwater.io/api/v1/results/23.92323,-66.3?access_token=", token, sep = "")
result <- GET(apiURL)


attributes(result)
```

    ## $names
    ##  [1] "url"         "status_code" "headers"     "all_headers"
    ##  [5] "cookies"     "content"     "date"        "times"      
    ##  [9] "request"     "handle"     
    ## 
    ## $class
    ## [1] "response"

``` r
## Parse results based on structure
parsed <- jsonlite::fromJSON((rawToChar(result$content)))
data.frame(parsed)
```

    ##            query                           request_id      lat
    ## 1 23.92323,-66.3 bf02bf45-3e98-4bdc-afe4-f5792d4485a7 23.92323
    ##     lon water
    ## 1 -66.3  TRUE
