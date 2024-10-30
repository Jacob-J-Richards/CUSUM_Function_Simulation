<h1 align="center"> Cumulative Sum Chart Function </h1>

## Install:
    install.packages('spc')
    library(spc)

## Call Command: 
    CUSUM_Chart(data,k,L0,mu0,hs,sided,r) 
    
## Usage:
    Provide your data as any one-dimensional data structure
    The input arguments other than your provided data will be passed to 
    ?spc::xcusum.crit
    for the calculation of the control limit

## Try this:
    CUSUM_Chart(rnorm(1000),.5,370,0,0,"two",30)


    
    
    
