# Data를 호출하여 출력

df2 <- read.csv("seoul.csv",

​                fileEncoding = 'utf-8',

​                header = TRUE,

​                sep = ',',

​                stringsAsFactors = FALSE)

<u>**#View(df2)**</u> **<u># 입력된 CSV 파일을 출력해준다.</u>**

<u>**\#str(df2$날짜)**</u> **<u># CSV파일의 데이터 중 "날짜" Column 을 호출 한다.</u>**

 

### Data를 가지고 Summary함수 이용하기

emp_data <- data.frame(emp_id =c(1:3),

​                       emp_name = c("홍길동","이순신","강감찬"),

​                       salary = c(100,200,300),

​                       start_data = c('2018-10-10','2018-10-12','2018-10-12'),

​                       stringsAsFactors = FALSE)

emp_data

<u>**# 출력 값:**</u>

<u>**\# emp_id  emp_name    salary    start_data**</u>

<u>**\# 1       1   홍길동    100       2018-10-10**</u>

<u>**\# 2       2   이순신    200        2018-10-12**</u>

<u>**\# 3       3   강감찬    300        2018-10-12**</u>

summary(emp_data) 

<u>**\# 출력 값:**</u>

<u>**\# emp_id       emp_name          salary            start_data**</u>       

<u>**\# Min.   :1.0    Length:3            Min.   :100      Length:3**</u>          

<u>**\# 1st Qu.:1.5    Class :character      1st Qu.:150       Class :character**</u>  

<u>**\# Median :2.0   Mode  :character    Median :200      Mode  :character**</u>  

<u>**\# Mean   :2.0                       Mean   :200**</u>                     

<u>**\# 3rd Qu.:2.5                        3rd Qu.:250**</u>                     

<u>**\# Max.   :3.0                        Max.   :300**</u>

<u>**\# Summary를 이용하여 각 항목에 대한 정보를 출력**</u>

 