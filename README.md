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
## Common mode signal analysis
![WhatsApp Image 2025-03-02 at 12 53 32_8a598854](https://github.com/user-attachments/assets/43a1e522-c5f6-4bd4-857a-f8f1de7db941)

A common mode input signal is applied to both the mosfets i.e Vin1=Vin2\
**Vin1-Vin2=0(common mode signal in ideal case =0)**\
Both the mosfets **M1=M2** (symmetrical) in nature and also Rd1=Rd.\ Both the mosfets need to be in saturation and the current I<sub>ss</sub> will be equally divided to both the mosfets and hence **I<sub>d1</sub> = I<sub>d2</sub>**.\
**V<sub>gs1</sub> + V<sub>p</sub> < V<sub>icm</sub> < V<sub>dd</sub> - R<sub>d</sub> * I<sub>d</sub> + V<sub>th</sub>**\
In an ideal case the amplifier will be able To reject the common mode signals which are basically the noise signals and the dc signals which are coming from the supply without using a capacitor and hence decreasing the area and eliminating noise as well as dc in the amplified output. And hence the common mode signals gets subtracted.\
**A<sub>v</sub>=(V<sub>o1</sub>-V<sub>o2</sub>)/V<sub>icm</sub>**.Ideal case the common mode gain = 0.\But in practical there is a slight input commmon mode signal and hence is not 0.
This is a common mode signal analysis.
## Differential mode analysis:
Any diifferential signal which is applied in suvh a way that V<sub>in1</sub>>V<sub>in2</sub> which causes the the corresponding current I<sub>d1</sub>>I<sub>d2</sub>.
WKT ** V<sub>dd</sub> = I<sub>d</sub>*R<sub>d</sub>+V<sub>ds</sub>** that implies V<sub>ds</sub> decreases , on the other hand since I<sub>d2</sub> decreases , V<sub>ds</sub> increases and the circuit is self adjusting to changes in differential mode to maintainthe eqilibrium state.\ This happens when the difference is too small and the potential V<su>p</sub> is maintained.
But when the difference betwen V<sub>in1</sub> >>> V<sub>in2</sub>, then the entire currrent I<sub>ss</sub> flows throw the mosfet 1 and the mosfet 2 is off.
If this happens the other way round mosfet 2 is turned on whereas the mosfet1 is turned off.
![WhatsApp Image 2025-03-02 at 14 44 45_34a7f73f](https://github.com/user-attachments/assets/c1100cd6-8e0f-4c2d-8ff3-4e4a895b6873)
 The differential signals add up and get amplified in the circuit which in turn is the output of the differential pair circuit.
 ## small signal model:
![WhatsApp Image 2025-03-02 at 14 42 11_794c5c52](https://github.com/user-attachments/assets/e3da0887-8d28-4eb5-a04d-8aa6f7bea272)
The small signal model verifies that the tail node **P** remains constant in the presence of small diffential inputs and the corresponding small signal gain is given by
**A<sub>v</sub> = g<sub>m</sub> * R<sub>d</sub>** which is also the magnitude of differential mode gain.

