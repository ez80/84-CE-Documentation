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
:raw-html:`<br />`
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
:raw-html:`<br />`
1001000

========  ============  =======  
Decimal   Hexadecimal   Binary    
========  ============  ======= 
72        $48           1001000      
========  ============  =======  

But what if we want to convert directly from hexadecimal to binary?

$48 in hexadecimal = (4*16
:sup:`2`
)

`To the next tutorial! </en/latest/registers.html>`_ 
