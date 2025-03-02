## Aim: To design and analyze the MOS differential amplifier circuit for the specifications provided.
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
**A<sub>v</sub> =g<sub>m</sub>*R<sub>d</sub>**\
=2*I<sub>d</sub>/V<sub>ov</sub>= 2*0.6*10^-3/(0.8-0.366)*1.8339*10^3\
= 5.07=20log(5.07)= 14.11dB
## Observations:
## Circuit 1:
### Circuit Diagram :
![WhatsApp Image 2025-03-02 at 20 35 29_891bee8f](https://github.com/user-attachments/assets/58a5abfe-0fc3-4ec4-8f2b-9c2b9b65ba9e)
### DC Analysis:
![{5D3CE92C-F171-4FF1-BCAE-7EF3B10D8D5F}](https://github.com/user-attachments/assets/5f4b8816-58d1-4a74-b41b-7fa8db234db7)
length =180nm, width=7.65um \
The width is varied and the length is fixed to get the desired vout = 1.4 V.This ensures the mosfet operates in saturation and steady state operation.
If the other parameters are kept constant and the input biased voltage is slightly varied by +/-0.15V, i.e 1.45 or to 1.25 V ,the corresponding vriation in Vout and I<sub>d</sub> can be seen as follows.\
![{64B6AA68-18CC-4ECD-B708-3EEF2D158389}](https://github.com/user-attachments/assets/45f8b8ad-dc35-4f22-a06f-3dc4255022bc)
**Fig : V<sub>incm</sub>  1.45V ,  V<sub>ocm</sub>=1.18V, I<sub>d</sub>=0.71mA ,I<sub>rss</sub>=1.43mA**\
When the voltage is increased, the effective output commom voltage decreases whereas the current through each of the mosfet increases which is justified by the dependency of current on V<sub>gs</sub> value according to the square law relationship.
![{2E5FED8C-EB9C-42F4-BED5-4A2FFB80C2A1}](https://github.com/user-attachments/assets/c49b0a04-35df-44cb-80f3-e1b4370bef3e)
**Fig: V<sub>incm</sub>  1.25V ,  V<sub>ocm</sub>=1.47V, I<sub>d</sub>=0.56mA ,I<sub>rss</sub>=1.1mA**\
As the value of inputcommon mode voltage is decreased the effective output voltage increases an the corresponding value of current through each mosfet is decreased which again is justified by te square law relationship and V<sub>o1</sub> = V<sub>dd</sub>-Id*Rd , as the current decreases , v<sub>o</sub> increases which can be obseved during the simulation.
### AC Analysis :
![image](https://github.com/user-attachments/assets/6ab00382-f951-4130-af34-95a40b113fd1)
Gain of the circuit = 13.8dB which is very close to that of theoritical value of 14.01 dB and the corresponding bandwidth is 134.27 MHz .There is significant increase in the gain as comparedto that of normal CS amplifier circuit and increase in the range of linear operation of the circuit.
### Transient analysis:
![image](https://github.com/user-attachments/assets/2d94b071-e34d-4331-8534-2da9c63bd3e6)
There is 180 degree phase shift between input and output with amplified otput by a factor of Vout/Vin=1.625/1.35=1.20.
i.e The output is 1.20 times amplified than input.\
## Circuit 2 :
When the resistor is replaced by a constant current source.\
### Circuit Diagram:
![{75CA2FBC-03E4-4064-9579-BD87C8501563}](https://github.com/user-attachments/assets/74dc62af-c0cd-4718-baef-275240171830)
### DC Analysis:
![{CDDE4870-D8EF-424E-BD9A-56E8617576CD}](https://github.com/user-attachments/assets/3762c684-1bd6-42d5-b639-f7f657390fd8)
There is no much variation in the operating point and stability is maintained.All the other parameters are kept constant and the current flowing is equally distributed between each of the mosfets,i.e 0.6mA and Vout=1.399V.
### AC Analysis:
![image](https://github.com/user-attachments/assets/a18f7a73-324f-45c8-b285-fa51ca38cb9c)
The gain remains constant as there is no variatin in gm as well as Rd but there is increase in the bandwidth to 505.9 MHz which is significantly large as compared to the previous circuit.
### Transient Analysis:
![image](https://github.com/user-attachments/assets/013dd688-5134-409b-8240-60fb10b85588)
There is 180 degree phase shift betweeen input and output and the differential input signal is amplified by a factor of 1.624/1.347= 1.205 and the response ,i.e time varied response is observed.










