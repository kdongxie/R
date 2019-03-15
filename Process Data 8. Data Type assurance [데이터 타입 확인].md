# Data Type assurance [데이터 타입 확인]

x1 <-8

is.numeric(x1) **<u>#TRUE</u>**

is.integer(x1) **<u>#FALSE</u>**

 

### Data Type 강제 변형

**<u># as.list() 는 Function 이기 때문에 변수를 받아야 함.</u>** 

**<u># 자체의 원본 데이터 타입은 변하지 않는다.</u>** 

**<u># 이유: 참조의 형태이기 때문이다 (Reference)</u>**

x2 <-as.integer(x1)

is.numeric(x2) **<u>#TRUE</u>**

class(x2) **<u>#integer</u>**

x5 <- 1:20

as.list(x5)

class(x5) **<u>#integer</u>**

x6 <- as.list(x5) **<u>#강제 형 변환 실시</u>**

class(x6) **<u>#list 출력</u>**

 