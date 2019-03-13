# DataType 1. Vector

### Vector Type의 종류

data8 <-"343" ***<u>#character</u>***

data9 <- 1 ***<u>#Numeric</u>***

data10 <- 3L ***<u>#Integer</u>***

data11 <- 1:10 ***<u>#Integer</u>***

data12 <- seq(5,9, by = 1) **<u>*# 5부터 9까지 1만큼 증가</u>***

data13 <- seq(9,5, by = -0.5) ***<u># 9부터 5까지 0.5만큼 감소</u>***

data14 <- seq(5,9, by = -1) ***<u># 실행이 되지 않는다</u>***

data15 <- c("apple",1000,TRUE) ***<u># character</u>***

 

#### Index에 해당되는 값을 출력하기

data16 <- c(1,2,3,4,5)

data16[1] **<u># 인덱스 값은 1부터  / 출력 값: 1</u>**

 

#### Index를 이용한 예제 

data17 <- c("sun","mon",'tue','wed','Thr','fri','sat')

data17[1] **<u>#출력 값: sun</u>**

data17[2] **<u>#출력 값: mon</u>**

<u>data17[c(2,4)] **#출력 값: mon, wed**</u>

<u>data17[2:4] **#출력 값: mon, tue, wed**</u>

data17[-1] **<u># 지정 인덱스를 제외하고 나머지 출력</u>**

data17[-2]

data17[c(-2,-3)] **<u># 출력 값: "sun" "wed" "Thr" "fri" "sat"</u>**

data17[-2:-4] **<u>#출력 값: "sun" "Thr" "fri" "sat"</u>**

data18 <- data17[c(TRUE,FALSE,TRUE,FALSE,FALSE,TRUE,FALSE)] **<u># TRUE 의 값으로 설정</u>**

data18 **<u># 출력 값:  "sun" "tue" "fri" FALSE 값은 출력되지 않음</u>**

 

 

 

#### 두개의 Vector를 연산하기

data19 <- c(1,2,3)

data20 <- c(3,4,5)

data19 + data20 **<u>#출력 값: 4 6 8</u>**

 

data21 <-c(1,2,3,4,5)

data22 <-c(1,2)

data21 + data22 

\<u>**#출력 값: 2 4 4 6 6 (작은 쪽을 순차적으로 계속 돌려서 연산하게 된다)</u>**

 

#### Sort

data22 <- c(1,5,23,47,3,7,9,5,4)

sort.result <- sort(data22)

sort.result 

**\# default 값으로 오름차순으로 정렬됨**

**<u># 출력 값: 1  3  4  5  5  7  9 23 47</u>**

sort.result1 <- sort(data22,decreasing = TRUE)

sort.result1 

<u>**\# 정렬 값을 내림차순으로 정렬하는 법 Decending 이 아님 decreasing 임**</u>

<u>**\# 출력 값: 47 23  9  7  5  5  4  3  1**</u>
