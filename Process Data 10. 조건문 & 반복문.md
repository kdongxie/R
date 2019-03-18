# 조건문 & 반복문

### if

#### 숫자타입에 대한 조건문

a <-10L

class(a)

if(is.integer(a)){

  print("a is integer")

}

#### 문자열 타입에 대한 조건문

t_name <- "Tom"

if(t_name == "Tom"){

  print("t_name is Tom")

}

 

### if else

\# 1

tmp_data <- c('Who','are','you')

tmp_data

if('you' %in% tmp_data){

  print("Exitst")

}else{

  print("Not Exist")

}

\# 2

tmp_data <- c('Who','are','you')

tmp_data

if('you' %in% tmp_data){

  print("you Exitst")

}else if{ 'are' %in% tmp_data

  print("are Exist")

}else{

  print("NOT Exist")

}

### switch [함수에 가깝다]

s <- switch(3,"one",'two','three')

print(s)

 

### ifelse [함수]

tmp_data2 <- c(4,5,6,7,132645,891532)

tmp_data3 <- ifelse(tmp_data2 %% 2 == 0, "even","odd")

tmp_data3

 

 

### 반복문 

#### repeat loop [무한루프]

**<u># 예제 1</u>**

tmp_data4 <- c("hi","hello")

count <- 1

 

repeat{

  print(tmp_data4)

  count <- count+1

  if(count > 5){

​    break **<u># [ ; ] 이 존재하지 않는다</u>**

  }

}

 

**<u># 예제 2</u>**

x <- 1

repeat{

  print(x)

  x = x+1

  if(x==10){

​    break

  }

}

#### while loop

tmp_data5 <- c("hi","hello")

count <- 1

while(count < 10){

  print(tmp_data5)

  count =count+1

  if(count %% 5 == 0){

​    print("WOW")

  }else if(count %% 2 ==0){

​    print("GOOD")

  }

}

 

#### for loop

**<u># 예제 1</u>**

tmp_data6 <- 1:10

for(i in tmp_data6){

  print(i)

  if(i %% 2 == 1){

​    print(c(i,"은/는 2의 배수가 아닙니다"))

  }

}

 

**<u># 예제 2</u>**

for(j in LETTERS[1:10]){

  print(j)

  if(j=='E'){

​    break

  }

}

**<u># 예제 3</u>**

tmp_data7 <-letters[1:10]

for(k in tmp_data7){

  if(k == "d"){

​    next

  }

  print(k)

}

 

rm(list = ls())

 

### 구구단 만들기 

 

g <- 1:9

h <- 2:9

for(l in h){

  msg <-c (l,'단 입니다')

  print(paste(msg, collapse = ""))

  for(m in g){

​    msg2<-c(l, 'X', m,'=',l*m)

​    print(paste(msg2,collapse = ""))

  }

}