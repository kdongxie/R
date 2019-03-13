# Lists => Container

 

List_data <- list("apple",10,c(1,2,3),TRUE)

List_data **<u># 안의 요소가 어떠한 형태이던지 List로써 만들 수 있다.</u>**

<u>**\# Index를 네이밍을 하는 법 name()의 함수를 이용</u>**

names(List_data) <- c('one','two','three','four') 

List_data **<u># 인덱스의 값이 설정 값으로 출력 됨</u>** 

<u>**# 출력 값: 설정한 이름의 인덱스 값을 가져오게 된다)**</u>

<u>**# LIst_data$one**</u>

[1] "apple"

**<u>List_data[1]</u>**

[1] "apple"

 

**<u># Multiple List</u>**

list_data3 <- list("apple",

​                   matrix(c(4,3,2,1,0,1), nrow = 2),

​                   10,c(1,2,3),TRUE)

names(list_data3) <- c('one','two','three','four','five')

list_data3$two **<u>#matrix의 값을 출력</u>**

 

<u>**# 리스트의 원소 값을 변경하는 방법**</u>

list_data3$one <- "orange" **<u>#Index 값에 원소 값을 덮어 씌우면 된다.</u>**

 

\# 리스트 안의 원소 값을 삭제하는 법

list_data3$three <- NULL

list_data3 **<u>#index three의 값이 사라짐</u>**

 

**<u># 새로운 Index와 원소의 값을 추가하는 법</u>**

list_data3[6] <- "tomato"

list_data3 **<u># Index값이 6이고 tomato라는 원소 값을 갖게 된다.</u>**

 

**<u># Merging</u>**

list_data4 <- list("홍길동","이순신")

list_data5 <- list("권율","이성계")

list_data6 <- c(list_data4 , list_data5)

list_data6 # 두개의 List를 하나로 합친다

 

**<u># List를 Vector로 바꾸기 -> unlist를 사용</u>**

vector_data6 <- unlist(list_data6)

vector_data6 **<u># Vector Type인 character type으로 바뀌게 된다.</u>**

\<u>**#출력 값: "홍길동" "이순신" "권율"   "이성계"</u>**

vector_data6[1] **<u># 출력 값: "홍길동"</u>**