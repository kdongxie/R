# Matrices

### matrix(data, nrow, ncol, byrow, dimnames) 형식의 Syntax를 갖는다

 

m_data <- matrix(c(1,2,3,4),nrow = 2)

m_data2 <- matrix(3:14,nrow = 4)

m_data2 **<u># default 값으로 세로부터 순차적으로 입력됨</u>**

m_data3 <- matrix(3:14,nrow = 4,byrow = TRUE)

m_data3 **<u># 가로부터 순차적으로 입력</u>**

m_data4 <- matrix(3:14,nrow = 4,byrow = FALSE)

m_data4 **<u># 세로부터 순차적으로 입력</u>**

m_data5 <- matrix(1:6)

m_data5 **<u># 세로로 입력되며, column은 한개</u>**

m_data6 <-matrix(1:6, nrow = 3, ncol = 2)

m_data6 **<u># 세로부터 입력되며 2행 3열 짜리의 표가 만들어짐</u>**

m_data7 <-matrix(1:6, nrow = 3, ncol = 1)

m_data7 **<u># 세로부터 입력되며 1행 3열 짜리의 표가 만들어짐 1,2,3 만 출력</u>**

 

#### Matrix의 열과 행의 이름을 부여하는 방법

 

row_names = c('row1','row2','row3') # 열에대한 Vecter 생성

col_names = c('col1','col2') # 행에대한 Vecter 생성

m_data8 <-matrix(1:6, nrow = 3, ncol = 2, dimnames = list(row_names,col_names))

**<u># dimnames 를 바꾸어 줄 때 list의 형식으로 입력 해준다. !!</u>** 

m_data8 **<u># 열과 행의 이름이 바뀐 상태로 출력 됨</u>**

<u>\**# 출력 값 :**</u> 

<u>**\#           col1 col2**</u>

<u>**\#row1    1    4**</u>

<u>**\#row2    2    5**</u>

<u>**\#row3    3    6**</u>

<u>****</u> 

#### 두개의 matrix 을 사칙연산 하기

m_colnames <-c("col1","col2")

m_rownames <-c("row1","row2","row3")

m_matrix <- matrix(1:6, nrow = 3, ncol = 2, dimnames = list(row_names,col_names))

m_matrix

 

m_matrix[1,2] **<u># row 가 우선적으로 선택 row1 col2</u>**

m_matrix[2,] **<u># row2 의 전체 값</u>**

m_matrix[,2] **<u># col2 의 전체 값</u>**

 

m_matrix2 <- matrix(6:12, nrow = 3, ncol = 2, dimnames = list(row_names,col_names))

m_matrix2

 

m_matrix3 = m_matrix + m_matrix2

m_matrix3 **<u># 각각의 행렬끼리 더한다</u>**

m_matrix3 = m_matrix * m_matrix2

m_matrix3 **<u># 각각의 행렬끼리 곱한다</u>**

m_matrix3 = m_matrix - m_matrix2

m_matrix3 **<u># 각각의 행렬끼리 뺀다</u>**

m_matrix3 = m_matrix / m_matrix2

m_matrix3 **<u># 각각의 행렬끼리 나눈다</u>**

m_matrix3 = m_matrix %% m_matrix2

m_matrix3 **<u># 행렬끼리의 나머지값</u>**

m_matrix3 = m_matrix %/% m_matrix2

m_matrix3 **<u># 행렬끼리의 나누기 몫</u>**

 