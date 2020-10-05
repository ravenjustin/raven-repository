# raven-repository
# This is a line from RStudio
Working Directory
# setwd("C:/Users/rducut/Documents/inline; filename=_resource_map_doi_10_18739_A2S46H57S.zip_/resource_map_doi_10_18739_A2S46H57S/data")
# netR <- read.csv("netR.csv")
# as.vector(netR$doy)

# NetR <- read.csv("https://cn.dataone.org/cn/v2/resolve/urn:uuid:229ad93b-ddfe-4e3f-a32d-d8e8e17eca4d")
Graph1 <- subset(netR, sensorZ==800 & year==2017 & site=="hd")
# subset(netR, sensorZ==800 & year==2017 & site=="hd")
# aggregate(IRUp~doy,Graph1,mean)
# aggregate(IRDn~doy,Graph1,mean)
Graph2 <- subset(netR, sensorZ==800 & year==2017 & site=="ld")
# subset(netR, sensorZ==800 & year==2017 & site=="ld")
# aggregate(IRUp~doy,Graph2,mean)
# aggregate(IRDn~doy,Graph2,mean)
Graph3 <- subset(netR, sensorZ==100 & year==2017 & site=="hd")
# subset(netR, sensorZ==100 & year==2017 & site=="hd")
# aggregate(IRUp~doy,Graph3,mean)
# aggregate(IRDn~doy,Graph3,mean)
Graph4 <- subset(netR, sensorZ==100 & year==2017 & site=="ld")
# subset(netR, sensorZ==100 & year==2017 & site=="ld")
# aggregate(IRUp~doy,Graph4,mean)
# aggregate(IRDn~doy,Graph4,mean)

doy vs IRUp
hd.at.800<-aggregate(IRUp~doy,Graph1,mean)
hd.at.100<-aggregate(IRUp~doy,Graph3,mean)
ld.at.800<-aggregate(IRUp~doy,Graph2,mean)
ld.at.100<-aggregate(IRUp~doy,Graph4,mean)

Longwave Radiation Facing Up during 2017
plot(hd.at.800,type="l",main="Longwave Radiation Facing Up during 2017",
+ xlab="doy(day of year)",
+ ylab="IRUp (w/m^2)",
+ cex.axis=0.6,
+ xlim=c(88,225),
+ ylim=c(0,400),
+ col="red")
lines(hd.at.100,type="l",col="blue")
lines(ld.at.800,type="l",col="green")
lines(ld.at.100,type="l",col="yellow")

legend(88,400,
       legend=c("High Density, 1m","High Density, 8m", "Low Density, 1m","Low Density, 8m"),
       col=c("red","blue","green","yellow""),
       lty=1:2,
       cex=0.8,
       title="Site",
       text.font=2)

doy vs IRDn
hd.at.800.Dn<-aggregate(IRDn~doy,Graph1,mean)
hd.at.100.Dn<-aggregate(IRDn~doy,Graph3,mean)
ld.at.800.Dn<-aggregate(IRDn~doy,Graph2,mean)
ld.at.100.Dn<-aggregate(IRDn~doy,Graph4,mean)

Longwave Radiation Facing Down during 2017
plot(hd.at.800.Dn,type="l",main="Longwave Radiation Facing Down during 2017",
+ xlab="doy(day of year)",
+ ylab="IRDn (w/m^2)",
+ cex.axis=0.6,
+ xlim=c(88,225),
+ ylim=c(0,500),
+ col="red")
lines(hd.at.100.Dn,type="l",col="blue")
lines(ld.at.800.Dn,type="l",col="green")
lines(ld.at.100.Dn,type="l",col="yellow")