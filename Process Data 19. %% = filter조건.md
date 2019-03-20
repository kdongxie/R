# %>% <= filter조건 

attach(df)

df[which(class==1),]

##### #위의 작성이 불편하다. 아래의 작성법을 사용하자.

df %>% filter(class ==1)

df %>% filter(class ==2)

df %>% filter(math > 50)

pass <- df %>% filter(class !=1 & math > 60 & science > 60 & english >60)

library(ggplot2)

attach(df)

tmp_data <- as.data.frame(df)

tmp_data

tmp_data %>% filter(class <=4 | math > 50)

df %>% filter(class %in% c(1,2))

df %>% select(math) %>% filter(math > 50)

 

### ggplot2::mpg

library(ggplot2)

df4 <- ggplot2::mpg # 내제 Data 초기화 하기 방법 

df5 <- as.data.frame(df4)

df6 <- df5 %>% select(cty,class) #column 선택 Select 를 사용한다.

df5 %>% arrange(class,cty) # 선택 조건에 따라 정렬하기 default 값은 오름차순

df5 %>% arrange(desc(class)) # 내림차순으로 정렬하기 

 

head(df5 %>% filter(manufacturer == "audi") %>% arrange(desc(hwy)))



### filter 적용과 arrange 를 이용한 정렬 

 

#### #df$test <- "test" : col 네임 정의 해주기

#### #filtering 과 함께 새로운 Column 을 생성해주기 : mutate / 변수를 받아주어야 함 

df6 <- df5 %>% mutate(total = (hwy + cty)/2) %>% head()

str(df6)

df6 %>% mutate(mean = total / length(total))

 

### summary 요약하기 : 특정 건에 대해 grouping하여 출력

df5 %>% summarise(hwy_mean = mean(hwy))

 

### Group BY 를 이용한 Grouping

df7<- df5 %>% group_by(class) %>% summarise(hwy_mean = mean(hwy), class_max = max(hwy), class_min = min(hwy))

df7

 

df5 %>% group_by(class) %>% summarise(count=n())

 

<u>**# mean() = 평균**</u>

<u>**\# str() = 표준편차**</u>

<u>**\# median() = 중간값**</u>

<u>**\# min() = 최소값**</u>

<u>**\# max() = 최대값**</u>

<u>**\# n() = 빈도**</u>


 

 

### 문제

#### #회사별, SUV 자동차의 도시 및 고속도로 통합 연비 

#### #평균을 구하고 내림차순으로 정렬하고 ,~위부터 5위까지 출력하시오 

 

library(ggplot2)

df8 <- ggplot2::mpg # 내제 Data 초기화 하기 방법 

df9 <- as.data.frame(df8)

str(df9)

 

df9 %>% filter(class == 'suv') %>%  **<u># SUV filtering</u>**

  select(manufacturer,cty, hwy, class ) %>% **<u># 뽑아낼 Column</u>**

  group_by(manufacturer) %>% **<u># 그룹핑</u>** 

  mutate(total = (hwy + cty)/2) %>% **<u># 새로운 Column 생성</u>**

  summarise(total_mean = mean(total)) %>% **<u># 평균값을 하나의 객체로 출력</u>**

  arrange(desc(total_mean)) %>% **<u># 배열하는 방법</u>**

  head(5) **<u># 상위 5개만을 출력</u>**

***** 위의 풀이는 한줄로 이루어진 쿼리문으로 %>% 로 Data가공을 순차적으로 진행한다.

