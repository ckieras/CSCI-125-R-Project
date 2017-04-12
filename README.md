# CSCI-125-R-Project
##EX 1
F<-head(tData)*(180/100)+32
r<-(tData)*(180/100)+32
mean(r)
#her directions were a little strange and didn't correspond totally to the website, so this might be wrong but according to her directions it is right?

##Ex.2
> fam<-as.matrix(r)
> g <- matrix(fam, ncol=12)
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
#Lowest within each month 
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

#In general the higher temperatures are more recent. If the number is higher than 65.5 that means it occurs more recently. First the min temperature is printed and then the max

#EX 3
colnames(g)[c(1,2,3,4,5,6,7,8,9,10,11,12)]<-c("Jan","Feb","Mar","Apr","May","June","July","Aug","Sept","Oct","Nov","Dec")
print(g)
rownames(g)[c(1:132)]<-c(1880:2017)
