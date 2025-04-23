Prime number count parallelism exercise

- This code counts the number of primes in an array without parallelism
- Your goal is to add parallelism with OpenMP!
- The project should be configured properly, but you can add OpenMP to 
  Visual Studio project by going to Project Properties-C/C++-Language.
  Set the Open MP Support option to "Yes"
-
  1. What is the average time for ten runs of the serial version of the code? (You may run this
10 times and manually calculate the average or you may write a loop to do it for you.)
  - Average (0.463921 + 0.481424 + 0.427255 + 0.427613 + 0.460836 + 0.442694 + 0.4455 + 0.443249 + 0.441285 +  0.435019) / 10 = 0.4468796

2. What is the average time for ten runs of the parallel version of the code? (You may run
this 10 times and manually calculate the average or you may write a loop to do it for
you.)
- Average(0.172017 + 0.168392 + 0.163043 + 0.191578 + 0.170704 + 0.176644 + 0.183345 + 0.168075 +  0.173528 + 0.17054) / 10 = 0.1737866

3. Calculate the speedup of the parallel version. Is the parallel code significantly faster?
	- 0.4468796 - 0.1737866 = 0.273093 
	- (0.273093 ÷ 0.4468796) × 100 = 61.11%
	-  Yes, the parallel code is significantly faster as it reduces the runtime by over 61%

4. How many elements of the array do you think OpenMP assigned to each processor? 
- 4 threads were used, OpenMP assigned approximately 250,000 elements to each processor, as the total array size is 1,000,000

5.If you have time, try to parallelize the gen_numbers() function and compare the timing.
Was it faster? If it wasn’t faster, what do you think happened?
- parallelizing the gen_numbers() function using OpenMP, the runtime showed little or no improvement(did not provide a meaningful speedup).  
- The overhead of creating and managing threads outweighed the small gain from dividing the work.