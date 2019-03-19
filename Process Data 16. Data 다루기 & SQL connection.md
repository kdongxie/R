#### #sorting #merging #aggregating #reshape #reshape package #subsetting #which #subset

# Sorting 하기

mtcars **<u># 내제 Data</u>**

\# attach(mtcars)  

**<u># attach를 사용하여 column을 사용할 때에 dataname 을 붙혀주지 않고 사용 가능하도록 해준다.</u>** 

df_car = mtcars

head(mtcars)

mtcars[,1]

colnames(mtcars) 

mtcars[order(mpg) , ] **<u># mpg을 기준으로 Sorting 하기</u>**

mtcars[order(mpg , cyl) , ] **<u># 두가지의 항목에 있어서 Sorting을 하고 싶을 때</u>** 

mtcars[order(-mpg , -cyl) , ] **<u># Decending 으로 Sorting 하고 싶을 때에는 "-"를 붙힌다</u>** 

 

# Merging하기

df1 <- data.frame(mtcars[1:10,],mtcars[11:20,]) **<u># data.frame을 기준으로 합치기</u>** 

 

# Aggregating : 

# 어떤것으로 GroupBy를 할 것 인가?

attach(mtcars)

aggregate(mtcars, by = list(cyl,vs),FUN = mean, na.rm = TRUE)

str(mtcars)

detach(mtcars)

 

# Reshaping : 

# T()를 이용하여 row와 col을 바꾸어 출력해준다.

mtcars

dim(mtcars)

tmp <- t(mtcars) #transpose

dim(tmp)

 

# Reshape Package 사용하기(무엇인가...? 좀더 공부하기)

 

tmp_data <- data.frame(

  id = c(1,1,2,2),

  time = c(1,2,1,2),

  x1 = c(5,3,6,2),

  x2 = c(6,5,1,4)

)

tmp_data

library(reshape2)

 

tmp_data2 <- melt(tmp_data, id=c("id"))

tmp_data2

tmp_data3 <- melt(tmp_data, id=c("id","time"))

tmp_data3

tmp_data

 

# Subsetting 

tmp_data4 <- c('La','la','bla')

tmp_data4[1]

tmp_data4[2]

paste(tmp_data4[1],tmp_data4[2],sep = "")

 

tmp_data5 <- c('a1','a2','a3')

names(tmp_data5) <- c("one","two","three")

tmp_data5[1]

tmp_data5['one']

tmp_data5[c(1,3)]

tmp_data5[c(-1,-2)]

tmp_data5[1:2]

 

# library(RMySQL)

 

mysqlconnection = dbConnect(MySQL(), dbname = 'employees', 

​                            user = 'hadoop', 

​                            password = 'Pa$$w0rd123',

​                            host = '192.168.137.100')

dbListTables(mysqlconnection) **<u># DB의 Table을 확인</u>**

 

result <- dbGetQuery(mysqlconnection, "SELECT * FROM employees")

df <- result

head(df)

df[1:10 , ]



# which : Index 값을 알아내는 방법

index <- which(df$gender=="F" $ df$emp_no < 10500) **<u># 조건에 맞는 Index값을 넣어서 출력하기</u>**

df[index , ]

 

# subset : 

# Data.Frame 에 직접 조건을 걸어서 출력하기 

table<-subset(df,df$gender =="F" & df$emp_no < 10050, select = c(emp_no,gender,first_name))

attach(table)

table

table[order("first_name"),]

 