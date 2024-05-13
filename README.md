# SIMULATE AND SYNTHESIS OF LOGIC GATES ,ADDERS AND SUBTRACTORS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Vivadoo Software

APPARATUS REQUIRED: Vivado™ ML 2023.2

PROCEDURE:

Open Vivado: Launch Xilinx Vivado software on your computer.

Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:
#1:-

FULL_ADDER:-

Code:
```
full adder(code):
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
OUTPUT:

Elaborated Design:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/c00dfa5e-0261-4ac9-8353-264c94e7f3cf)

Simulation:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/d40fd61d-646a-447e-a04a-4b99a4bd2979)

#2:-

FULL_SUBTRACTOR:-

Code:
```
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; // sum and carry
or(sum,a,b);
and(carry,a,b);
endmodule
```
output:
Simulation:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/f6f7e6a6-b0b6-4d2d-8f62-d4d9d80c7345)
Elaborated Design:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/422b68d7-29d5-4266-afa8-8456f05fc359)



#3:-

HALF_ADDER:-

Code:
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
OUTPUT:
Elaborated Design:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/9be2426b-9f03-4e73-860c-d11c94d6e448)
Simulation:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/f57915b9-7669-4ed4-b6f2-d46e1df039e5)



#4 HALF_SUBTRACTOR:-

Code:
```
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

output:
Simulation:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/119024ee-1de3-43d5-8833-3f6a930c9165)

Elaborated Design:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/2779fde7-0015-4282-9560-7c2ad5c403fa)

#5 LOGIC_GATES:-

Code:
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
output:

Simulation:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/41af7ce7-e6af-4281-b556-dcc13dfd1aff)

Elaborated Design:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/e1219f05-ef53-47e7-b5d6-afee83f0eadf)

#6

RIPPLE_CARRY_Adder(4-BIT):-

Code:
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

output:

Simulation:
![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/0d3fe0d1-618a-409f-aae2-85902b15de4c)

Elaborated Design:


![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/c2278b6b-eaf4-4991-9fa2-3901246dc0df)



#7

RIPPLE_CARRY_ADDER(8-BIT):-

Code:
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

output:
Elaborated Design:

![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/2be28cbc-0974-473b-b405-945dade12520)


Simulation:



![image](https://github.com/Nagarajan2003/VLSI-LAB-EXP-1/assets/164840481/f882d103-802e-46df-bf59-d6a062f495c5)







RESULT : The simulation and synthesis of Logic Gates, Adders and Subtractor using Vivadoo Software are successfully verified

