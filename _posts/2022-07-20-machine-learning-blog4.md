Blog Post 4: Machine Learning
================
Jovanni Catalan Hurtado
2022-07-20

``` r
## Render Code

rmarkdown::render("./_Rmd/2022-07-20-machine-learning-blog4.Rmd", 
                  output_format = "github_document",
                  output_dir = "./_posts",
                  output_options = list(
                    html_preview= FALSE
                    )
)  
```

## What method did you find most interesting?

I thought the Tree based methods were pretty interesting since the fits
for these are a bit different. They split up the predictor space into
regions and predict the most prevalent class for that region. I think
that it would be pretty cool to see this in action in some sort of cool
app or to see how it is applied in a field or profession and be able to
test how well it  
performs there!

## Below is an example of a Classification Tree Fit

``` r
library(tree)
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
set.seed(3)

train <- sample(1:nrow(iris), size = nrow(iris)*.80)

irisTrain <- iris[train, ]
irisTest <- iris[-train, ]

treeFit <- tree(Species ~ ., data = irisTrain)
treePred <- predict(treeFit, select(irisTest, -Species), type = "class")
treeRMSE <- table(data.frame(treePred, iris$Species))
treeRMSE
```

    ##             iris.Species
    ## treePred     setosa versicolor virginica
    ##   setosa         14         14         7
    ##   versicolor     29         22        29
    ##   virginica       7         14        14
