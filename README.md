# Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit
## Digital circuit for Linked List-
### Problem Statement-
We have to implement a **linked list** data structure using the digital cirduits components like mux, gates, registers e.t.c.
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

Now, we have our required result, we just have to show it on 7 segment display.
For 7 segment display we will use **Shift Add 3 method**. You can read about it [here](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/Binary2BCD.pdf).
## Solution-
You can find complete proteus file [here](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/ps1.DSN).
### Working-
You can see the working video of our circuit [here](https://drive.google.com/file/d/1smdCNSce_toEbJcSIwCuEU5kZWQFbrIi/view?usp=sharing).
We have used the data give in [problem statement](https://github.com/ujjawalece/Implementation-of-Linked-List-and-Binary-Tree-using-Digital-Circuit/blob/main/Digisim'21_PS1.pdf).
