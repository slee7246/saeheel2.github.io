---
slug: posts
title: Blog
---

# Covid-19 Maps

Very quick and simple visual map that shows the confirmed covid-19 cases in the U.S.

![Confirmed Covid-19 cases in the US](/images/covid19.jpg)
- Confirmed cases since April 30, 2020

![Covid-19 Deaths in the US](/images/covid19_deaths.jpg)
- Confirmed deaths since April 30, 2020


# STAT 385

I'm taking STAT 385 class for my Data Science Certification! 



Here's something about R that I was not familiar with: vectorizing. Since I started coding 6-7 years ago, I was always taught that short and good loops were the best, but you want to avoid that in R! I know. *Shocking*. 

So here's some code that prints names with 8 or more letters in them:

**Something that would be very normal in java or something, but want to be avoided in R:**

```{r}
long_names_vec <- function(names) {
  output <- c()
  for (i in 1:length(names)) {
    name <- names[i]
    if (nchar(name) >= 8) {
      output <- c(output, name)
    }
  }
  output
}
```

Running the function:

```{r}
my_names <- c("alexander", "david", "sebastian", "johnathan", "christopher", "ha",
              "washington", "lincoln", "maximo", "mason", "luca", "anthony", "kevin")
long_names_vec(names = my_names)

```
Output = 

```{r}
[1] "alexander"   "sebastian"   "johnathan"   "christopher" "washington" 

```

**But you can significanly reduce the runtime if you vecorize that code above into this:**


```{r}
long_name_vec <- function(names) {
  my_names[nchar(my_names) >= 8]
}
```

Running the same function:

```{r}

my_names <- c("alexander", "david", "sebastian", "johnathan", "christopher", "ha",
              "washington", "lincoln", "maximo", "mason", "luca", "anthony", "kevin")
# test your code
long_name_vec(names = my_names)

```
Output = 

```{r}
[1] "alexander"   "sebastian"   "johnathan"   "christopher" "washington" 

```


Both works and produces the same output, but the last one works better.

