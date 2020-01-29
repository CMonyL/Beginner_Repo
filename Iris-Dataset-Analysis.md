Iris Dataset analysis
================
Chan Mony Lach
29/01/2020

## The beginning

Hello World\!

I am far from being experienced in data science, therefore I figured I
should start with one of the most common datasets in the world; the
*IRIS* dataset.

This dataset is was commonly referred to in throughout my university
courses as a means to introduce various machine learning/statistical
concepts.

Fortunately this dataset is already built into R, which makes it a
suitable candidate for a beginner Exploratory Data Analysis (EDA).

The dataset describes three classes of flowers:

  - Setosa
  - Versicolor
  - Virginica

As well as their sepal length/width and petal length/width.

The first line of code will assign the iris dataset to an object called
“iris\_data”. This will allow for more functions to be applied to the
object at a later stage of this EDA.

The head() function will display the first 5 rows of the dataset.

The dim() function wil describe the dimensions of the iris dataset (or
“iris\_data” object). The function shows that there are 150 rows of
data with 5 headings.

``` r
iris_data <- iris
head(iris_data)
```

    ##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1          5.1         3.5          1.4         0.2  setosa
    ## 2          4.9         3.0          1.4         0.2  setosa
    ## 3          4.7         3.2          1.3         0.2  setosa
    ## 4          4.6         3.1          1.5         0.2  setosa
    ## 5          5.0         3.6          1.4         0.2  setosa
    ## 6          5.4         3.9          1.7         0.4  setosa

``` r
dim(iris_data)
```

    ## [1] 150   5

By referring to the previous head() function, we can see that the 5
headings are: \* Sepal.Length \* Sepal.Width \* Petal.Length \*
Petal.Width \* Species

The summary() function allows us to see summary statistics of the
dataset.

``` r
summary(iris_data)
```

    ##   Sepal.Length    Sepal.Width     Petal.Length    Petal.Width   
    ##  Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100  
    ##  1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300  
    ##  Median :5.800   Median :3.000   Median :4.350   Median :1.300  
    ##  Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199  
    ##  3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800  
    ##  Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500  
    ##        Species  
    ##  setosa    :50  
    ##  versicolor:50  
    ##  virginica :50  
    ##                 
    ##                 
    ## 

Interestingly enough, it also shows the unique values of each flower,
and their occurences in the dataset which is seeen in the “species”
column.

A useful function to see the *type* of data in the dataset is sapply().
e.g. sapply(data, typeof)

``` r
sapply(iris_data, typeof)
```

    ## Sepal.Length  Sepal.Width Petal.Length  Petal.Width      Species 
    ##     "double"     "double"     "double"     "double"    "integer"

This shows that all the data in this dataset are of type *double*, with
the exception of species which is *integer*.

My understanding is that in the *real world*, datasets are not always
going to be clean, and some entries may have null values. The *is.null*
function can be used to check if the object contains null values.

If the output is *TRUE*, then our dataset does contain NULL values, and
therefore we can either choose to omit them from our analysis or do
something else. However, if the output is *FALSE*, then our dataset
*DOES NOT* contain null values (which is a good thing\!).

``` r
is.null(iris_data)
```

    ## [1] FALSE
