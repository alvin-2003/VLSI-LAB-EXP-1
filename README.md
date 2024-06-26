# VLSI-LAB-EXPERIMENTS
# AIM:
To simulate and synthesis Logic Gates,Adders and Subtractor using Vivado 2023.2.

# APPARATUS REQUIRED: 
  Vivad0 2023.2

# PROCEDURE:
STEP:1 Start the Xilinx navigator, Select and Name the New project. 
STEP:2 Select the device family, device, package and speed. 
STEP:3 Select new source in the New Project and select Verilog Module as the Source type.
STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 
STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. 
STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.
STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained.
STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

# Logic Diagram :

# Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


# Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


# Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


 #Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



# Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



# 8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



# VERILOG CODE:

# FULL ADDER CODE:
```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
```
# #OUTPUT:
# SIMULATION:
![image](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/da22ffe7-f3cc-4dce-9b56-4338676ccabf)
# ELABORATED DESIGN:
![image](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/32f0b070-a80e-45f1-b3cb-a40e85731945)X

# HALF ADDER CODE:
```
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; // sum and carry
or(sum,a,b);
and(carry,a,b);
endmodule
```
# OUTPUT:
# SIMULATION:
![image](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/6898899c-506a-4247-8f29-24c9519ab0d9)
# ELABORATED DESIGN:
![image](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/4c844f64-9255-4427-9519-b1168780cd28)

# FULL SUBRACTOR:
```
// fullsubtractor using gate level modeling
module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
```
# OUTPUT
# SIMULATION:
![image](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/37bdf45b-db0b-49f9-ac15-d85ae9eebaa4)
# ELABORATED DESIGN:
![317327356-72c0bbaf-c51a-43d4-a2b6-c55c73245459](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/c8e64820-5d0b-4bc4-ad15-980e01062773)

# HALF SUBTRACTOR:
```
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule
```
 # OUTPUT
# SIMULATION:
![317337815-4f826bba-c803-46f4-aa12-51a6020a1d02](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/162baea4-60b3-499f-b762-75956c2228cd)
# ELABORATED DESIGN:
![317338139-1646f000-56dc-4944-80c5-dcd15e35ae08](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/c075dfb9-29c1-4814-8a94-df136aa6b3b7)

# LOGIC_GATES: 
```
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
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
```
# OUTPUT:
# SIMULATION:
![317342238-8ea068c7-4870-4224-9def-3b441ca500e8](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/82e74947-77fc-4d9a-a0a2-6f9f25f95470)
# ELABORATED DESIGN:
![317342553-51299302-0ebd-4a71-9047-070d13ce30f8](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/1dcce76a-7793-40ac-b8ba-5c5299fb85ec)

# RIPPLE_CARRY_Adder(4-BIT):-
```
module rippe_adder(S, Cout, X, Y,Cin);
input [3:0] X, Y;// Two 4-bit inputs
input Cin;
output [3:0] S;
output Cout;
wire wl, w2, w3;

fulladder u1(S[0], w1,X[0], Y[0], Cin);
fulladder u2(S[1], w2,X[1], Y[1], w1);
fulladder u3(S[2], w3,X[2], Y[2], w2);
fulladder u4(S[3], Cout,X[3], Y[3], w3);
endmodule
module fulladder(S, Co, X, Y, Ci);
input X, Y, Ci;
output S, Co;
wire w1,w2,w3;
//Structural code for one bit full adder 
xor G1(wl, X, Y);
xor G2(S, w1, Ci);
and G3(w2, w1, Ci);
and G4(w3, X, Y);
or  G5(Co, w2, w3);
endmodule
```
# OUTPUT:
# SIMULATION:
![317347459-5693d20b-dd92-4623-948c-f34d75e15bac](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/5c76be55-d4a5-484f-99dc-10a686647231)
# ELABORATED DESIGN:
![317347282-2fd66ce3-4067-41df-9265-652ac4e07886](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/6402e62e-2b2b-4ec4-916d-62f055ca69db)

# RIPPLE_CARRY_ADDER(8-BIT):-
```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
module rippe_adder(S,Cout,X,Y,Cin);
input [7:0] X,Y;
input Cin;
output [7:0] S;
output Cout;
wire w1,w2,w3,w4,w5,w6,w7;
fulladder u1(S[0],w1,X[0],Y[0],Cin);
fulladder u2(S[1],w2,X[1],Y[1],w1);
fulladder u3(S[2],w3,X[2],Y[2],w2);
fulladder u4(S[3],w4,X[3],Y[3],w3);
fulladder u5(S[4],w5,X[4],Y[4],w4);
fulladder u6(S[5],w6,X[5],Y[5],w5);
fulladder u7(S[6],w7,X[6],Y[6],w6);
fulladder u8(S[7],Cout,X[7],Y[7],w7);
endmodule

module fulladder(S,CO,X,Y,Ci);
input X,Y,Ci;
output S,CO;
wire w1,w2,w3;
xor G1(w1,X,Y);
xor G2(S,w1,Ci);
and G3(w2,X,Ci);
and G4(w3,X,Y);
or G5(CO,w3,w3);
endmodule
```
# OUTPUT:
# SIMULATION:
![317348471-8f2236eb-8ecf-43ca-afe7-38859087f512](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/4770dc7f-c350-45ec-99a2-f8a00c3d9cfc)
# ELABORATED DESIGN:
![317348323-012dabdf-2bca-4a1f-b710-9abece39c8fa](https://github.com/alvin-2003/VLSI-LAB-EXP-1/assets/163816866/daddb44a-d927-4bd0-bff2-a777cffe4b59)


# RESULT:
Thus the Simulation of Logic Gates ,Adders and Subtractors is done and verified.
