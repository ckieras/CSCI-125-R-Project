# CSCI-125-R-Project
##EX 1
f<-tData/100
r<-f*(9/5)+57.2
mean(r)
#her directions were a little strange and didn't correspond totally to the website, so this might be wrong but according to her directions it is right?

##Ex.2
> fam<-as.matrix(r)
> g <- matrix(fam, byrow=T, ncol=12)
> g2 <- matrix(fam, ncol=12)
> print(g)

> mean(g[,1])
> mean(g[,2])
> mean(g[,3])
> mean(g[,4])
> mean(g[,5])
> mean(g[,6])
> mean(g[,7])
> mean(g[,8])
> mean(g[,9])
> mean(g[,10])
> mean(g[,11])
> mean(g[,12])


#Lowest within each month 
> apply(g, 2, min)
#Highest within each month 
> apply (g, 2, max)

#lowest total
j<-mean(g[,1])
f<-mean(g[,2])
m<-mean(g[,3])
a<-mean(g[,4])
ma<-mean(g[,5])
ju<-mean(g[,6])
jul<-mean(g[,7])
au<-mean(g[,8])
s<-mean(g[,9])
o<-mean(g[,10])
n<-mean(g[,11])
d<-mean(g[,12])
total<-c(j,f,m,a,ma,ju,jul,au,s,o,n,d)
min(total)
max(total)

print("Yes, there are temperatures that occurred more recently. Any number that is higher than 66 in the vector below means that the year of that temperature is more recent. There are 8 months that have had the highest temperature occur more recently.")
apply(g,2,which.max)

rownames(g)[c(1:132)]<-c(1880:2017)
colnames(g)[c(1,2,3,4,5,6,7,8,9,10,11,12)]<-c("Jan","Feb","Mar","Apr","May","June","July","Aug","Sept","Oct","Nov","Dec")

#whenoccurred<-function(index) {
 #k<-arrayInd(index, dim(g))
 #t<-mapply(`[[`, dimnames(g), k)
 #return(t)
 #}
#whenoccurred(forfunction)


#EX 3
rownames(g)[c(1:132)]<-c(1880:2011)
colnames(g)[c(1,2,3,4,5,6,7,8,9,10,11,12)]<-c("Jan","Feb","Mar","Apr","May","June","July","Aug","Sept","Oct","Nov","Dec")
print(g)
#indextoyear function takes the input as a vector and then searches the matrix
indextoyear<-function(m) {
  k <- arrayInd(m, dim(g))
  t<-mapply(`[[`, dimnames(g), k)
  return(t)
}
indextoyear(133)
yeartoindex<-function(y,m) {
  u<-(g[y,m])
  r<-(match(u,g))
  return(r)
}
yeartoindex("1881","Jan")

#EX 4
plot(1880:2011,g[,1], xlab='year', ylab ='temp')
plot(1880:2011,g[,2], xlab='year', ylab ='temp')
plot(1880:2011,g[,3], xlab='year', ylab ='temp')
plot(1880:2011,g[,4], xlab='year', ylab ='temp')
plot(1880:2011,g[,5], xlab='year', ylab ='temp')
plot(1880:2011,g[,6], xlab='year', ylab ='temp')
plot(1880:2011,g[,7], xlab='year', ylab ='temp')
plot(1880:2011,g[,8], xlab='year', ylab ='temp')
plot(1880:2011,g[,9], xlab='year', ylab ='temp')
plot(1880:2011,g[,10], xlab='year', ylab ='temp')
plot(1880:2011,g[,11], xlab='year', ylab ='temp')
plot(1880:2011,g[,12], xlab='year', ylab ='temp')

Does there seem to be a warming trend in your graphs? Type your answer below: 
Yes, temperatures seem to be rising for each month.


##EX 5
lk<-apply(g, 1, mean)
plot(1880:2011,lk, xlab='year', ylab ='temp')
#Finds the highest average temperature for all years
max(lk)
match (57.3455,lk)
indextoyear(123)
##Finds the lowest average temperature for all years
min(lk)
match(56.978,lk)
indextoyear(30)

In what year did the highest and lowest temperatures occur?
Highest: 2002
Lowest: 1909

##EX 6
plot(1:144,g[121:132,], xlab='year (2000-2012)', ylab ='temp')
Do you see any pattern to the data? Are temperatures rising? 
Yes; there is greater variation in the earilier part of the time span, and in the later part of the data there is more consistency and less variation. They are more concentrated around a higher temperature. 

##EX 7

plot(1:12,apply(g[121:132,], 1,mean), xlab='year (2000-2012)', ylab ='temp')
q<-matrix(apply(g[121:132,], 1,mean))
apply(q,2,mean)

Is it easier to see a warming trend? What is the average temperature of these 13 years?
We are relunctant to generalize, based on such a short time span, but within this time span there are generally more years having a higher temperature than the average within 2000-2012. Average temperature within these years is 58.23963 degrees F

##EX 8
plot(1:120,g[111:120,],xlab='Number of Months Starting Jan 1990', ylab='temp')
min(g[111:120,])
max(g[111:120,])
print(g[111:120,])
Do you see any pattern to the data? Are temperatures rising? Which months had the highest and lowest temperatures?
There isn't a significant pattern to the data, and we attribute this to the small amount of time that we are plotting.
Lowest September 1991
Highest Februrary 1997

##EX 9
w<-apply(g[111:120,],1,mean)
plot(1:10,w,xlab="year", ylab="temp")
apply(w,2,mean)

Is it easier to see a warming trend? What is the average temperature of the 1990s?
Yes, the second half of the 1990s, compared to the first half of the 1990s, in generally warmer. So, there is a warming trend in the 1990s.The mean temperature is 57.8507.
##EX 10
plot(1:120, g[11:20,], xlab='months in 1890-1899', ylab='temp')

#What is the mean temperature of this decade? How does this decade compare to the 1990s?

##EX 10
#Create plots of the monthly averages of the first 44 years, the second 44 years, and the last 43 years. Remember to use the previously defined functions!

#Do you see any warming trends in any of these plots? What is the average temperature of each of these time periods?
