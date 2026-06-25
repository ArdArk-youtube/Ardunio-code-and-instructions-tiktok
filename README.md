BEFORE YOU READ GO TO THE README.md file ITS EASIER TO READ

First you need these supplies,
MG90 servos:https://www.amazon.com/DIANN-Walking-Helicopter-Airplane-Control/dp/B0DH22MFY4/ref=sr_1_6?sr=8-6
PCA9685 servo driver:https://www.amazon.com/HUAREW-PCA9685-Interface-Compatible-Raspberry/dp/B0CRV3MK14/ref=sr_1_11?sr=8-11
Arduino uno:https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/ref=sr_1_3? sr=8-3
OPTIONAL CHEAPER UNO:https://www.amazon.com/hiBCTR-arduino-uno-Board-Cable/dp/B0FKN4T68T/ref=sr_1_3?sr=8-3
Power supply:https://www.amazon.com/NICE-POWER-Adjustable-Switching-Regulated-Adjustments/dp/B0CDW12H3X/ref=sr_1_7?sr=8-7
Wire:https://www.amazon.com/Fermerry-Stranded-Electric-Tinned-Copper/dp/B089CQHRDT/ref=sr_1_2?sr=8-2
OPTIONAL battery case 6v:https://www.amazon.com/DaierTek-Battery-Holder-Storage-Connector/dp/B09N1GDWQ9/ref=sxin_17_pa_sp_search_thematic_sspa?cv_ct_cx=battery%2B6v&sbo=RZvfv%2F%2FHxDF%2BO5021pAnSA%3D%3D&sr=1-2-0d09cc37-3d68-4cb9-bf15-66a765415250-spons&aref=7Nu6xBzdas&sp_csd=d2lkZ2V0TmFtZT1zcF9zZWFyY2hfdGhlbWF0aWM
OPTIONAL Batterys:https://www.amazon.com/Amazon-Basics-Batteries-Leak-Free-Household/dp/B00NTCH52W/ref=sr_1_1_ffob_sspa?s=electronics&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY

Next,
  Video for assembly:THERE IS NO VIDEO YET. COME BACK LATER FOR UPDATES
Get 4 male to female wires. 

Arduino                              PCA9685
GND <-------------------------------> GND
5v <-------------------------------->VCC
A4 <--------------------------------> SDA
A5 <-------------------------------->SCL

In the demo I am using 4 MG90 servos but any will work.
As you can see, there are 3 colored wires on the servo. Brown, Red, and Orange. Match the Orange wire to the yellow pin on the pca board. Then match the Red wire to the red pin. Finally match the Brown wire to the black pin.
When you are done with that cut 2 wires off of the wire spool. Strip both ends and unscrew the caps on the bottom off the power supply. There will be 1 hole on each side. Plug both wires into the pca board and the power supply and 
screw them in tight.




  Finally,
    Before you run the code you need to install the librarys.
    Step 1, open your arduino IDE. Step 2, go to "sketch" up top when you get to the dropdown go to include>Manage librarys.
    Step 3, At the search bar up top search "adafruit servo driver". After you type that in there should be a bar that pops up and says, Adafruit PWM Servo Driver Library.
    If you hover over it there will be a button that says "instal" press that button. After it installs you can press close.
    Now you are ready to code your arduino! Note if you haven't watched my youtube video you should watch it. It has all the wiring, parts, and tips for this project.
