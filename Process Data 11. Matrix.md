# Matrix 

#### Matrix 생성

city <- c('seoul', 'japan', 'newyork', 'beijing')

state <- c('a', 'b', 'c', 'd')

address <- c(1111,2222,3333,4444)

home <- c(101,202,303,404)

tmp_data <- cbind(city, state, address, home) **<u># cbind</u>** : Column 기준으로 묶기

tmp_data

class(tmp_data) **<u>#matrix</u>**

df1 <- data.frame(tmp_data) **<u>#data.frame 으로 형변환</u>**

class(df1) **<u>#data.frame</u>**

 

tmp_data2 <- data.frame(

city = c('seoul', 'japan', 'newyork', 'beijing'),

state = c('a', 'b', 'c', 'd'),

address = c(1111,2222,3333,4444),

home = c(101,202,303,404),

stringsAsFactors = F

)

tmp_data2

class(tmp_data2) **<u>#data.frame</u>**

**rbind**(tmp_data, tmp_data2) **<u># data.frame끼리 묶기</u>** : Row 기준으로 묶기

 

colnames(tmp_data2) **<u># column 명을 출력</u>**

rownames(tmp_data2) **<u># row 명을 출력</u>**

dimnames(tmp_data2) **<u># row명과 column명을 출력</u>**

dim(tmp_data2) **<u># data.frame의 차원 수를 출력해준다</u>**

str(tmp_data2) **<u># data.frame의 내용을 요약하여 출력해 준다</u>**

tmp_data2$state <- factor(tmp_data2$state)

str(tmp_data2)

 

### Make Function

seq(1,10)

mean(1:10)

sum(1:10)

 

<u>**# 사용자에 의하여 정의되는 함수**</u> 

<u>**\# 함수 1 – 출력**</u>

myfunc <- function(a){

  print(a)

}

myfunc("b")

**<u># 함수 2 – 합</u>**

myfunc2 <- function(a){

  sum <-0

  for( i in 1:a){

​    sum = sum + i

  }

  print(sum)

}

myfunc2(100)

\#rm(list=ls())

 

**<u># 함수 3 – 두 변수의 합</u>**

myAdd <- function(a,b){

  c<-a+b

  print(c)

}

myAdd(3,4)

 

**<u># 함수 4 – 고정 출력 함수</u>**

myAdd2 <- function(){

  c<- 1+2

  print(c)

}

myAdd2()

 

**<u># 함수 5 – 우선 선언된 두 변수의 합 함수</u>**

myAdd3 <- function(a=1,b=2){

  c = a+b

  print(c)

}

myAdd3

myAdd3(a=2,b=4)

myAdd3(3,3)

 

**<u># 함수 6 – 두 변수의 합 함수를 호출하기</u>**

myAdd <- function(a,b){

  c <- a+b

  return(c)

}

r <- myAdd(1,2)

print(r)

r2 <- myAdd()

print(r2)

r3 <- myAdd(2,3)

print(r3)

 

**<u>#함수 7 – 반복문을 갖는 함수 설정</u>**

tmp_v_sum = function(myv){

  sum <-0

  for(i in myv){

​    sum=sum+i

​    print(sum)

  }

  return(sum)

}

tmp_v= c(1,2,3,4)

print(tmp_v)

 

r5 <- tmp_v_sum(tmp_v)

print(r5)

 


 

 

### 다음 그림을 출력하시오.

\# n <- 10

\#

\##

\###

\####

\#####

\######

\#######

\########

\#########

\##########

 

display <- function(n){

  for(i in 1:n){

  print((paste(rep("$",times=i),collapse = "")))

  }

}

display(10)

 

## Apply계열 함수 -> matrix 의형태

### apply(X , margin , function) 의 Syntax를 갖는다.

### # X 안에는 matrix or Dataframe의 형태로 들어가면 된다.

m_data <- matrix(c(1,2,3,4,5,6,7,8,9) , nrow = 3 , ncol = 3)

apply(m_data, 1, sum) **<u># row를 기준으로 하여 합</u>**

apply(m_data, 2, sum) **<u># col을 기준으로 하여 합</u>**

apply(m_data, 2, mean) **<u># col을 기준으로 하여 평균값</u>** 

 

<u>**#lapply / 반환값이 list의 형태**</u> 

<u>**\#lapply(X,function)**</u> 

tmp_data <-c('a','b','c','d')

lapply(tmp_data,toupper) **<u># list의 형태로 출력 되며, toupper로 인해 대문자로 출력</u>**

tmp_data2 <- list(a=1:10,b=1:20)

tmp_data2

lapply(tmp_data2,mean)

 

<u>**#sapply / 반환값이 matrix의형태**</u>

<u>**\#sapply (X, function)**</u> 

sapply(tmp_data2,mean)

 

<u>**#mapply / 반환값이 vector의 형태 (sapply의 multiple버젼)**</u>

<u>**\#mapply (function, X, Y) # mapply는 함수의 위치에 주의해야한다.**</u> 

tmp_data3 <- list(a=1:10,b=1:20,c=1)

tmp_data4 <- list(a=2:10,b=2:20,c=2)

tmp_data5 <- list(a=3:10,b=3:20,c=3)

mapply(sum,tmp_data3,tmp_data4,tmp_data5)

 

#### 사용자정의 Function을 가지고 sapply에 적용하기

tmp_data6 <- list(a=1:10,b=1:20)

tmp_data6

testFunc <- function(x){

  (min(x) + max(x)) / 2

}

tmp_data7 <- sapply(tmp_data6, testFunc)

tmp_data7

 

#### tapply 

head(warpbreaks) **<u># warpbreaks 라는 기본 내장함수가 있음 (기본 dataframe을제공)</u>**

str(warpbreaks)

View(warpbreaks)

 

with(warpbreaks,tapply(breaks, list(wool,tension), mean))

**<u># tapply(vector, index, function) 의 syntax를 갖는다</u>**

View(iris)

tapply(iris$Sepal.Width , iris$Species , mean)

tapply(iris$Sepal.Length , iris$Species , mean)