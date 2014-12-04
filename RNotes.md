---
title: "R notes"
author: "qiandu"
date: "Wednesday, December 03, 2014"
output: html_document
---

----
`which(a1!=a2,arr.aind = T)`*arry.ind*返回数据列的行列位置

`subset(x,subset,select)`subset是取row,select是针对data.frame或矩阵选列

`XT.y <- crossprod(X,y)` 效率比t(x)%*%x

#### 时间日期、正则表达
```{r}
#正则表达
grep("j.",c("ja","jas","aa","bbb","bj"))
#返回字符个数
nchar("123")
#返回向量长度
length("123")

format(Sys.Date(),format= "%A %d/%B/%y")
as.Date("2014/12/04")
as.POSIXct("2014/12/04")

substr("abcdef",2,4)
substring("abcdef",1:6,1:6)
```

####plot

```{r}

layout(matrix(c(1,1,1,2,3,4,2,3,4),nr=3,byrow = T))
hist(rnorm(25),col = "Red")
hist(rnorm(25),col = "Red")
hist(rnorm(25),col = "Red")
hist(rnorm(25),col = "Red")

layout(matrix(1))
op<-par(bg="light blue")
x<-seq(0,2*pi,len=51)
plot(x,sin(x),type="l",bg=par("bg"))
points(x,sin(x),pch=21,cex=0.5,bg="red")

```
```{r}
op <- par(bg="white")
#las 坐标y上的数字水平放置
plot(0,0,xaxt = "n",type = "n",ylim=c(0,100),las=1)
mtext("35",side=2,at=35,line=1,las=1)

```
```{r}
x<-1:10
names(x)<-letters[1:10]
b<-barplot(x,col=rev(heat.colors(3)))
#显示bar数值
text(b,x,labels=x,pos=3)
```
**交叉列联表**
table(x)为x的频数，table(x,y)交叉列联表
```{r}

x<-with(airquality,table(cut(Temp,quantile(Temp)),Month))
prop.table(x,1)

Z <- stats::rnorm(10000)
table(cut(Z, breaks = -6:6))

```

