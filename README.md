# Boot-camp

<img width="1280" alt="screen shot 2015-09-02 at 10 10 46 am" src="https://cloud.githubusercontent.com/assets/14082101/9638307/ee510faa-515a-11e5-892a-d835cc80b69e.png">

<img width="1280" alt="screen shot 2015-09-02 at 10 59 55 am" src="https://cloud.githubusercontent.com/assets/14082101/9639663/e9eaba5e-5161-11e5-9b87-3f46c9dc2c73.png">

<img width="1280" alt="screen shot 2015-09-02 at 11 15 59 am" src="https://cloud.githubusercontent.com/assets/14082101/9640023/0de4a116-5164-11e5-84d5-cb14a8c1042e.png">

<img width="1280" alt="screen shot 2015-09-02 at 11 49 52 am" src="https://cloud.githubusercontent.com/assets/14082101/9640923/d82cf438-5168-11e5-970a-0455b71134ed.png">

<img width="1280" alt="screen shot 2015-09-02 at 12 27 55 pm" src="https://cloud.githubusercontent.com/assets/14082101/9641915/19781d14-516e-11e5-9cae-2a59dfafecaf.png">

# This will calculate the mean of 10 random standard normal variables.
mean(rnorm(10))  
# shortcut select/block-command enter

'?'(mean) # sama dengan ?(mean), help(mean)

# If you don't know the exact name of the R function you want help with, you can try
help.search("mean")
apropos("mean")
# These will provide lists of places you can look for functions related to this keyword.

# If you are on line, help for functions that you have not yet downloaded can be retrieved with
RSiteSearch()

# To learn more about help function, combine them!
help(RSiteSearch)

a <- 2+3 ; a # ; untuk langsung menentukan nilai a tanpa mengetik ulang
b <- a+a; b
a+a; a+b # I can perform two actions on one line by separating them with a semicolon.
# [1] 10
# [1] 15

# VECTORS

Y <- c(8.3, 8.6, 10.7, 10.8, 11, 11, 11.1, 11.2, 11.3, 11.4)
Y = c(8.3, 8.6, 10.7, 10.8, 11, 11, 11.1, 11.2, 11.3, 11.4)

# Sequences
1:4
# [1] 1 2 3 4

4:1
# [1] 4 3 2 1

-1:3
# [1] -1  0  1  2  3

-(1:3)
# [1] -1 -2 -3

seq(from=1, to=3, by=0.2)
# [1] 1.0 1.2 1.4 1.6 1.8 2.0 2.2 2.4 2.6 2.8 3.0

seq(1, 3, by=0.2)
# [1] 1.0 1.2 1.4 1.6 1.8 2.0 2.2 2.4 2.6 2.8 3.0

seq(1, 3, length=7) # dari 1 sampai 3 dibagi 7
# [1] 1.000000 1.333333 1.666667 2.000000 2.333333
# [6] 2.666667 3.000000

rep(1,3) # repeated "1", 3 times
# [1] 1 1 1

rep(1:3, 2) # repeated "1,2,3", 2 times
# [1] 1 2 3 1 2 3

rep(1:3, each=2) # repeated "1". 2 times, followed by "2", 2 times and "3", 2 times
# [1] 1 1 2 2 3 3

Y = c(8.3, 8.6, 10.7, 10.8, 11, 11, 11.1, 11.2, 11.3, 11.4)
sum(Y)
mean(Y)
max(Y)
length(Y)
summary(Y)
# Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
# 8.30   10.72   11.00   10.54   11.18   11.40 

Names <- c("Sarah", "Yunluan"); Names
# [1] "Sarah"   "Yunluan"

b <- c(TRUE, FALSE); b

class(Y)
# [1] "numeric"

class(b)
# [1] "logical"

Y > 10 # we test whether each element of a vector is greater than a particular value
# [1] FALSE FALSE  TRUE  TRUE  TRUE  TRUE  TRUE
# [8]  TRUE  TRUE  TRUE

Y > mean(Y)
Y == 11 # we tested whether a vector is wqual to a number
Y != 11 # test of "not equal to"

# algebra with vectors
 a <- 1:3
 b <- 4:6
 a+b
 
a*b
a/b
a+1
a*2
1/a
a * 1:2
# [1] 1 4 3
# Warning message:
# In a * 1:2 :
# longer object length is not a multiple of shorter object length
a * c(1,2,1)

1:4 * 1:2
# [1] 1 4 3 8
# On the other hand, if we multiply vectors of length 4 and 2, we get no error,
# because four is a multple of 2.
# this is same with: 
1:4 * c(1,2,1,2)

# Extraction and missing values

Y[1]
Y[1:3]

Y > mean(Y)
Y[Y > mean(Y)]

# Missing data-"NA" is "Not Available"
a <- c(5,3,6,NA); a
is.na(a)
# [1] FALSE FALSE FALSE  TRUE
!is.na(a)
# [1]  TRUE  TRUE  TRUE FALSE

a[!is.na(a)]
# [1] 5 3 6
na.exclude(a)
# [1] 5 3 6
# attr(,"na.action")
# [1] 4
# attr(,"class")
# [1] "exclude"

mean(a) # the result is NA, because it still count NA

mean(a, na.rm=TRUE)
d <- na.exclude(a); mean(d)
# both are the same functions

# MATRICES

matrix(letters[1:4], ncol=2)
M <- matrix(1:4, nrow = 2); M

M2 <- matrix(1:4, nrow=2, byrow=TRUE); M2
#      [,1] [,2]
# [1,]    1    2
# [2,]    3    4

I <- diag(1, nrow=2); I # Here is a matrix with 1s on the diagonal.
#      [,1] [,2]
# [1,]    1    0
# [2,]    0    1

Minv <- solve(M)
M %*% Minv
# need to learn more about this

M[1,2] # row 1, col 2
M[1,1:2] # row 1, col 1-2
M[,2] # col 2
M[,] # all the matrix

# DATA FRAME

dat <- data.frame(species = c("S.altissima", "S.rugosa", "E.graminifolia", "A.pilosus"), treatment = factor(c("Control", "Water", "Control", "Water")), height=c(1.1, 0.8, 0.9, 1), width=c(1, 1.7, 0.6, 0.2)); dat
#       species      treatment height width
# 1    S.altissima     Control    1.1   1.0
# 2       S.rugosa     Water      0.8   1.7
# 3 E.graminifolia     Control    0.9   0.6
# 4      A.pilosus     Water      1.0   0.2

dat[2,] # row 2, it show the col title and row 1 start with the first species data
dat[3,4] # row 3, col 4, start with first data (species name)

dat[,2] == "Water"
# [1] FALSE  TRUE FALSE  TRUE
# test whether each element column 2 is "Water"

dat[dat[,2] == "Water",] # just show the "Water" in column 2
subset(dat, treatment == "Water")
# both way produce the same result.
