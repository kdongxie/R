# Arrays

v1 <- c(1,2,3)

v2 <- c(10,11,12,13,14,15)

arr <- array(c(v1,v2))

arr **<u># array 의 값을 단순이 하나로 합친다</u>**

 

arr2 <-array(c(v1, v2), dim=c(3,3,2))

arr2 **<u># 3 X 3 의 행렬을 2개 만든다.</u>**

 

#### 다차원 array

row_names <- c("row1","row2","row3")

col_names <- c("col1","col2","col3")

matrix_names <- c("matrix1","matrix2")

arr3 <-array(c(v1,v2),dim=c(3,3,2), dimnames = list(row_names,col_names,matrix_names))

arr3 **<u># 3 X 3 의 행렬을 2개 만들고 Labeling(dimnames를 통해) 하기.</u>**

 

arr3[1,2,1] **<u># row1의 col2의 matrix1 을 가져온다</u>**

arr3[2,2,2] **<u># row2의 col2의 matrix2 을 가져온다</u>**

arr3[, 1,] **<u># col2의 값 출력</u>**

arr3[1, ,] **<u># row1 의 값 출력</u>**

arr3[,, 2] **<u># matrix2 의 값 출력</u>**

 

 

#### Apply

v3 <- c(1,2,3,10,11,12,13,14,15)

v4 <- c(1,1,1,1,1,1,1,1,1)

data.array <- array(c(v3,v4),dim = c(3,3,2)) 

**<u># 3X3의 행렬 2개 생성 (row, col, matrix)</u>**

data.array

<u>**\#출력 값:**</u>

<u>**\#, , 1**</u>

<u>**\#**</u>

<u>**\#      [,1]  [,2]   [,3]**</u>

<u>**\#[1,]    1   10   13**</u>

<u>**\#[2,]    2   11   14**</u>

<u>**\#[3,]    3   12   15**</u>

<u>**\#**</u>

<u>**\#, , 2**</u>

<u>**\#**</u>

<u>**\#      [,1]  [,2]   [,3]**</u>

<u>**\#[1,]    1    1    1**</u>

<u>**\#[2,]    1    1    1**</u>

<u>**\#[3,]    1    1    1**</u>

 

result <- apply(data.array,c(2),sum)

<u>result **# column의 전체 값들을 합한다.**</u>

<u>****</u> 

<u>**\# 출력값 :**</u>

<u>**\# [1]  9 36 45**</u>

 

result2 <- apply(data.array,c(1),sum)

result2 **<u># row의 전체 값들을 합한다.</u>**

**<u># 출력값 :</u>**

<u>**\# [1] 27 30 33**</u>

 

