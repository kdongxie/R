# Data Frame

height <- c(160,170,190,179)

weight <- c(48,73,90,56)

gender <- c("male","female","male","female")

df <- data.frame(height,weight,gender, stringsAsFactors = FALSE) 

**<u># stiringsAsFactors 의 조건을 두어 type설정, default 값은 Factor로 정의된다.</u>**

df$height **<u># $까지 입력하면 column의 이름들이 뜨며 선택하여 출력 가능</u>**

**<u># 이름을 바꾸고 싶을 때는 names()함수를 사용한다.</u>**

class(df)

is.factor(df$gender)

df$gender

 



 

