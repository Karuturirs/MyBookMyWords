#<center> R Language</center>

## Essentials of R Programming

Everything you see or create in R is an  object. A vector, matrix, data frame, even a variable is an object. R  treats it that way. So, R has 5 basic classes of objects. This includes:

1. Character
2. Numeric (Real Numbers)
3. Integer (Whole Numbers)
4. Complex
5. Logical (True / False)

An object can have following attributes:

1. names, dimension names
2. dimensions
3. class
4. length

### Data Types in R

* **Vector:**  a vector contains object of same class.

  ``` R
  > x <- c(5, 10)
  > x
  [1] 5 10
  ```

  

* **List:** A list is a special type of vector which contain elements of different data types.

  ```R
  > >  my_list <- list(22, "ab", TRUE, 1 + 2i)
  > my_list
  [[1]]
  [1] 22
  
  [[2]]
  [1] "ab"
  
  [[3]]
  [1] TRUE
  
  [[4]]
  [1] 1+2i
  
  > my_list[[3]]
  > [1] TRUE
  ```

* **Matrices:** When a vector is introduced with *row* and *column* i.e. a dimension attribute, it becomes a matrix.

```R
> my_matrix <- matrix(1:6, nrow=3, ncol=2)
> my_matrix
     [,1] [,2]
[1,]    1    4
[2,]    2    5
[3,]    3    6

> dim(my_matrix)
[1] 3 2

> attributes(my_matrix)
$dim
[1] 3 2

> my_matrix[,2]   #extracts second column
> my_matrix[,1]   #extracts first column
> my_matrix[2,]   #extracts second row
> my_matrix[1,]   #extracts first row

```

As an interesting fact, you can also create a matrix from a vector. All you need to do is, assign dimension dim() later. Like this:

```R
> age <- c(23, 44, 15, 12, 31, 16)
> age
> [1] 23 44 15 12 31 16

> dim(age) <- c(2,3)
> age
> [,1] [,2] [,3]
> [1,] 23 15 31
> [2,] 44 12 16

> class(age)
> [1] "matrix"
```

**Continuous variables** are those which can take any form such as 1, 2, 3.5, 4.66 etc. **Categorical variables** are those which takes only discrete values such as 2, 5, 11, 15 etc. In R, categorical values are represented by factors. In df, name is a  factor variable having 4 unique levels. Factor or categorical variable  are specially treated in a data set. For more explanation, click [here](https://www.analyticsvidhya.com/blog/2015/11/easy-methods-deal-categorical-variables-predictive-modeling/). Similarly, you can find techniques to deal with continuous variables [here](https://www.analyticsvidhya.com/blog/2015/11/8-ways-deal-continuous-variables-predictive-modeling/).

```R
> df[1:2,2] <- NA #injecting NA at 1st, 2nd row and 2nd column of df 
> df
name score
1 ash NA
2 jane NA
3 paul 87
4 mark 91

> is.na(df) #checks the entire data set for NAs and return logical output
name score
[1,] FALSE TRUE
[2,] FALSE TRUE
[3,] FALSE FALSE
[4,] FALSE FALSE
> table(is.na(df)) #returns a table of logical output
FALSE TRUE
6      2

> df[!complete.cases(df),] #returns the list of rows having missing values
name  score
1 ash  NA
2 jane NA
```

