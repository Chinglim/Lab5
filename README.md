Lab5
====
##1st Program Operation

7(Hexadecimal) is the op code for LDAI, it will load the value of the operand into the accumulator. In the next address, 8(hexadecimal) is seen, that will be the operand value, to be loaded into the accumulator. 

At address 02, '6'(hexadecimal) is the opcode for ADDI, it means add the value of the operand to the number in the accumulator. Since '1'(hexadecimal) is on the next address, the operation will be that 1 will be added to the current accumulator value, '8' to generate a '9'(hexadecimal).

As in the address 04, '4' is seen, it is ithe opcode for transferring the data from the accumulator to the selected output port. The output port number is as display on address 05 . Therefore, the value '9' hexadecimal will be output on port 3 .

At address 06, 'B' (hexadecimal) is seen, it is the opcode to jump to the operand address if the accumulator has a negative number. Since '9'(hexadeciaml) has a sign bit of 1 which means it is a negative number, it JN function will be carried out and back to address 02 instruction again.

Apparently, this program will output values that is going up sequentially, out of port 3, as long as the post addition value is within '8'-'F' hexadecimal value. This is because for this range of number, their sign bit is '1', which meant that they are negative number , so the jump function to carry out the plus 1 will be carried out.

This process will just end when the accumulator value reads 0 as the sign bit of the hexdecimal number.
