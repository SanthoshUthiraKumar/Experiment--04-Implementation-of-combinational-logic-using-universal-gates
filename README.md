# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate

## Equipments Required:

## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

### Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram
![Combination1LG](https://user-images.githubusercontent.com/119477975/213919758-7629586b-74c6-4747-8d7b-a2ab3a798a6b.jpg)

### Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
![Combination2LG](https://user-images.githubusercontent.com/119477975/213919779-b679ee49-b821-4084-b88a-e1c67859461c.jpg)

## Procedure
```
1.Using NAND Gates and Wires construct F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

2.Construct the same for F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR Gates and Wires

3.Find RTL and Timing Diagram for both the expressions 

4.End the program
```
## Program:
```
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: Santhosh U
RegisterNumber:  22009224

Using NAND Gates

module combin1(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(~c & b & a);
assign q=(~d & c & c & a);
assign r=(c & ~b & a);
assign f=(~(~p & ~q & ~r));
endmodule

Using NOR Gates

module combin2(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(c & ~b & a);
assign q=(d & ~c & a);
assign r=(c & ~b & a);
assign f=~(~(p | q | r));
endmodule
```

## Output:
## RTL realization
### Using NAND Gates
![Combination1RTL](https://user-images.githubusercontent.com/119477975/213916775-59c6e684-4c92-4417-af4c-75c58841cc20.png)

### Using NOR Gates
![Combination2RTL](https://user-images.githubusercontent.com/119477975/213919419-799d1a58-6e82-4516-b8cb-0d3a07b4b99b.png)

## Timing Diagram
### Using NAND Gates
![Combination1Simulation](https://user-images.githubusercontent.com/119477975/213916791-a10d9637-7b7e-45e4-a273-87d9707a743d.png)

### Using NOR Gates
![Combination2Simulation](https://user-images.githubusercontent.com/119477975/213919432-0a740492-fc35-49bf-afae-e30d299a5963.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
