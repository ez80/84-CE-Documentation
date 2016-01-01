Hex, Binary, and Decimal Additional Learning
********************************************
*Note: This is the additional learning section of the Hex, Binary, and Decimal tutorial, the original tutorial is available* `here </en/latest/numbers.html>`_.

Ok, so let's visit our previous practice problems. We'll walk through them step by step.

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
10        ?             ?
72        $48           ?       
?         ?             101011  
?         $1E           ?
========  ============  ======  

Ok, so for the first problem, we need to convert 10 in decimal to hexadecimal. Let's make another chart.

======  =======  ======  ======  ======
Place   16384's  256's   16's     1's
======  =======  ======  ======  ======
Digit   0        0       0       10
======  =======  ======  ======  ======

Since we have 10 1's, no 16's, 256's, or 16384's, our number is still 10 in hexadecimal.

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
10        10            ?
========  ============  ======  

Great! Now we need to convert 10 to binary.

How many 16's go into 10? Zero.

======  ======  ======  ======  ======  ======
Place   16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======
Digit   0                                      
======  ======  ======  ======  ======  ======

How many 8's go into 10? One. Now we subtract 8 from 10, and are left with 2.

======  ======  ======  ======  ======  ======
Place   16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======
Digit   0       1                              
======  ======  ======  ======  ======  ======

How many 4's go into 2? None.

======  ======  ======  ======  ======  ======
Place   16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======
Digit   0       1       0                     
======  ======  ======  ======  ======  ======

How many 2's go into 2? One. 2-2=0, so we are done

======  ======  ======  ======  ======  ======
Place   16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======
Digit   0       1       0       1       0  
======  ======  ======  ======  ======  ======

10 in binary is 01010

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
10        10            01010
========  ============  ======  

Ok, so now for the next problem, we are given two values, and we need to solve for the binary form.

========  ============  =======  
Decimal   Hexadecimal   Binary    
========  ============  ======= 
72        $48           ?       
========  ============  =======  

But which way is easiest to solve from? 

We can convert decimal to binary like so:

======  ======  ======  ======  ======  ======  ======  ======
Place    64's    32's    16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======  ======  ======
Digit   1       0       0       ?       ?       ?       ?  
======  ======  ======  ======  ======  ======  ======  ======

72-64= 8

======  ======  ======  ======  ======  ======  ======  ======
Place    64's    32's    16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======  ======  ======
Digit   1       0       0       1       0       0       0    
======  ======  ======  ======  ======  ======  ======  ======

8-8=0

72 in binary is 1001000

========  ============  =======  
Decimal   Hexadecimal   Binary    
========  ============  ======= 
72        $48           1001000      
========  ============  =======  

But what if we want to convert directly from hexadecimal to binary?

$48 in hexadecimal = (4*16
:sup:`2`
) * (8 * 16)

$48 in hexadecimal = (1*2
:sup:`6`
) * (1*2
:sup:`3`
)

Another way of writing the chart is with powers of 2

======  ======  ======  ======  ======  ======  ======  ======
Place   6       5       4       3       2       1       0
======  ======  ======  ======  ======  ======  ======  ======
Digit   1       0       0       1       0       0       0    
======  ======  ======  ======  ======  ======  ======  ======

But you can still also do

======  ======  ======  ======  ======  ======  ======  ======
Place   64's    32's    16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======  ======  ======
Digit   1       0       0       1       0       0       0    
======  ======  ======  ======  ======  ======  ======  ======

$48 = (64) * (8)

You still get the same answer, 1001000

Ok, now for the next problem, we need to convert binary back in to decimal and hexadecimal. Once again, we can either decide to convert binary to decimal and then to hexadecimal or to convert to each using binary.

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
?         ?             101011
========  ============  ======  

Since we already know how to convert decimal to hexadecimal, we're going to convert directly to each.

Decimal:

======  ======  ======  ======  ======  ======  ======
Place   32's    16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======  ======
Digit   1       0       1       0       1       1    
======  ======  ======  ======  ======  ======  ======

%101011 to decimal = (1*32) + (0 * 16) + (1*8) + (0*4) + (1*2) + (1*1)
%101011 to decimal  = 43

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
43         ?            101011
========  ============  ======  

Once again, %101011 = (1*32) + (0 * 16) + (1*8) + (0*4) + (1*2) + (1*1)
32 is 2 *16, or 2 16's. Since there are no other 16's that can fit inside, we put 2 in the 16's column.

====== ======  ======
Place  16's    1's
====== ======  ======
Digit  2       ?
====== ======  ======

How many do we have left over? 1*8, 1*2, and 1*1. In Hexadecimal, we have B left over.

====== ======  ======
Place  16's    1's
====== ======  ======
Digit  2       B
====== ======  ======

So our hexadecimal version of %101011 is 2B

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
43        2B            101011
========  ============  ======  

Try the final one on your own, if you get stuck, our work is below. You can also check your answer when you are finished.

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
?         $1E           ?
========  ============  ======  



The solution:
========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
?         $1E           ?
========  ============  ======  

=======  ============ 
Decimal  Hexadecimal  
=======  ============  
10       A                     
11       B            
12       C            
13       D            
14       E            
15       F            
=======  ============

E is 14 in decimal.

$1E in decimal = (1*16
:sup:`1`
) * (14*16
:sup:`0`
)

$1E = 30 in decimal

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
30         $1E           ?
========  ============  ======  

$1E in decimal = (1*16
:sup:`1`
) * (14*16
:sup:`0`
)

======  ======  ======  ======  ======  ======  ======
Place   32's    16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======  ======
Digit   0       1       ?       ?       ?       ?    
======  ======  ======  ======  ======  ======  ======

(14*16
:sup:`0`
)

14=8+4+2

======  ======  ======  ======  ======  ======  ======
Place   32's    16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======  ======
Digit   0       1       1       1       1       0    
======  ======  ======  ======  ======  ======  ======

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
30        $1E           011110
========  ============  ======  

Oh, and one last thing, now that we have learned to convert between these three systems ourselves, here is a cheatsheet:

=======  ============  ========
Decimal  Hexadecimal   Binary 
=======  ============  ======== 
1        1              0001
2        2              0010
3        3              0011
4        4              0100
5        5              0101
6        6              0110        
7        7              0111
8        8              1000
9        9              1001
10       A              1010             
11       B              1011
12       C              1100
13       D              1101
14       E              1110
15       F              1111    
=======  ============  =========

You can use it to convert easily, for example:
$7F in binary is 01111111

If you still don't understand, you can ask around on the `Cemetech <http://cemetech.net>`_ forums. These concepts will be used quite frequently, so you need to master them.

`To the next tutorial! </en/latest/registers.html>`_ 
