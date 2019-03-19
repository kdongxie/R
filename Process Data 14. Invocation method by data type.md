# CSV file 불러들이기

#### read.csv(("csv_exam.csv")) 

df<-read.csv("input_data.csv", fileEncoding = "utf-8", stringsAsFactors = F)

is.data.frame(df)

df$id **<u># $를 쓰기 위해서는 dataframe의 형태 또는 List의 형태에서 가능하다</u>**

df$salary **<u>#예시</u>**

max(df$salary) **<u>#예시</u>**

mean(df$salary) **<u>#예시</u>**

summary(df$salary) **<u>#예시</u>**

test <- subset(df,dept == "IT" & salary > 600) **<u># SQL 의 WHRER 조건과 같다.</u>** 

write.csv((test, "test.csv")) **<u>#가공된 데이터프레임을 csv로 변환하는 방법</u>**

 

# subset을 이용하여 데이터를 가공하는 방법 예제 

test2 <- subset(df, as.Date(start_date) > as.Date("2014-01-01") )

 

# Excel 파일을 읽을 수 있도록 해주는 Package

#### install.packages("xlsx") 

library(xlsx)

any(grepl("xlsx", installed.packages()))

df2 <- read.xlsx("input_data.xlsx", sheetIndex = 1)

 

# json 파일 읽을 수 있도록 해주는 Package

#### install.packages("rjson") 

library(rjson)

df3 <- fromJSON(file = "input_data.json")

class(df3) **<u>#list type</u>**

df3$Salary **<u># $ 사용가능</u>**

df4 <- as.data.frame(df3)

 