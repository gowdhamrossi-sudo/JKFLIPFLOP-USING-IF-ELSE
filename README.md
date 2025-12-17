# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**
```
1.Define Inputs/Outputs: Inputs: J (Set), K (Reset), c1k (clock); Outputs: q, qbar (~q).
2.Initialization: Set q = 0 and qbar = 1 at the start of the simulation.
3.JK Flip-Flop Logic: On posedge c1k, compute q
4.Complementary Output: Update qbar = ~q to maintain complementarity.
5.Testbench: Simulate with combinations of J, K, and c1k to verify JK Flip-Flop functionality.
```
 

**PROGRAM**
```

module exp7(J,K,c1k,q,qbar);
input J,K,c1k;
output reg q;
output reg qbar;
initial q=0;
initial qbar=1;
always @(posedge c1k)
begin
q=((J&(~q)))|((~K)&q);
qbar=~q;
end
endmodule
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by: GOWTHAM M RegisterNumber:25016844
*/

**RTL LOGIC FOR FLIPFLOPS**

<img width="1397" height="767" alt="image" src="https://github.com/user-attachments/assets/aa92f468-c9c3-4168-94ae-ea3dac683a62" />

**TIMING DIGRAMS FOR FLIP FLOPS**

<img width="1557" height="882" alt="image" src="https://github.com/user-attachments/assets/2b90444a-9ca8-4365-a0df-3e8f1886d54b" />


**RESULTS**
Thus the JK flipflop is implemented and verified.


