# VLSI-LAB-EXPERIMENTS-1
# AIM:
To simulate and synthesis Logic Gates,Adders and Subtractor using vivado 2023.2.
# APPARATUS REQUIRED:
vivado 2023.2
# PROCEDURE:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.
Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)

## VERILOG CODE

module logicgate (a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);

input a,b;  

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b); 

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule

## OUTPUT:
![image](https://github.com/vandana9676/VLSI-LAB-EXP-1/assets/165563035/f5d70de4-a23d-4af5-8d22-682d0e06472c)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)

## VERILOG CODE

module half_adder(a,b,sum,carry);

input a,b;

output sum,carry;

xor g1(sum,a,b);

and g2(carry,a,b);

endmodule
## OUTPUT WAVEFORM
![image](https://github.com/vandana9676/VLSI-LAB-EXP-1/assets/165563035/3ae67485-ee10-4e9b-8e82-f0ea815973e6)

Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)
## VERILOG CODE

module fulladder(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

wire w1,w2,w3;

xor(w1,a,b);

xor(sum,w1,c);

and(w2,w1,c);

and(w3,a,b);

or(carry,w2,w3);

endmodule
## OUTPUT WAVEFORM
![image](https://github.com/vandana9676/VLSI-LAB-EXP-1/assets/165563035/627a811a-cb1b-43ee-b832-1089ff6cb580)

Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)

## VERILOG CODE

module halfsub(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor(diff,a,b);

and(borrow,~a,b);

endmodule
## OUTPUT WAVEFORM
![image](https://github.com/vandana9676/VLSI-LAB-EXP-1/assets/165563035/9bb18454-0c3e-4ef0-97a8-d864955e83a9)

Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)

## VERILOG CODE

module fs(a,b,bin,d,bout);

input a,b,bin;

output d,bout;

wire w1,w2,w3;

xor(w1,a,b);

xor(d,w1,bin);

and(w2,~a,b);

and(w3,~w1,bin);

or(bout,w3,w2);

endmodule
## OUTPUT WAVEFORM
![image](https://github.com/vandana9676/VLSI-LAB-EXP-1/assets/165563035/a3bbf5f0-89e6-4c0d-a1e8-8cf4287134ce)

8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)
## VERILOG CODE

module fulladder(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

wire w1,w2,w3;

xor(w1,a,b);

xor(sum,w1,c);

and(w2,w1,c);

and(w3,a,b);

or(carry,w2,w3);

endmodule


module rca_8bit(a,b,cin,s,cout);

input [7:0]a,b;

input cin;

output [7:0]s;

output cout;

wire [7:1]w;

fulladder f1(a[0], b[0], cin, s[0], w[1]);

fulladder f2(a[1], b[1], w[1], s[1], w[2]);

fulladder f3(a[2], b[2], w[2], s[2], w[3]);

fulladder f4(a[3], b[3], w[3], s[3], w[4]);

fulladder f5(a[4], b[4], w[4], s[4], w[5]);

fulladder f6(a[5], b[5], w[5], s[5], w[6]);

fulladder f7(a[6], b[6], w[6], s[6], w[7]);

fulladder f8(a[7], b[7], w[7], s[7], cout);
endmodule
## OUTPUT WAVEFORM:
![image](https://github.com/vandana9676/VLSI-LAB-EXP-1/assets/165563035/175f8550-87bb-4713-b06c-0c8ae984d0df)

## RESULT:
Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .














