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


#In general the higher temperatures are more recent. If the number is higher than 65.5 that means it occurs more recently. First the min temperature is printed and then the max
