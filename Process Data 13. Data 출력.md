# head(), tail(), View(), dim(), str(), summary()



##### Data.frame 을 만들고 함수이용하기 

english <- c(80,85,60,75)

math <- c(65,80,95,75)

class <- c(1,2,1,2)

df <- data.frame(english,math,class)

mean(df$english) **<u># english column의 평균 값</u>** 

mean(df$math) **<u># math column의 평균 값</u>** 

 

<u>**# 제품 가격 판매량  의 Data.Frame을 만들어라.**</u>

<u>**\# 사과 2000 20**</u>

<u>**\# 배   1500 30**</u>

<u>**\# 딸기 2000 40**</u>

<u>**\# 수박 9000 20**</u>

products <- c('사과','배','딸기','수박')

price <- c(2000,1500,2000,9000)

sales <- c(20,30,40,20)

df2 <- data.frame(products,price,sales)

mean(df2$price) **<u># 평균 값</u>**

mean(df2$sales) **<u># 평균 값</u>**

median(df2$price) **<u># Data의 중값 값</u>** 

summary(df2) **<u># Data의 요약</u>**

 

### 데이터를 읽어오기 

df3 <- read.csv("csv_exam.csv",encoding = "utf-8",stringsAsFactors = F)

df3

str(df3)

 

#### 새로운 csv파일 형태의 data set으로 만들어 준다

write.csv(df3,file='test_data.csv') 

#### 새로만든 data set을 load하도록 만들어준다

save(df3,file = "df2_data.rda") 

 

head(df3) **<u>#상위 6개만을 출력한다 default값</u>**

head(df3,10) **<u>#상위 10개를 출력</u>**

tail(df3) **<u>#하위 6개를 출력 default값</u>**

tail(df3,10) **<u>#하위 10개를 출력</u>**

dim(df3) **<u># dataframe의 차원 수를 나타내 준다. row수 / column수</u>**

str(df3) **<u># dataframe의 개요</u>**

summary(df3) **<u># 데이터의 요약 내용을 보여준다</u>**

 

### Typereverse : data를 쉽게 조작하기 위한 library

#### 명칭 : dplyr

##### install.packages('dplyr')

 

library(dplyr)

library(ggplot2)

 

df4 <- as.data.frame(mpg) **<u>#dataframe으로 강제 변환</u>** / **<u>mpg file은 dplyr의 기본 내장 data</u>**

class(df4) **<u>#dataFrame으로 형변환이 됨</u>**

df4$manufacturer **<u>#manufacturer 들의 내용이 출력</u>**

factor(df4[1]) **<u># manufacturer 의 Distinct 값을 보여준다</u>**

head(df4,3) **<u>#df4의 내용에서 3번째 열까지 출력해준다</u>**

 

df4$sum_test <- df4$hwy

colnames(df4)

qplot(df4$sum_test) **<u>#막대그래프로 나타내 줌</u>**

hist(df4$sum_test) **<u>#히스토그램으로 나타내 줌</u>**

 

