# Python에 Matplot이 있고 R에는 ggplot2가 있다

##### install.packages("ggplot2")

library(ggplot2)

data <- c('a','b','a','c','d')

data

qplot(data)

hist(data) **<u># 요소 값이 숫자일 때만 가능함</u>** 

 

View(mpg) **<u># 1999~2008 38개 유명 자동차 연비에 대한 ggplot2의 내장 데이터</u>**

class(mpg)

str(mpg)

colnames(mpg)

rownames(mpg)

#### 데이터를 그래프화 해주는 qplot

qplot(data = mpg,x = hwy, y = manufacturer)

qplot(data = mpg,x = hwy, y = model)

qplot(data = mpg,x = hwy, y = trans)

qplot(data = mpg,x = hwy, y = class)

qplot(data = mpg,x = drv, y = hwy)

qplot(data = mpg,x = hwy, y = model, geom='line') **<u>#선형으로 이루어진 그래프</u>**

qplot(data = mpg,x = drv, y = hwy, geom ='boxplot',colour=drv) **<u>#box그래프</u>**

qplot(data = mpg,x = trans, y = hwy, geom ='boxplot',colour= trans) **<u>#colour로 변수의 색상 지정 가능</u>** 

qplot(data = mpg,x = trans, y = hwy, geom ='boxplot',colour= 'red') **<u>#colour로 색상 지정 가능</u>**