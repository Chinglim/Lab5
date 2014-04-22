Lab5
====
##1st Program Operation

7(Hexadecimal) is the op code for LDAI, it will load the value of the operand into the accumulator. In the next address, 8(hexadecimal) is seen, that will be the operand value, to be loaded into the accumulator. 

At address 02, '6'(hexadecimal) is the opcode for ADDI, it means add the value of the operand to the number in the accumulator. Since '1'(hexadecimal) is on the next address, the operation will be that 1 will be added to the current accumulator value, '8' to generate a '9'(hexadecimal).

As in the address 04, '4' is seen, it is ithe opcode for transferring the data from the accumulator to the selected output port. The output port number is as display on address 05 . Therefore, the value '9' hexadecimal will be output on port 3 .

At address 06, 'B' (hexadecimal) is seen, it is the opcode to jump to the operand address if the accumulator has a negative number. Since '9'(hexadeciaml) has a sign bit of 1 which means it is a negative number, it JN function will be carried out and back to address 02 instruction again.

Apparently, this program will output values that is going up sequentially, out of port 3, as long as the post addition value is within '8'-'F' hexadecimal value. This is because for this range of number, their sign bit is '1', which meant that they are negative number , so the jump function to carry out the plus 1 will be carried out.

This process will just end when the accumulator value reads 0 as the sign bit of the hexdecimal number.

## 1st Program Instruction Cycle 
The defination of those cycles are labelled clearly in the diagrams attached " 0-90 ns waveform" and "90-170 ns waveform".

##Answers to PRISM QUESTIONS

1) When the controller's current state is "FETCH." what is the status of the following control lines:

a) PCLd--High
b) IRLd--High
c)ACCLd--Low

2)Current state is Decode LoAddr and the IR contains "OUT". What are the control signals that are asserted, and what will the next state be? 

Control signals: AddrSel, Enaccbuffer and Opsel='111'

Next state: Direct IO Execute

3)What are the the status signals sent from the PRISM datapath to the PRISM controller?

-JMP
-JN
-JZ

4)Why is it important that ACCLd signal be active during the execute state for the ADDI instruction?

It is important so that the new sum value can then be able to overwrite whatever present value that the accumulator has.

5)What changes are necessary to the PRISM datapath to add another instruction (SUBI, which would subtract and immediate value from the accumulator) to the instruction set. 

-One can do the 2's complement of the immediate value and then input it into the add function instead.
-A mux can then be used to choose that 2's complement value once a certain signal is of active high. Therefore, allowing us to still be able to use the ADDI instructions

##1st Program Simulation

Program simulated and verified correct by Cpt Sliva, on 17 April 2014.

## 2nd Program Simulation
Program simulated and verified correct by Dr Nibble, on 18 April 2014.

My first simulation failed in a way the countdown was successful but for the countup operation it only count 10, 11, 12 then 20, 21 ,22, then 30 and so on.... after troubleshooting my jumpup codes, I found out a serious error. I placed 2 jmp codes one after another for instruction 1C and 1F, this results in the operation to only run to the jmp for only value  that is 8 and above , while leaving out those 7 and below. 

After experimenting and some discussion with Dr Nibble, the error 'jmp' on instruction 1C was changed into 'JN' as for number 8 and above, since their sign bit will then be one, it will be neg. So it is only right to put 'JN' instead if one want operation to continue with the later codes for 7 and below if value is 7 and below and not jump to the jump9 instructions for value 8 and above.

Only on the second time that i demostrated to Dr Nibble, then the 2nd program counter operation was a success.


Upload the edited ROM file, to show rhe edited codes and upload the prism codes on next friday!!!

