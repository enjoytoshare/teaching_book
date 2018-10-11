# R Basics

How to make professional and beautiful plots

> **Tips:**
>
> Do things with multiple ways
>
> Efficient Writing: Bash &gt; R &gt; Perl/Python &gt; Excel &gt; C,C++

## 1. Install and Use R

** a. Install R**

See the official site of R: https://www.r-project.org/

Here is an example of installation in Linux (centos):

- For CentOS

  ```bash
  yum -y install epel-release
  yum -y install R
  ```
  
- For Ubuntu

  ```bash
  apt -y install r-base
  ```

** b. Install RStudio **

If you like a nice interface to use R instead of Linux command line, you can try **RStudio:** [https://www.rstudio.com/](https://www.rstudio.com/)

We have some instruction of Rstudio in [Appendix. Plot with R](/appendix/appendix.plots.md)

** c. Use R**

* How to quit?

`q()`

* How to get help?

`?t.test`



## 2. Basic Data Types

```r
> x = 10.5 # assign a decimal value
> x # print the value of x
[1] 10.5
> class(x) # print the class name of x
[1] "numeric"

> y = as.integer(3)
> y # print the value of y
[1] 3
> class(y) # print the class name of y
[1] "integer"

> z = 1 + 2i # create a complex number
> z # print the value of z
[1] 1+2i
> class(z) # print the class name of z
[1] "complex"

> x = 1; y = 2 # sample values
> z = x > y # is x larger than y?
> z # print the logical value
[1] FALSE
> class(z) # print the class name of z
[1] "logical"

> x = as.character(10.5)
> x # print the character string
[1] "10.5"
> class(x) # print the class name of x
[1] "character"
```

* **vector**

```r
> c(2, 3, 5)
[1] 2 3 5

> n = c(2, 3, 5)
> s = c("aa", "bb", "cc", "dd", "ee")
> c(n, s)
[1] "2" "3" "5" "aa" "bb" "cc" "dd" "ee"

> s = c("aa", "bb", "cc", "dd", "ee")
> s[3]
[1] "cc"
```

* **matrix**

```r
> B = matrix(
+ c(2, 4, 3, 1, 5, 7),
+ nrow=3,
+ ncol=2)

> B # B has 3 rows and 2 columns
[,1] [,2]
[1,] 2 1
[2,] 4 5
[3,] 3 7
```

* **list**

```r
> n = c(2, 3, 5)
> s = c("aa", "bb", "cc", "dd", "ee")
> b = c(TRUE, FALSE, TRUE, FALSE, FALSE)
> x = list(n, s, b, 3) # x contains copies of n, s, b
```

* **data frame**

```r
> n = c(2, 3, 5)
> s = c("aa", "bb", "cc")
> b = c(TRUE, FALSE, TRUE)
> df = data.frame(n, s, b) # df is a data frame
> df
n s b
1 2 aa TRUE
2 3 bb FALSE
3 5 cc TRUE
```



## 3. Examples

**A simple example of t test: **

* First, make two files, foo1 and foo2, write some numbers in each file, for example:
```
5.6
7.9
8.9
19.5
20.5
39.5
```

* Then, start R and type:

```r
x<-read.table("foo1") # read the file
y<-read.table("foo2") # read the file
x=x[,1]  # read the first column
y=y[,1]  # read the first column
t.test(x,y,alternative=c("less") )
t.test(x,y,altrenative=c("less"),paired=TRUE) # paired t test
```

* You can also write these into a file, script.R, then run  
`R CMD BATCH script.R`


**More R Examples:**

* [Appendix. Plot with R](/appendix/appendix.plots.md)
* [John's Github](https://github.com/urluzhi/scripts/tree/master/Rscript) 



## 4. More Readings and Practices

**Basic:**

* << Bioinformatics Data Skills >>
  * A Rapid Introduction to the R Language
* [Quick R](https://www.statmethods.net/) 可以从如下章节开始 :
 * Learning R  
 * R Interface  
 * Data Input  
 * Statistics


**Advanced:**

* [Advanced R Tutorial](https://lulab.gitbook.io/training/part-i-basic-skills/4.r)
* << Bioinformatics Data Skills >>
  * Working with Range Data
* [Quick R](https://www.statmethods.net/) 