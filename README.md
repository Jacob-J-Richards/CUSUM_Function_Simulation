This project implements a Cumulative Sum (CUSUM) Chart for detecting shifts in the mean of a data stream composed of Gaussian random variables. The CUSUM chart is designed to monitor and signal when there is sufficient statistical evidence to conclude that the mean of the data stream has changed. This implementation follows an S4 class structure in R, allowing for flexible and customizable CUSUM chart simulations.
Key Features:

    CUSUM Chart Setup:
        The data stream starts with random variables sampled from a normal distribution N(0,1).
        At a random time, the data stream switches to a new normal distribution N(delta,1), where delta represents the shift in the mean.
        The CUSUM chart tracks two signals:
            Upper Signal: Detects increases in the mean.
            Lower Signal: Detects decreases in the mean.

    Control Limit:
        The control limit (CL) is dynamically calculated using the spc::xcusum.crit() function. This value determines the threshold at which the CUSUM chart signals that the mean has changed.
        The control limit is set based on a specified Average Run Length (ARL), with k = 0.5 and L0 = 370 (in-control ARL ≈ 370).

    Stopping Condition:
        The simulation halts once either the upper signal exceeds the control limit or the lower signal falls below the negative control limit. This indicates that the null hypothesis (that the data stream is still from N(0,1)) has been rejected.
        The stopping time is recorded, which is the time step at which the control limit is reached, signaling the detection of a mean shift.

    Simulation of Data Streams:
        The class Data_stream simulates a single data stream, starting from a normal distribution N(0,1) and shifting to N(delta,1) at a random time.
        The CUSUM signals (upper and lower) are updated at each time step based on the observed data point.
        A second class, Data_stream_2, is used for larger-scale simulations where the stopping times for multiple data streams are collected.

    Histogram of Stopping Times:
        The simulation is repeated for N = 10,000 data streams, and the stopping times are recorded.
        A histogram of the stopping times is plotted to visualize the distribution of detection times.
        The sample mean of the stopping times (the in-control Average Run Length, ARL) is calculated and is expected to be close to 370, based on the chosen control limit parameters.

Example Usage:

    Create a data stream and monitor the signals:

    r

new_data <- create_Data_Stream()
new_data <- update_Data_Stream(new_data, new_data@x)
show(new_data)

Run the simulation for 10,000 data streams and calculate stopping times:

r

    N <- 10000
    stopping_times <- numeric(N)
    for (i in 1:N) {
      new_data_2 <- create_Data_Stream_2()
      stopping_times[i] <- new_data_2@iteration_count
    }
    hist(stopping_times)
    print(mean(stopping_times))

Conclusion:

This CUSUM chart implementation provides an effective way to detect mean shifts in a normally distributed data stream. By dynamically calculating control limits and evaluating upper and lower CUSUM signals, the simulation accurately identifies shifts and computes the in-control ARL, which is useful for quality control monitoring and similar applications.
