# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */

**PROGRAM**
```
module Exp7(q, clk, reset);

output [3:0] q;
input clk, reset;

T_FF tff0(q[0], clk, reset);
T_FF tff1(q[1], q[0], reset);
T_FF tff2(q[2], q[1], reset);
T_FF tff3(q[3], q[2], reset);

endmodule


module T_FF(q, clk, reset);

output q;
input clk, reset;

wire d;

D_FF dff0(q, d, clk, reset);

not n1(d, q);

endmodule


module D_FF(q, d, clk, reset);

output q;
input d, clk, reset;

reg q;

always @(negedge clk or posedge reset)
begin
    if (reset)
        q = 1'b0;
    else
        q = d;
end

endmodule
```
/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.
```
 Developed by: siva prasath
 RegisterNumber: 212225040417
```
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="1917" height="1078" alt="651904773-64f74095-7bb9-4ea3-a894-5029baeacfcc" src="https://github.com/user-attachments/assets/f3f9352c-78b5-4d55-953b-ada0b5a7f90f" />

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="1915" height="1134" alt="651904916-7a8be2f4-d904-4a4c-a7fd-250328248ab8" src="https://github.com/user-attachments/assets/77ee20ad-6ebb-42f6-82aa-6f2e933029b6" />





**RESULTS**
