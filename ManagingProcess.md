Managing and Interacting with processes
=======================================

To run in *background* use `&` at the end of the program, for example:

    $ my_prog input.txt > result.txt &
    [1] 6790

The number is the *Process ID* or **PID**.


To check what process we have running

    $ jobs
    [1]+ Running my_prog input.txt > results.txt

To send the first process of the stack in *foreground*

    $ fg
    my_prog input.txt > result.txt

to send any process 

    $ fg %<num>

where num is the <num> is the number of the process in the stack. In our example is 1.

To send in background a process use `Ctrl-z`
