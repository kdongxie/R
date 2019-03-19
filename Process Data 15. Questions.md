### mpg : ggplot2 의 내제 Data

library(ggplot2)

df <- as.data.frame(mpg) **<u># data.frame의 형태로 type 강제변환</u>**

class(df) **<u># type 출력</u>**

head(df) **<u># 상위 6개 출력</u>**

tail(df) **<u># 하위 6개 출력</u>**

summary(df) **<u># Data 요약</u>**

colnames(df) **<u># Data columns 의 이름을 출력</u>**

 

### dplyr package를 이용한 Data 처리

install.packages("dplyr") **<u># dplyr 를 설치</u>** 

library(dplyr) **<u># dplyr 를 사용하겠다는 선언</u>**

data <- rename(data, city = cty) **<u># colname을 변경하기</u>**

data <- rename(data, hightway = hwy) **<u># colname을 변경하기</u>**

colnames(data)

### 문제

#### 통합 연비를 구해서 히스토그램으로 출력 하시오

##### (cty + hwy) /2 평균 연비를 구하는 공식

total <- data$city + data$hightway

total_mean <- total /2

toal_mean **<u>#평균 연비</u>**

 

df2<-data.frame(data, total_mean)

head(df2)

library(ggplot2)

qplot(total_mean, binwidth=2, geom = "histogram")

hist(total_mean)

qplot(data =df2, x = manufacturer, y=total_mean, geom = "boxplot", colour=manufacturer)

\##############################################################

### 문제 2

##### 다음의 등급을 정의하여 빈도수를 출력하시오

##### 등급 Total 기준

#####   A   30 이상 ~ 40 이하

#####   B   20 이상 ~ 30 이하

#####   C   10 이상 ~ 20 이하

#####   D   0 ~ 10 이하하

 

total <- data$city + data$hightway

total_mean <- total /2

toal_mean

valuse <- list()

for (i in c(1:length(total_mean))){

  if (total_mean[i] >0.0 & total_mean[i] <= 10.0){

​    total_mean[i] <- "D"

  } else if (total_mean[i] >10.0 & total_mean[i] <= 20.0){

​    total_mean[i] <- "C"

  } else if (total_mean[i] >20.0 & total_mean[i] <= 30.0){

​    total_mean[i] <- "B"

  } else if (total_mean[i] >30.0 & total_mean[i] <= 40.0){

​    total_mean[i] <- "A"

  } 

}

total_mean

qplot(total_mean)

\##############################################################

### if문을 한번에 작성하여 조건을 걸어주기.

library(ggplot2)

class(mpg)

data <- as.data.frame(mpg)

colnames(data)

data$total <- (data$cty + data$hwy) / 2

\#data$total 

data$level <- ifelse(data$total >= 30 & data$total < 40,

​                     "A", 

​                     ifelse(data$total >= 20 & data$total < 30, 

​                            "B",

​                            ifelse(data$total >= 10 & data$total < 20,

​                                   "C", "D"

​                            )))

 

data$level

library(ggplot2)

qplot(data$level)

\##############################################################

### if문을 한번씩 조건을 걸어주기.

test <- function(total){

  level <- ""

  if(total >= 30 & total < 40) {

​    level = "A"

  } else if(total >= 20 & total < 30){

​    level = "B"

  } else if(total >= 10 & total < 20){

​    level = "C"

  } else {

​    level = "D"

  }

  return(total)

}

 

data$level <- test(data$total)

 

\###########################################################

### 문제 3

#### 전체 인구대비 아시아 인구 백분율 => 히스토그램으로 출력 

colnames(data2)

asian = (data2$popasian / data2$poptotal) * 100

library(ggplot2)

qplot(asian, binwidth = 1,geom = "histogram")

 