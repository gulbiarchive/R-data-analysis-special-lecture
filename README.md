# R-data-analysis-special-lecture
Simple data analysis with R in a special lecture at UNI
# [0. Data analysis & R required for current employees](https://velog.io/@gulbi/Special-lecture0.-Data-analysis-R-required-for-current-employees)
# Why is important Data Analysis?

- Data mining: data analysis, meaningful pattern rules can be found
- Data visualization: dashboard, infographics, etc.
- Database management
- Company: Identify market trends, customers, and sales
- Government: Number of floating population(유동 인구), traffic volume, buses operating only at night, etc.
- Academic research

---

# What is R?

A language capable of statistical analysis, data visualization, and artificial intelligence

## When is to use R in company?

statistics based
Thousands of packages available or extended through CRAN
Can be used on various OS such as Windows, Mac, and Linux

## Examples of data analysis using R

[R을 활용한 데이터 분석 실습 - 분석사례 실습 튜토리얼, 실습자료 제공](https://bd.kma.go.kr/kma2020/dta/edu/KBP57000.do?pageNum=5&menuCd=F040301000)

## Install R

[The Comprehensive R Archive Network](https://cran.r-project.org/)

## Install R-Studio

[Posit](https://posit.co/download/rstudio-desktop/)

After install, **`File - New File - R Script`**

After writing the code in the script section, press Ctrl + Enter to print it on the console.

### What is Environment?

Window to manage variable

![스크린샷 2024-07-25 103656](https://github.com/user-attachments/assets/4d8da2ed-92ba-40e7-8f21-e8f3180f9b86)

## R and R-Studio?

R-Studio can be operated only if R is installed.

---

# Using R

## **Shortcut keys available in r**

ctrl + c : 복사

ctrl + v : 붙여넣기

ctrl + a : 전체 선택

ctrl + z : 실행 되돌리기

## **commet**

#
ctrl + shift + c : **Processing multiple comments at once(not ctrl + shift + /)**

---

# Simple Exercise

## Making Data

```r
# sales(변수를 나타냄) <-(R에서는 대입할 때 = 대신 <-를 사용함) data.frame(name=c(...), sale=c(...))
# c는 여러 개의 데이터를 combine한다는 뜻 
sales <- data.frame(name=c(‘kim’, ‘lee’, ‘jung’), sale=c(100, 200, 300))
```

**Code**

I want to create data called sales, but I want to create it as a data.frame (meaning something with rows and columns like Excel).
I want to put the names ‘kim’, ‘lee’, and ‘jung’ in the name field of data.frame() and write how much these people sold as sale, so I write 100, 200, and 300 in sale.

```
> sales <- data.frame(name=c('kim', 'lee', 'jung'), sale=c(100, 200, 300))
> sales
  name sale
1  kim  100
2  lee  200
3 jung  300
```
![스크린샷 2024-07-25 103734](https://github.com/user-attachments/assets/a3efa12c-8a6d-4406-b0ad-f7be7a677946)

# assignment

<aside>
❓ Created a dataframe under the name we for the data used in our department (ex: branch management)
→ How many NCC contents do I manage per day?

</aside>

```r
we <- data.frame(name=c('FC', 'mapleM'), count=c(100, 50))
```

```r
> we <- data.frame(name=c('FC', 'mapleM'), count=c(100, 50))
> we
    name count
1     FC   100
2 mapleM    50
```
# [01. Analyze data with an example](https://velog.io/@gulbi/01.-Analyze-data-with-an-example)
# Review

## Create Data

```r
sales <- data.frame(name=c(...), sale=c(...))
```

---

# Load Data

```r
df <- read.csv("df.csv"); df
df <- rad.csv("D:/test/df.csv"); df
write.csv(df, "D:/df2.csv", row.names=F)
```

## csv files to use

```r
df <- read.csv("C:/Users/jihyeonpark/Desktop/df.csv")
df1 <- read.csv("C:/Users/jihyeonpark/Desktop/1.csv")
```

```
 df <- read.csv("C:/Users/jihyeonpark/Desktop/df.csv")
> df
  dept score
1   sw   100
2   sw    99
3   sw   100
4   sw    88
5 comp   100
6 comp    99
7 comp   100
8 comp   100
9 comp    89
> df1 <- read.csv("C:/Users/jihyeonpark/Desktop/1.csv")
> df1
  name dept nation n1 price
1    a    k  korea 10  1000
2    b    k  korea 20  2000
3    a    k  korea 30 90000
4    a    k  korea 50  1100
```

## Save as new csv file

<aside>
💡 An error occurred when I wrote the code below. At first, I thought an error occurred because the \ escape was not processed, but that was not the case, and the df and df1 objects I wanted to use were not created in the Environment.

</aside>

```r
stu <- data.frame(name=c('kim', 'lee', 'oh'), dept=c('sw', 'com', 'sw'))
df <- read.csv("C:/Users/jihyeonpark/Desktop/test/df.csv")
df1 <- read.csv("C:/Users/jihyeonpark/Desktop/test/1.csv")

# df1 객체를 ttt1 cvs 파일로 저장한다는 뜻
# row.names = F: 행 이름을 포함하지 않고 파일 저장 
write.csv(df1, "C:/Users/jihyeonpark/Desktop/test/ttt1.csv", row.names=F)
```
![스크린샷 2024-07-25 102655](https://github.com/user-attachments/assets/d595ad17-36d3-4f26-b72d-f833ee540ee8)

```r
stu <- data.frame(name=c('kim', 'lee', 'oh'), dept=c('sw', 'com', 'sw'))
df <- read.csv("C:/Users/jihyeonpark/Desktop/test/df.csv")
df1 <- read.csv("C:/Users/jihyeonpark/Desktop/test/1.csv")

# df 객체를 ttt cvs 파일로 저장한다는 뜻
# row.names = T: 행 이름을 포함하고 파일 저장
write.csv(df, "C:/Users/jihyeonpark/Desktop/test/ttt.csv", row.names=T)
```

![스크린샷 2024-07-25 102722](https://github.com/user-attachments/assets/190507f8-6efb-4fc1-8798-75b5f9b8c1af)

---

# **stu Object Utilization**

```r
stu <- data.frame(name=c('kim', 'lee', 'oh'), dept=c('sw', 'com', 'sw'))
```

```
> stu <- data.frame(name=c('kim', 'lee', 'oh'), dept=c('sw', 'com', 'sw'))
> stu
  name dept
1  kim   sw
2  lee  com
3   oh   sw
```

## Print only specific columns or rows

**In the console `stu[position of desired row, position of desired column]`** → The relevant(해당) data is output

```
> stu[1, 1]
[1] "kim"
```

### First row output

```
> stu[1,]
  name dept
1  kim   sw
```

### Only ‘sw’ student output in dept

$ : specific column

```
> stu[stu$dept=='sw',]
  name dept
1  kim   sw
3   oh   sw
```

### Only ‘com’ student output in dept

```
> stu[stu$dept=='com',]
  name dept
2  lee  com
```

## Add specific column to object

```
> stu$score<-c(100, 99, 100)
> stu
  name dept score
1  kim   sw   100
2  lee  com    99
3   oh   sw   100
```

## Remove specific column to object

```
> stu$score<-NULL
> stu
  name dept
1  kim   sw
2  lee  com
3   oh   sw
```

---

# Add num(학번) to df object

```
> df$num<-c(10, 20, 30, 40, 50, 60, 70, 80, 90)
> df
  dept score num
1   sw   100  10
2   sw    99  20
3   sw   100  30
4   sw    88  40
5 comp   100  50
6 comp    99  60
7 comp   100  70
8 comp   100  80
9 comp    89  90
```

---

# Data Analyze with dplyr

## Install packages

```
install.packages("패키지이름")
library(패키지이름)
```

## **Selecting specific columns using the chain function**

```
> df1 %>% select(name)
  name
1    a
2    b
3    a
4    a
```

```
> df1 %>% select(name, dept)
  name dept
1    a    k
2    b    k
3    a    k
4    a    k
```

## Filter to specific row

```
> df1 %>% filter(name=='a')
  name dept nation n1 price
1    a    k  korea 10  1000
2    a    k  korea 30 90000
3    a    k  korea 50  1100
```

### Select only name whose price is 1,000 won or more

```
> df1 %>% filter(price>1000) %>% select(name)
  name
1    b
2    a
3    a
```

### **Name it group_by and find the n1 average to summarize**

```
> df1 %>% group_by(name) %>% summarise(mean(n1))
# A tibble: 2 × 2
  name  `mean(n1)`
  <chr>      <dbl>
1 a             30
2 b             20
```

a Person’s average is 30, b Person’s average is 20

---

# Assignment

Read the files you use at work and be sure to apply dplyr


```r
s1 <- read.csv("/Users/parkjihyeon/Desktop/R/special-lecture/SeoulNationalsbyInflowPoint.csv")
```

When using the above code, the following error occurs. This occurs due to an encoding problem in the csv file. There are several ways.

## Error Solution

### Read files by specifying encoding

```r
# UTF-8 인코딩으로 파일 읽기
s1 <- read.csv("/Users/parkjihyeon/Desktop/R/special-lecture/SeoulNationalsbyInflowPoint.csv", fileEncoding = "UTF-8")
```

### To use reader package

```r
# readr 패키지 설치 (한 번만 설치하면 됩니다)
install.packages("readr")

# readr 패키지 로드
library(readr)

# read_csv 함수 사용하여 파일 읽기
s1 <- read_csv("/Users/parkjihyeon/Desktop/R/special-lecture/SeoulNationalsbyInflowPoint.csv")
```

### **I kept getting an error, but it was resolved by doing the following.**

```r
s1 <- read.csv("/Users/parkjihyeon/Desktop/R/special-lecture/SeoulNationalsbyInflowPoint.csv", fileEncoding = "EUC-KR", encoding = "EUC-KR")
```

## **Print only when the customer address is Songpa-gu and the number of card uses is 50 or more.**

```r
> s1 %>% filter(카드이용건수계 >= 50, 고객주소시군구 == "송파구") %>% select(고객주소시군구)
  고객주소시군구
1         송파구
2         송파구
```

```r
> s1 %>% filter(카드이용건수계 >= 50, 고객주소시군구 == "송파구") %>% select(고객주소시군구, 카드이용건수계)
  고객주소시군구 카드이용건수계
1         송파구             69
2         송파구            764
```

# [02. Visaulize data with an example](https://velog.io/@gulbi/Special-lecture02.-Visualize-data-with-an-example)
# Install ggplot2 package

```r
install.packages("ggplot2")
library(ggplot2)
```

## iris → too many data so check the structure to use str()

5 column and 150 row

```
> str(iris)
'data.frame':	150 obs. of  5 variables:
 $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
 $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
 $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
 $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
 $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...
```

## **Using head(), I can check only the first few data**

```
> head(iris)
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
5          5.0         3.6          1.4         0.2  setosa
6          5.4         3.9          1.7         0.4  setosa
```

### Write x, y and using geom_point()

```
> ggplot(data=iris, aes(x=Sepal.Length, y=Sepal.Width)) +
+ geom_point()
```

![스크린샷 2024-07-25 102943](https://github.com/user-attachments/assets/8304bd60-ebcc-49eb-9a58-522e46451bc2)

<aside>
💡 what is geom_point()?
: This is a function provided by the gglot2 package and is used when creating a scatter plot. It displays each data point individually(개별적으로) and is useful for visually representing(나타내는데) the relationship between two variables.
In other words, you can create various visualizations by adjusting(조절하여) the location, color, size, and shape of the points with a function that creates a scatterplot. It is very useful for visually understanding the distribution(분포) of data and the relationships between variables.

</aside>

<aside>
💡 What is aes()?
: This is a function that sets the ‘aesthetic mapping(미적 매핑)’ used when drawing graphs in the ggplot2 package. It plays a role in mapping the visual properties(속성) of the graph using the variables in the data frame.
For example, you can specify the values of the x and y axes, the color, size, and shape of the points, etc.

</aside>

## Specify color

Since there are a total of 3 species, colors are classified into 3 categories.

```r
> ggplot(data=iris, aes(x=Sepal.Length, y=Sepal.Width, color=Species))+
+ geom_point()
```

![스크린샷 2024-07-25 103026](https://github.com/user-attachments/assets/1d81dc9c-e746-4e42-8049-d1617886c46e)

---

# Box Plot

You can identify above average, below average, etc.

```
> ggplot(data=iris, aes(x=Species, y=Sepal.Length)) +
+ geom_boxplot()
```

![스크린샷 2024-07-25 103057](https://github.com/user-attachments/assets/41ddff7a-e7c2-4bec-a6ea-34ed9742d578)

---

# theme_minimal()

With the theme function, it simplifies the background and style of the graph with minimal elements. Used to set the appearance of the graph to a predefined style.

```
> ggplot(data=iris, aes(x=Sepal.Length, y=Sepal.Width, color=Species))+
+ geom_point()+
+ theme_minimal()
```

![스크린샷 2024-07-25 103114](https://github.com/user-attachments/assets/af6f3ca1-9071-4493-8fa7-f3d712b1340d)

---

# Assignment

x: n1

y: price

color : name

```
> ggplot(data=df, aes(x=n1, y=price, color=name))+
+ geom_point()+
+ theme_minimal()
```

![스크린샷 2024-07-25 103133](https://github.com/user-attachments/assets/14cccb3b-63a0-4404-bfba-b038f09f898a)
