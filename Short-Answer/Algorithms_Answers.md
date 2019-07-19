# Answers - Analysis of Algorithms


## Exercise 1
```txt

a.  In order to approximate run time, each line is considered and the relationship between increasing `n` and the number of operations that results for a given line of code is deduced.  Then, run time becomes a function of the number of operations (y-axis) vs. the size of the input (x-axis).

Line 1:

*a = 0*
This is O(1) or constant time regardless of the sample size(n) 
since changing n does not change the number of times this executes.  It is 
going to execute only one time each time the program executes.

*while(a < n*n*n):*
The relationship here is going to depend on the sample
size, and how many times the loop runs with respect to the sample size. For 
now, we can simplify the exponents of n in this step and write:

while (a < n^3):
So, in terms of this step alone, we can't deduce its runtime because how the 
loop is controlled and how it reaches its upper bound and terminates is vital
. This we will see in the step that follows.

a = a + n*n or a = a + n^2:
In this case, starting at a = 0, as n increases by a exponential factor of 3, 
the number of times this loop executes will by an exponential factor of 2.  
Therefore, as the sample size increases by a power of 3, the number of 
operations will increase by a power of 2.  The ratio between these two 
quantities represents the big O approximation, and this would reduce to an 
exponential factor of n^1, considering n^3/n^2.  Therefore, this loop would 
show linear time, or O(n).  

Overall, considering all the steps, the step that dictates the overall 
runtime here is the while loop since the first step is constant time.  
Therefore, this process should approximate linear time, or O(n) overall.  


b.  sum = 0 (constant time, only executes once regardless of input size)
        for i in range(n): (linear time - as n increases by one, i increases 
        by 1 so this loop puts out 1 value for every incoming value of n, 
        making this O(n))
          i += 1
          for j in range(i + 1, n): (linear time)
            j += 1
            for k in range(j + 1, n): (linear time)
              k += 1
              for l in range(k + 1, 10 + k): (constant time - notice that 
              complexity doesn't grow here because the bounds of this range 
              are not influenced by n at all here, so if n grows, this range 
              doesn't grow like the other three do.)
                l += 1
                sum += 1
                
         
Overall, the first three nested loops each demonstrate O(n) runtime and 
the last loop which is not controlled by the input size would be constant.Because of 
this, the three loops that are controlled by n dictate the overall runtime 
here of O(n^3).  
    
c.  def bunnyEars(bunnies):
          if bunnies == 0: (constant)
            return 0 (constant)
    
          return 2 + bunnyEars(bunnies-1) (This is a recursive call - this is
           going to be linear time and will output once time for every n 
           value.  

Overall, dropping the constants, this becomes linear or O(n) runtime.
```



## Exercise 2
```txt

Pseudocode analysis:

allocate a variable in memory to track if the egg is broken or not (bool)
allocate a variable in memory to track current_floor
start at first floor (f = 1)
    while not broken
        drop egg
        if broken
            broken = True
            return current_floor
        else 
            f += 1 (go to the next floor)

Considering the runtime here - the while loop can only output one operation 
for every input since it either will return or repeat once depending on if 
the egg is broken or not, therefore, this could be approximated as O(n) runtime.
```


