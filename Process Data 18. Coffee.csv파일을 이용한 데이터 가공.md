# Coffee.csv파일을 이용한 데이터 가공

df <- read.csv("coffee.csv", encoding = "utf-8", stringsAsFactors = F)

### 2000년도 이후 폐업된 매장의 정보를 출력하시오.

 

sub_df2 <- subset(df,df$stateOfbusiness =="폐업 등" & dateOfclosure >=20010101, select=(c(companyName, dateOflicensing,stateOfbusiness)))

dim(sub_df2)

plot(sub_df2)

sub_df3 <- subset(df,df$stateOfbusiness =="폐업 등" & df$yearOfStart >=2000, select=(c(dateOflicensing,stateOfbusiness)))

sub_df3

df[which(df$stateOfbusiness=="폐업 등" & df$yearOfStart >"2000"),]

 

### 전국 커피숍 데이터 에서 연도별 개업 수

table(df$yearOfStart)

 

### 전국 커피숍 데이터 에서 연도별 폐업 수

sub_year<-subset(df,df$stateOfbusiness == "폐업 등", select= c(yearOfStart,stateOfbusiness))

plot(table(sub_year),geom = "liner")

 