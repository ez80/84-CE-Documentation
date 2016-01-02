Hex, Binary, and Decimal
********************************

| **If you are already familiar with binary and hexadecimal, you may skip straight on to the next tutorial.**
| If you would prefer a video tutorial, you can use `this <http://youtu.be/jvx-NrILgpE>`_ instead. Just know that assembly programmers use the prefix "$" for hexadecimal and "%" for binary.

When we humans write numbers, we like to use base 10, also called decimal. Decimal is a number system in which there are ten digits (0-9). We can write any number from zero to nine using that digit.

- 4

But if we want to write a number greater than nine, we have to use two digits.

- 42

The digit on the left tells you how many "tens" there are in this number (because we use base 10) and the digit on the right tells you how many "ones" there are in this number. So we can say that a two-digit number is equal to ``( 10 * digit on the left ) + digit on the right``.

For numbers greater than 99, the highest two-digit number, we use three digits.

- 256

The digit on the right now tells you how many "hundreds" there are (one hundred being the next power of ten), and the middle digit tells you how many "tens" there are, etc. So we can say that a three-digit number is equal to ``( 100 * digit on the left ) + ( 10 * digit in the middle ) + digit on the right

I'm sure you can see the pattern by now.

Humans may like base 10, but computers don't. Computers can't keep track of ten digits very easily. They only like two: 0 and 1. A number system using only two digits is base 2, or binary. When we write a binary number, we usually put a percent sign ``%`` in front of it to make it clear that it isn't base 10. Here's what a typical binary number may look like: %101010

In base 10, each digit is ten times as significant as the next. For example, a small change in the "hundreds" place makes a much bigger change in the value of a number than a change in the "tens" place, and likewise between the "tens" and "ones" places. In binary, each digit is twice as significant as the one after it. What do I mean by that? Well on the far left, there's the "ones" place as we would expect it. After that comes the "twos" place. And after that comes the "fours" place (2 * 2 = 4). And the "eights" (4 * 2 = 8), "sixteens" (8 * 2 = 16), "thirty-twos," and so on. It will really pay to memorize your powers of two at least up to 2^8, which is 256 (in decimal notation).

So how can we use this information to go from a binary number to a decimal number? We make a chart!

======  ======  ======  ======  ======  ======  ======
Place   32's    16's    8's     4's     2's     1's
======  ======  ======  ======  ======  ======  ======
Digit   1       0       1       0       1       0
======  ======  ======  ======  ======  ======  ======
Okay, so now how do we do this? We multiply down and add across. So let's start from the right:

| There is a 0 in the 1s place, so we multiply 1 times 0. The result is 0.
| There is a 1 in the 2s place, so we multiply 2 times 1. The result is 2.
| There is a 0 in the 4s place, so we multiply 4 times 0. The result is 0.
| There is a 1 in the 8s place, so we multiply 8 times 1. The result is 8.
| There is a 0 in the 16s place, so we multiply 16 times 0. The result is 0.
| There is a 1 in the 32s place, so we multiply 32 times 1. The result is 32.

Now we add the results. So 32 + 0 + 8 + 0 + 2 + 0 = 42. %101010 = 42. This may seem like a rather tedious way to work with numbers, stretching what would otherwise be a relatively short and easy-to-read decimal number into a long, inefficient, and annoying string of binary, which is why we programmers have another way of writing numbers: hexadecimal!

Hexadecimal, often abbreviated to hex, is precisely what the name suggests: base 16. Hexadecimal numbers are much shorter than binary, and usually shorter than decimal too. In assembly, we put a dollar sign ``$`` in front of a number to make it clear that the number is hexadecimal. (Sometimes you will see ``0x`` in front of a hexadecimal number too.) Hexadecimal has a "ones" place, a "sixteens" place, (bear with me here) a "256s" place (16 * 16 = 256), a "65536s" place (256 * 16 = 65536), a "16777216s" place (65536 * 16 = 16777216), and so on. It gets really big really quickly.

But wait! In decimal, we had ten digits. Binary had two. Hexadecimal needs... sixteen digits, right? How do we even write that? Well, we use letters. In Hexadecimal, when a digit is ten, we use the letter A. When a digit is eleven, we use the letter B. C is twelve, D is thirteen, E is fourteen, and F is fifteen. (Anything past that spills over into the next digit, just like how decimal doesn't have anything over the digit 9.)

Let's use another chart to convert from hexadecimal to decimal.

======  =======  ======  ======  ======
Place   16384's  256's   16's    1's
======  =======  ======  ======  ======
Digit   9        9       2       C
======  =======  ======  ======  ======
Just like with binary numbers, we multiply down and add across. We just have to remember that letters A-F correspond to the numbers 10-15.

| There is a C in the 1s place, so we multiple 1 times 12 (C = 12). The result is 12.
| There is a 2 in the 16s place, so we multiple 2 times 16. The result is 32.
| There is a 9 in the 256s place, so we multiple 2 times 16. The result is 2304.
| There is a 9 in the 65536s place, so we multiple 2 times 16. The result is 36864.

36864 + 2304 + 32 + 12 = 39212. That was a very large number. If we were to write it out in binary it would be %1001100100101100. Ick. Hexadecimal makes things a lot cleaner. And the best part is that every four digits in binary is equal to EXACTLY one hexadecimal digit! So if you split up that icky binary string into sections of four (%1001 %1001 %0010 %1100) every little section corresponds with one of the digits of the hexadecimal string. This makes converting between binary and hexadecimal much easier if you just memorize which 4-digit binary numbers go with which hexadecimal digits.

Okay, so everything in computers is actually binary, which can be represented more nicely in hexadecimal. But even a computer can't manage a humongous amount of binary in one large lump. It needs to organize things. So it splits up the data into sections called bytes. Every binary digit in a computer is a bit. If the bit is one, we say it is on. If it is zero, we say it is off. Every byte has 8 bits. That means each byte is an 8-digit binary number, or a 2-digit hexadecimal number. Since a single byte is two hexadecimal digits and the highest number you can write with two hexadecimal digits is $FF (255 in decimal), a byte can store a number from 0 to 255. This is why lots of computer things have limits at 255 or 256. You know the term kilobyte, which is 1024 bytes (roughly a thousand). A megabyte is of course 1048576 bytes (roughly a million).

Finally, computers start counting with zeroes, so if I have two files, one would be labeled file 0, and the other file 1.

Here are some practice problems to do:

========  ============  ======  
Decimal   Hexadecimal   Binary    
========  ============  ====== 
10        ?             ?
72        $48           ?       
?         ?             101011  
?         $1E           ?
========  ============  ======  

If you can do all of these problems, you are ready to move on to the next tutorial.

If you need more help, visit the additional learning page: `here </en/latest/al/numbers.html>`_ 

We'll be using these concepts very frequently, so make sure you have mastered them before moving on to the next tutorial.

*In the next tutorial, we'll be learning about how information is stored on your calculator.*
