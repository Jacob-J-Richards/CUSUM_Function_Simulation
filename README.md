  CUSUM_FUNCTION.Rmd:
  Is the function of which CUSUM_Package_2 is implimenting. 

  Simulated_data_stream_demonstration.Rmd:
  simulates a datastream being sampled from a population whos mean changes at a random time. Plots the     time the mean changes, time of 
  control limit is breached, upper and lower signals etc. 



<h1 align="center"> Cumulative Sum Chart and Simulation </h1>

## Call Commands: 
    Priestley_Chao(user_data_x,user_data_y,user_input_h,user_input_arg)
    
    Parzen_Rosenblatt(user_data,user_input_h,user_input)
    
    Nadaraya_Watson(user_data_x,user_data_y,user_input_h,user_input_arg)
    

## Test Code:

    Priestley_Chao(seq(-3.14,3.14,by=.1),cos(seq(-3.14,3.14,by=.1)),1,seq(-3.14,3.14,by=.01))
    
    Parzen_Rosenblatt(rnorm(100),1,seq(-3,3,length.out=500)) 
    
    Nadaraya_Watson(seq(-3.14,3.14,by=.1),cos(seq(-3.14,3.14,by=.1)),1,seq(-3.14,3.14,by=.01))
