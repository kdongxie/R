##### rm(list=ls()) # 저장된 변수의 list 삭제

#### cancer.csv # csv file을 불러들이기

### 문제

##### 연령대 별로 임의 발생률을 구하고 그래프로 출력 하시오

##### 10s, 20s, 30s, 40s, 50s, 60s, 70s, 80s, 90, 100s

##### cut function 

##### 

### 풀이 1

tmp_data <- data.frame(

  age <- c(15,56,45,20,20)

)

tmp_data$age....c.15..56..45..20..20.

table(cut(tmp_data$age....c.15..56..45..20..20., breaks = (1:11)*10))

 

data<-read.csv("cancer.csv", encoding = "utf-8", stringsAsFactors = FALSE)

table_age <- cut(data$age,breaks = (1:11)*10) # 구간별로 나누기 

\#table_age <- cut(data$age,1:11*10) # break를 쓰지 않고도 조건을 줄 수 있다. 

plot(table_age)

class(data[1])

 

\##############################################################


 

 

### 풀이 2

tmp_data <- data.frame(

  age <- c(76, 75, 81, 76)

)

table(tmp_data)

 

checkAge <- function(age){

  \#print(age)

  if(age > 0 & age < 10) {

​    age = "10s" # 10s

  } else if(age >= 10 & age < 20) {

​    age = "10s" # 10s

  } else if(age <= 20 & age < 30) {

​    age = "20s" # 20s

  } else if(age <= 30 & age < 40) {

​    age = "30s" # 30s

  } else if(age <= 40 & age < 50) {

​    age = "40s" # 40s

  } else if(age <= 50 & age < 60) {

​    age = "50s" # 50s

  } else if(age <= 60 & age < 70) {

​    age = "60s" # 60s

  } else if(age <= 70 & age < 80) {

​    age = "70s" # 70s

  } else if(age <= 80 & age < 90) {

​    age = "80s" # 80s

  } else if(age <= 90 & age < 100) {

​    age = "90s" # 90s

  } else {

​    age = "100s"

  }

  \#print(age)

  return(age)

}

\#str(tmp_data2)

tmp_data3 <- ""

for (i in 1:length(tmp_data2$age)){

  tmp_data3 <- c(tmp_data3, checkAge(tmp_data2$age[i]))

}

 

str(tmp_data3)

tmp <- table(tmp_data3)

hist(tmp)