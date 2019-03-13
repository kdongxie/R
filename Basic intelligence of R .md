# 기본적인 원소Type

### Vector object [객체]

#### 1. logical [TRUE, FLASE]

v1 <- TRUE

print(class(v1))

 

#### 2. Numeric

v2 <- 12.5

print(class(v2))

 

#### 3. Integer

v3 <- 10L

print(class(v3))

 

#### 4. Complex

v4 <- 23 + 3i

print(class(v4))

 

#### 5. Charactor

v5 <- "Hi"

print(class(v5))

 

#### 6. Raw

v6 <- charToRaw("Test")

print(class(v6))

 

**<u># R-object == Vectors 라고 생각하면 됨.</u>**

 

<u>**# < DataType >**</u> 

<u>**\#   Vectors**</u>

<u>**\#   Lists**</u>

<u>**\#   Matrics**</u>

<u>**\#   Arrays**</u>

<u>**\#   Data Frames**</u>

 

### Vectors 설정

apple <- c('red','yellow','green')

print(apple) **<u>#character</u>**

a <- c(1,2,3,4)

class(a) **<u>#numeric</u>**

a1 <- "test"

class(a1) **<u>#character</u>**

a2 <- 2

class(a2) **<u>#numeric</u>**

a3 <- 2L

class(a3) **<u>#integer 숫자 뒤에 L을 붙이면 integer로 선언이 된다</u>**

a <- c(1,2,3,4)

class(a) **<u>#numeric</u>**

 

### Lists

list1 <-list(c(1,2,3),c(4,5,6),c(7,8,9))

class(list1) **<u>#list</u>**

list2 <- list(1,2)

class(list2) **<u>#list</u>**

#### List에 Function 을 집어 넣기

list1 <-list(c(1,2,3),c(4,5,6),c(7,8,9), sin)

list1

[[1]]

[1] 1 2 3

 

[[2]]

[1] 4 5 6

 

[[3]]

[1] 7 8 9

 

[[4]]

function (x)  .Primitive("sin")

 

 

### Matrixs

m <- matrix(c("a","b","c","d","a","b"),

​            nrow = 2,

​            ncol = 3)

m **<u># 세로로 순차적으로 입력된다.</u>** 

**<u># 출력값:</u>** 

```
[,1] [,2] [,3]
[1,] "a"  "c"  "a" 
[2,] "b"  "d"  "b" 
```

 

### Arrays

arr <- array(c('yellow','red'), dim = c(3,3,1))

arr **<u># 3X3의 Table이 형성</u>** 

**<u># 출력값 :</u>**

```
, , 1
 
     [,1]     [,2]     [,3]    
[1,] "yellow" "red"    "yellow"
[2,] "red"    "yellow" "red"   
[3,] "yellow" "red"    "yellow"
```

 arr2 <- array(c('yellow','red'), dim = c(3,3,2))

arr2 **<u># 3X3의 Table이 형성</u>**

**<u># 출력값 :</u>**

```
, , 2
 
     [,1]     [,2]     [,3]    
[1,] "red"    "yellow" "red"   
[2,] "yellow" "red"    "yellow"
[3,] "red"    "yellow" "red" 
```

 

### Factors [Distinct]

apple_colors <- c('green','yellow','red','red',

​                  'green','green','red')

apple_colors

**<u>#출력 값:</u>**

```
[1] "green"  "yellow" "red"    "red"    "green"  "green"  "red"
```

factor_apple <-factor(apple_colors)

factor_apple

**<u>#출력 값:</u>**

```
[1] green  yellow red    red    green  green  red   
Levels: green red yellow
```

print(nlevels(factor_apple)) **<u>#factor(Distinct)된 값의 개수를 출력함</u>**

**<u>#출력 값:</u>**

```
[1] 3
```

 

### DataFrame

test_data <- data.frame(gender = c("Male",'Female','Male'),

​                        hight = c("170",'180','155'),

​                        weight = c("75",'90','55'),

​                        age = c('40','25','45'))

test_data

**<u>#출력 값: (DataFrame의 형태)</u>**

```
gender hight weight age
1   Male   170     75  40
2 Female   180     90  25
3   Male   155     55  45
```

 

### DataTable

**<u>#install.packages("data.table")</u>**

library(data.table) **<u>#Package를 사용하겠다는 신호</u>**

test_table <- data.table(gender = c("Male",'Female','Male'),

​                        hight = c("170",'180','155'),

​                        weight = c("75",'90','55'),

​                        age = c('40','25','45'))

test_table

**<u>#출력 값: (DataTable의 형태)</u>**

```
gender hight weight age
1:   Male   170     75  40
2: Female   180     90  25
3:   Male   155     55  45
```

 

**<u># data.table 을 사용하기 위해서는 Package가 필요하다.</u>**

 

### Strings

data <- "test"

data **<u>#(OK)</u>**

data2 <- "test"

data2 **<u>#(OK) / 같은 값을 변수로 지정 가능함</u>**

data3 <- "test' **<u># " " 을 잘 묶어야 함</u>** 

data3 **<u>#(Disable)</u>**

 

### Paste [합치기]

data1 <- "Hello"

data2 <- "good"

data3 <- "Good bye"

data4 <- cat(data1,data2,data3)

data4 **<u>#출력 값:</u>**

```
Hello good Good bye
```

data5 <- paste(data1,data2,data3)

data5 **<u>#출력 값:</u>** 

```
"Hello good Good bye"
```

data6 <- paste(data1,data2,data3,sep = "-")

data6 **<u>#출력 값: - 으로 나누기</u>**

```
"Hello-good-Good bye"
```

 

### format

format(120.12222222,digits = 4) **<u># 소수점을 제외한 나머지 4자리 까지 출력 : 120.1</u>**

format(120.2200000, scientific = TRUE) # 

```
[1] "1.2022e+02"
```

format(14.7,width = 10) **<u># 전체 폭이 10칸 인 상태로 정렬 default 값은 오른쪽</u>**

```
[1] "      14.7"
```

format("Test",width = 10, justify = "c") **<u># 가운데 정렬 "c"</u>**

```
[1] "   Test   "
```

format("Test",width = 10, justify = "r") **<u># 오른쪽 정렬 "r"</u>**

```
[1] "      Test"
```

format("Test",width = 10, justify = "l") **<u># 왼쪽 정렬 "l"</u>**

```
[1] "Test      "
```

 

### substring

data7 <- "This is mine good morning"

data7

```
[1] "This is mine good morning"
```

substring(data7,2,4) **<u># 인덱스를 이용하여 출력 / 출력 값 : his / 인덱스는 1부터임</u>**

```
[1] "his"
```