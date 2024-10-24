# CUSUM-Chart with stopping condition of sufficient statistically evidence that population has changed

This is the implimenatation of a cumulative sum chart of a data stream composed of x ~ N(0,1) Gaussian random variables. At a random time the data stream will be sampled from a different gaussian distribution:
x ~ N(delta,1). The code will detect this mean change once the null hypothesis is rejected that the data stream is being sampled from the original distribution and thus terminate the simulation. 
