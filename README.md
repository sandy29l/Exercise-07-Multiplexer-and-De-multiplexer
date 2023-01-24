# Exercise-07-Multiplexer-and-De-multiplexer
AIM: 

To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs

HARDWARE REQUIRED:

– PC, Cyclone II , USB flasher

SOFTWARE REQUIRED: Quartus prime

THEORY

What are Multiplexer and Demultiplexer?

In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

What is a Multiplexer?

The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662](https://user-images.githubusercontent.com/123359969/214306586-b6f4675e-0ff7-4f6a-9a50-4b561f763f7b.png)


Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q” 


![170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5](https://user-images.githubusercontent.com/123359969/214306639-3589b1f0-ec5a-4b6c-aeac-4cc38ac7d89a.png)

Figure2 4X1 multiplexer If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p

What is Demultiplexer?

De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.

![170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d](https://user-images.githubusercontent.com/123359969/214307109-2fceb265-92d0-4fa5-93ce-87e7a4d38b6e.png)


De-multiplexer 1-4 Demultiplexer The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.

![170912683-00fb746a-1d45-4023-91d1-3a70b841073c](https://user-images.githubusercontent.com/123359969/214307149-ea54f8d6-a5f5-4d34-a3e2-d0722d1818a4.png)

![170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9](https://user-images.githubusercontent.com/123359969/214307191-d6f19ce8-b85f-4df9-8704-c7407dccbf25.png)

Figure4 1X4 De-multiplexer The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

Procedure
```
Create a project with required entities.
Create a module along with respective file name for both Multiplexer and De-multiplexer.
Run the module and get the respective RTL outputs.
Create university program(VWF) for getting timing diagram.
Give the respective inputs for timing diagram and obtain the results.
```
PROGRAM
Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: Santhosh L

RegisterNumber: 22008479

4-1 Multiplexer
```
module mux(i0, i1, i2, i3, s0, s1, y);
input i0, i1, i2, i3, s0, s1;
output y;
not(s0c, s0);
nor(s1c, s1);
wire p, q, r, s, s0c, s1c;
and(p, s0c, s1c, i0);
and(q, s0c, s1, i1);
and(r, s0, s1c, i2);
and(s, s0, s1, i3);
or(y, p, q, r, s);
endmodule
```
1-4 Demultiplexer
```
module demux(y0, y1, y2, y3, s0, s1, i);
input s0, s1, i;
output y0, y1, y2, y3;
wire s0c, s1c;
nor(s0c, s0);
nor(s1c, s1);
and(y0, i, s0c, s1);
and(y1, i, s0c, s1c);
and(y2, i, s0, s1c);
and(y3, i, s0, s1);
endmodule
```
RTL LOGIC
Multiplexer RTL

![mux_rtl](https://user-images.githubusercontent.com/123359969/214307431-f15cc4a5-1504-42d4-86d0-570134d501a9.png)


Demultiplexer RTL

![demux_rtl](https://user-images.githubusercontent.com/123359969/214307462-4ebc4e6a-c1c1-4bb2-9aeb-5ac877f71f3c.png)


TIMING DIAGRAMS
Multiplexer Timing Diagram

![mux_td](https://user-images.githubusercontent.com/123359969/214307480-f09eb67b-719f-49dc-bc46-50ad8afbe9e5.png)

Demultiplexer Timing Diagram

![demux_td](https://user-images.githubusercontent.com/123359969/214307494-7d75d0f5-69fd-4dc7-878a-0d2355cae778.png)


TRUTH TABLE
Multiplexer Truth Table

![mux_tt](https://user-images.githubusercontent.com/123359969/214307522-3740ee48-acc7-4d89-b1d2-de83e23c4fb5.png)


Demultiplexer Truth Table

![demux_tt](https://user-images.githubusercontent.com/123359969/214307538-f1e730e8-1efc-4418-b8e8-51cc3d60d538.png)

RESULTS

Thus the implementation of Multiplexer and Demultiplexer are verified
