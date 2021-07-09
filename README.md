# Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit
## Digital circuit for Linked List-
### Problem Statement-
We have to implement a **linked list** data structure using the digital circuit components like mux, gates, registers e.t.c.
And finally, we have to display the maximum number present in the linked list which is smaller than a given number.
Please, read the complete problem statement [here](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/Digisim'21_PS1.pdf) for better undersatnding.
### Approach-
We will simulate our circuit on EDA tool **Proteus**.

We have a ROM which act as a memory device for this circuit. Its store all the values of linked list corresponding to there addresses. You can change the data of Rom by using [this](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/python%20image%20file.py) python file. It will create [binary_file_PS1_t1.bin](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/binary_file_PS1_t1.bin) and you have to just load this file on our ROM.

Now, we connected two Flip-Flops to the output of our ROM one FF is negative edge triggered and the other one is positive edge triggered.
So, when the negative clock cycle comes the data (bank money) got stored in the first ff.

**TRAVERSING THROUGH LINKED LIST-**
We used an adder to increase the current address by 1 and then give that address to the
ROM with the help of a MUX which has two input lines one is of current address and other
one is of current address + 1. So now we can get the next node address and this address is
saved into the positive edge FF, whose output is used as current address for next cycle. So,
in this way we are traversing through the linked list.

**CALCULATION-**
Now, we just have to calculate the maximum bank amount which Harshad Mehta can repay.

It’s simple; remember we stored the bank money data in the negative edge FF. So, we just
compare that data to the current holding (CH) of Harshad Mehta using a comparator if it’s
less than CH we store it using a ff otherwise do nothing. And at last when we reach at end
of linked list (when next node address = 255) we subtract it from CH to get the amount left.

To find the address we travel through ROM data using a simple counter and comparing the
output of ROM with the amount which Harshad Mehta can repay, if its equal we show the
counter value which is the ADDRESS of the bank.

Now, we have our required result in binary form, we just have to show it on 7 segment display. Before that we have to convrt it into BCD.
For 7 segment display we will use **Shift Add 3 method**. You can read about it [here](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/Binary2BCD.pdf).
### Solution-
You can find complete proteus file [here](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/ps1.DSN).
### Working-
You can see the working video of our circuit [here](https://drive.google.com/file/d/1smdCNSce_toEbJcSIwCuEU5kZWQFbrIi/view?usp=sharing).
We have used the data give in [problem statement](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/Digisim'21_PS1.pdf).


## Digital circuit for Binary Tree-
### Problem Statement-
We have to implement a **Binary Tree** data structure using the digital circuit components like mux, gates, registers e.t.c.
Please, read the complete problem statement [here](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/Digisim'21_PS2.pdf) to understand what exactly we have to do.
### Approach-
We will simulate our circuit on EDA tool **Proteus**.

We have a ROM which act as a memory device for this circuit. Its store all the values of linked list corresponding to there addresses. You can change the data of Rom by using [this](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/python%20image%20file.py) python file. It will create [binary_file_PS2_t1.bin](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/binary_file_PS2_t1.bin) and you have to just load this file on our ROM.

The input of our ROM is connected to the output of an 8-bit 4:1 MUX. The select
line of MUX is a counter of 2-bit (count from 00 to 11). The input of this mux are
the Present node address, Present node address + 1, Present node address +
2.

We also created a 8-bit 8:1 mix whose input are connected to the output of 8 D-
FF connected in series and which store the left and right child node address of
the current node. And the output of this mux is connected to the input of 8-bit 4:1
mux.

So, what is happening? When our clock start, the counter will we at the 00 and it
will give the data of the present node, which is stored in separate D-FlipFlop
after some processing. When our counter increases and go to 10, ROM will give
address of left node which is store in one of the 8 FF connected to 8-bit 8:1 mux
and similarly when counter reaches to 10 the right child node address got
stored.

So, in this way we store all the address of our nodes and process them one by
one by sending them to 8-bit 4:1 mux.
We add one more 8-bit 8:1 mux which will store the value of tpc*distance of
each node.

The data which come out of ROM every time when our counter is at 00 is the
price of petrol and we just have to add the value of tpc*distance into it, which we
do by simple adder and then we compare this value (using comparator) with the
previous data if this is smaller the previous one, we will replace it otherwise do
nothing and whenever we replace data we also store it address in a register
which will become our final address after all nodes are processed.

Now, we have our required result, we just have to show it on 7 segment display.
For 7 segment display we will use **Shift Add 3 method**. You can read about it [here](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/Binary2BCD.pdf).
### Solution-
You can find complete proteus file [here](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/ps2.DSN).
### Working-
You can see the working video of our circuit [here](https://drive.google.com/file/d/1-Hjrgi0n4gRep6W1q02odHNMzv3j3KjB/view?usp=sharing).
We have used the data give in [problem statement](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/Digisim'21_PS2.pdf).
