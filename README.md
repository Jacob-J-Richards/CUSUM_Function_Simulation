<h1 align="center"> Cumulative Sum Chart and Simulation </h1>

## Install:

    install.packages('spc')

    library(spc)


## Call Command: 
    CUSUM_Chart(data,k,L0,mu0,hs,sided,r) 
    
## Usage:

    Provide your data sample as a column or row of a data frame, matrix, list, or just
    a simple numeric vector. So long as it's 1 dimensional it will coerce the data.

    the input arguments other than your provided data will be passed to 
    xcusum.crit(k, L0, mu0 = 0, hs = 0, sided = "one", r = 30) 
    for the calculation of control limits. 

    xcusum.crit(k, L0, mu0 = 0, hs = 0, sided = "one", r = 30)
    Arguments
    k     reference value of the CUSUM control chart.
    L0     in-control ARL.
    mu0     in-control mean.
    hs     so-called headstart (enables fast initial response).
    sided     distinguishes between one-, two-sided and Crosier’s modified two-sided CUSUM
    scheme by choosing "one", "two", and "Crosier", respectively.
    r     number of quadrature nodes, dimension of the resulting linear equation system
    is equal to r+1 (one-, two-sided) or 2r+1 (Crosier).


    
    
