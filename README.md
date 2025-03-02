## Aim: To design and analyze the MOS differential amplifier circuit for the specifications provoided.
## Design Question:
Design Differential Amplifier for the following specifications **V<sub>dd</sub> = 2.5V**, **P <= 3mW**,**V<sub>ocm</sub> = 1.4V**, **V<sub>p</sub> = 0.5V**,**V<sub>icm</sub> = 1.3V**.\
Perform the DC analysis, Transient Analysuis and AC Analysis and extract\
*DC operating point\
*Gain \
*Bandwidth\
*Vin max & Vin min\
*Frequency response using **LT spice simulation** and replacing the corresponding circuit components and analyzing the 4 circuits respectively.
## Differential Amplifier 
These circuits comprises of 2 symmetrical amplifier circuits clubbed together which are basically CS amplifier with common source resistor circuits which offer high input impedance, higher gain , increase in bandwidth and amplify the differential signals and eliminate the commom mode signals .
Basically there are two types of differential pair circuits namely\
**BJT based differential pair**\
**MOS differential pair circuits**\
MOS differential pair circuits are better than BJT based circuits due to the fact that they offer **higher input impedance, low power consumption ,better matching for integrated circuits, wider common mode input range and scalability for higher frequency application**.
### Common mode signal analysis
![WhatsApp Image 2025-03-02 at 12 53 32_8a598854](https://github.com/user-attachments/assets/43a1e522-c5f6-4bd4-857a-f8f1de7db941)

A common mode input signal is applied to both the mosfets i.e Vin1=Vin2\
**Vin1-Vin2=0(common mode signal in ideal case =0)**\
Both the mosfets **M1=M2** (symmetrical) in nature and also Rd1=Rd.\ Both the mosfets need to be in saturation and the current I<sub>ss</sub> will be equally divided to both the mosfets and hence **I<sub>d1</sub> = I<sub>d2</sub>**.\
**V<sub>gs1</sub> + V<sub>p</sub> < V<sub>icm</sub> < V<sub>dd</sub> - R<sub>d</sub> * I<sub>d</sub> + V<sub>th</sub>**\
In an ideal case the amplifier will be able To reject the common mode signals which are basically the noise signals and the dc signals which are coming from the supply without using a capacitor and hence decreasing the area and eliminating noise as well as dc in the amplified output. And hence the common mode signals gets subtracted.\
**A<sub>v</sub>=(V<sub>o1</sub>-V<sub>o2</sub>)/V<sub>icm</sub>**.Ideal case the common mode gain = 0.\But in practical there is a slight input commmon mode signal and hence is not 0.
This is a common mode signal analysis.
### Differential mode analysis:
Any diifferential signal which is applied in suvh a way that V<sub>in1</sub>>V<sub>in2</sub> which causes the the corresponding current I<sub>d1</sub>>I<sub>d2</sub>.
WKT ** V<sub>dd</sub> = I<sub>d</sub>*R<sub>d</sub>+V<sub>ds</sub>** that implies V<sub>ds</sub> decreases , on the other hand since I<sub>d2</sub> decreases , V<sub>ds</sub> increases and the circuit is self adjusting to changes in differential mode to maintainthe eqilibrium state.\ This happens when the difference is too small and the potential V<su>p</sub> is maintained.
But when the difference betwen V<sub>in1</sub> >>> V<sub>in2</sub>, then the entire currrent I<sub>ss</sub> flows throw the mosfet 1 and the mosfet 2 is off.
If this happens the other way round mosfet 2 is turned on whereas the mosfet1 is turned off.
![WhatsApp Image 2025-03-02 at 14 44 45_34a7f73f](https://github.com/user-attachments/assets/c1100cd6-8e0f-4c2d-8ff3-4e4a895b6873)
 The differential signals add up and get amplified in the circuit which in turn is the output of the differential pair circuit.
 ### Small Signal Model:
![WhatsApp Image 2025-03-02 at 14 42 11_794c5c52](https://github.com/user-attachments/assets/e3da0887-8d28-4eb5-a04d-8aa6f7bea272)
The small signal model verifies that the tail node **P** remains constant in the presence of small diffential inputs and the corresponding small signal gain is given by
**A<sub>v</sub> = g<sub>m</sub> * R<sub>d</sub>** which is also the magnitude of differential mode gain.
### Large Signal Analysis:
WKT **V<sub>in1</sub>-V<sub>in2</sub>=V<sub>id</sub>**\
Also **I<sub>d</sub> = 1/2 k<sub>n</sub> (V<sub>ov</sub>)^2**\
V<sub>idmax</sub>=V<sub>gs1</sub>+ V<sub>p</sub>\
=V<sub>th</sub>+2^1/2V<sub>ov</sub>-V<sub>th</sub>\
= **2^1/2 V<sub>ov</sub>**\
hence  2^1/2* V<sub>ov</sub> < V<sub>idmax</sub> <*2^1/2* V<sub>ov</sub>
![WhatsApp Image 2025-03-02 at 14 44 46_b8d80860](https://github.com/user-attachments/assets/b508694a-33a8-44df-ba78-546373e0d9c2)
## Procedure :
 1. Create a new Experiment file.
 2. Select the nmos4 (2) and change the name as CMOSN.fix the length to 180nm and the width need to be varied as per the aspect ratio calculated with the current equation in the saturation region.
 3. Buid the circuit diagram as per the circuit specifiacations and the calculations made . Make necessary connections required.(Circuit 1 with the source resistor R<sub>ss</sub> )
 4.  Go to spice directive and give the .lib file path for the circuit to access the parameters.  
 5. Go to simulation command , select configure analysis and click on dc operating point .op . Click on Run and observe the DC operation of the circuit and the correspondig DC operating point.
 6. Similarly perform ther transient anaylsis .trans 5m and obseve the response of th circuit to applied sinusoidal input and also the AC analysis , observe the gain and the bandwidth and the frequency response 
 of the circuit and comprehend the same with theoritical calculations. 
 7. Replace the resistor with constan current source and perform the DC ,AC and transient abnalysis . (circuit 2)
 8. Replace the constant current source with a nmos transistor and set the length to 180nm and vary the width to ensure the mosfet operates in saturation and give the biased voltage V<sub>b</sub> as per the calculations . Set the DC operating point and perform the AC analysis and the transient analysis.(Circuit 3)
 9. Replace the other two resistors by a diode connnected pmos transistor and fix the length to 180nm and the corresponding width(to be varied) to get the desired output.Performing the AC and transient analysis as well.(Circuit 4)
 10. Comparing the above 4 circuits as per their response recorded above.
## Calculations:
![WhatsApp Image 2025-03-02 at 16 00 53_0574411c](https://github.com/user-attachments/assets/9f7fc084-941e-48c0-b250-eacc82e20e01)
![WhatsApp Image 2025-03-02 at 16 00 53_b4abf5ad](https://github.com/user-attachments/assets/deafb9fa-7867-4cf4-8cca-c2c4a9daf0ba)







