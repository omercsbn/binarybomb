# Binary Bomb Explanation



Binary Bomb Phase 1 //

In this part, by running the bomb through the Interactive Disassembler, the string sought with phase_1 can be reached.


Another solution is to run the bomb with gdb to create a breakpoint for phase_1. Then, by typing any input, the phase_1 part can be navigated with the dissas command. By finding the memory address of $eax and using x/25 c, it is checked whether this is where the strings are stored. Prints the correct sentence on the screen.


Binary Bomb Phase 2 //

We create a breakpoint for phase_2 and write anything and disassemble the code. We notice that the function called read_six_numbers is called inside the code. We enter 6 random numbers and find where the first number entered compares, the required condition and how far the loop goes. By navigating the code with *until, we go to %esi, %ebx, 4 part. Because here it compares the values that come with eax. We find the formula of phase_2 by checking the values held with the info registers and enter the correct answer.


Binary Bomb Phase 3 //

The shortest and easiest way for phase_3 is to use the Interactive Disassembler application. When we examine Phase 3, we see that %d%d wants 2 integers from us and 8 different cases are controlled with a switcher. We get the correct result with the hex values that each case holds and we finish this part.

Another way for phase_3 is to control the inputs by creating breakpoints. If you can't find the first integer value you need to enter, find out in which range the code accepts numbers. Find the equivalence of each number in hex with info registers by navigating the code with *until. This method will be a bit of bruteforce, but you won't have to worry about seeing the first integer value being compared in the code anyway.

Binary Bomb Phase 4 //

Phase_4 is related to the fibonacci series. When the code is analyzed with breakpoint and rewritten in C, we see that the necessary parts return value(n-1) + value(n-2). Here we see that it is related to fibonacci and what our first integer value should be, enter our second value and solve this stage of the bomb.

Binary Bomb Phase 5 //

In phase_5, when we examine the code by creating a breakpoint, we will see something like cmp $0x34, %ecx. 0x34 is equal to 52. He wants 6 characters from us and the total value of these 6 characters should be 52. This is how we complete this stage.

related to values;
a=10 10
b=16 6
c=17 1 
d=29 12
e=45 16
f=54 9

g=3  3
h=7  4
i=14 7
j=28 21
k=33 5
l=44 11

m=8   8
n=23  15
o=36  13
p=38  3
q=48  10
r=54  6

Binary Bomb Phase 6 // 

The nicest and easiest part for me is the phase_6 part of the bomb. The key here is to create a breakpoint to examine the code and see that the code has a linked list. It asks us to write the linked list items sequentially. By finding the address of Node1 on the code, which is not a requirement, the first loaded node changes according to the input entered. We reach another node by asking for its address and the address it shows on the first node we reach. In this way, we find the whole linked list, its values, which node points to which node.

The first of the two ways is to enter the input in the order in which the nodes show each other and decode the bomb.

The second way is to compare the values held by each node, sort them from large-small or small-to-large, enter input and solve the bomb.

