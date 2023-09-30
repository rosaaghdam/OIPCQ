# OIPCQ
library(devtools)

install_github('rosaaghdam/OIPCQ')

library(OIPCQ)

##data row:samples columns:variable

data = read.csv("yourdatapath")

data_BN = log(data+1)

q1=0.8 #threshold for MI

q2=0.9 #threshold for CMI

data = t(data_BN)

result = edgereduce(data,q1,q2)

BN = result$G_order1
