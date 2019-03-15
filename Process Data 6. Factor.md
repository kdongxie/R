# Factor == Distinct 와 같다고 보면 된다. 

<u>**#[중복 값들을 제거하고 출력해준다]**</u>

<u>**\#요인(factor)은 범주형 데이터를 표현하는데 사용된다. 요인은 순위를 가질 수도, 순위를 갖지 않을수도 있다. 요인은 통계적 분석과 도식화에 대한 중요한 클래스다.**</u>

<u>**\#요인은 정수로 저장되고, 유일무이한 정수와 연관된 표식을 갖는다. 요인은 문자벡터처럼 보이지만(흔히 행동한다), 실제로 내부를 보면 정수다. 문자열처럼 요인을 다룰 때, 주의를 기울일 필요가 있다.**</u>

<u>**\#요인이 생성되면, 요인은 수준(level)으로 알려진 사전에 정의된 집합값만 담을 수 있다. 기본 디폴트 설정으로, R은 항상 수준을 알파벳 순으로 정렬한다.**</u> 

 

**<u># Vector를 Factor로 변형 해준다.</u>**

data <- c("east","west","south","north","east","west","south","north")

data

class(data)

is.factor(data)

f_data <- as.factor(data)

f_data **<u># Levels값이 생기게 된다</u>** 

<u>**#출력 값:**</u>

<u>**\#[1] east  west  south north east  west  south north**</u>

<u>**\#Levels: east north south west**</u>

is.factor(f_data) **<u># Data의 Type이 factor인지를 알아보는 명령어</u>** 



#### Factor Levels 설정하기

f_data2 <- gl(3,4,labels = c('seoul','japan','china')) 

**<u># gl은 임의적으로 생성해주는 함수</u>**

**<u># gl(3,4,labels =c(A, A, A)) 의 의미는 3개가 있는 요소를 4번 반복하라 라의 의미</u>** 

f_data2

<u>**# 출력값 :**</u>

<u>**\# [1] seoul seoul seoul seoul japan japan japan japan china china china china**</u>

<u>**\# Levels: seoul japan china**</u>