---
slug: posts
title: Blog
---

# STAT 385


I'm taking STAT 385 class because I need to get my Data Science Certificate. I first didn't like vectorizing because that was just not how I think. Since I started coding 5-6 years ago, I was always taught that short and good loops were the best, but you want to avoid that in R! I know. *Shocking*. 

So here's some code:

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


Both works, but the last one works better.

