BEFORE YOU READ GO TO THE README.md file ITS EASIER TO READ. PRESS CODE

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
Get 4 male to female wires. SEE "PIC 1" on main branch

Arduino                              PCA9685
GND <-------------------------------> GND
5v <-------------------------------->VCC
A4 <--------------------------------> SDA
A5 <-------------------------------->SCL

In the demo I am using 4 MG90 servos but any will work.
As you can see, there are 3 colored wires on the servo. Brown, Red, and Orange. Match the Orange wire to the yellow pin on the pca board. Then match the Red wire to the red pin. Finally match the Brown wire to the black pin. See "Pic4".
When you are done with that cut 2 wires off of the wire spool. Strip both ends and unscrew the caps on the bottom off the power supply. See "pic 2" and "Pic 3"  .
There will be 1 hole on each side. Plug both wires into the pca board and the power supply and screw them in tight. See "pic5". 
There are some tricky things you should know about when you are using this power supply.  The first is, you have to turn the output on. See "pic6".If this button isn’t pressed, the watts will say “off” and it won’t supply any power.  When you adjusting the voltages its a good idea to keep this turned off in case you accidentally turn it too high.

The other tricky thing is that you adjust both the maximum voltage and the maximum current with these power supplies.  First, turn the voltage to 5 volts. "See pic7". But now let’s turn it on and see what happens.  You see the servos don’t move.  That’s because the maximum amount of current is set too low.  They draw more current then we’re allowing, so the power supply will dip the voltage below five to keep it from sending too much current.  You can see this light is lit up, “CC”, meaning that it is current limited.  So now adjust this current knob up, and you’ll notice that sometimes it can stay up at 5, sometimes it dips. If you keep adjusting up, it will always be at 5.  The “CC” light goes out and the “CV” light comes on, so now it is keeping a constant 5 volts.  And you can see the servos are working normally.  Now, if you use batteries, this isn’t a problem, but you have to replace the batteries all the time so I like using the power supply.

Optinal read. Code explanation:
Let’s go through this code to understand it.

The first line includes a library called wire.h.  This library lets you communicate with other devices using the i2c protocol.  You need this so you don’t have to write that from scratch, you can just use it to send commands to the PCA9685 servo driver board.

The next line includes a library called Adafruit_PWMServoDriver.h.  This library has the code that makes the pulses the correct shape to control the servo, so all you have to do is put in where you want the servo to be and not worry about pulse widths and that stuff.  It makes it easy.

So now you are going to create a variable called pwm.  The type of variable is a Adafruit_PWMServoDriver.  That’s a big word but this is just a data type, like an integer is a data type.  Its a servo driver.  So pwm will equal this function, Adafruit_PWMServoDriver();, which gives you a servo driver.

So that’s your driver, it’s called pwm, and when you want to do things, you call pwm’s functions.

Now we’re just going to define the limits of the servo as 150 and 600.  So now instead of writing 150 or 600 over and over again, you can just use servomin and servomax, and if you need to change them, you just change it in one place and not all over the place.

The next section is the setup section.  This will run only once, when the arduino turns on.  We run two commands here, to initialize pwm, tell it to start up with the begin() command, then we set the frequency that it will use to communicate with the servo at 600.  You don’t really want to change anything in this section.

The next part is the loop that will run over and over and over as long as the arduino is on.  First there is a for loop, which will run 4 times, and will set servos 0 through 3 to the max.  The first argument is the servo number, the second argument is when to turn the pulse on, and the third argument is when to turn the pulse off.  The servo will move depending on how long the pulse is, so when you make it shorter it will move one direction and when you make it longer it will move the other direction.

After it has changed it for all four, it delays.  Then it makes the pulse width shorter, delays again, and then repeats.  So this just moves back and forth.





  Finally,
    Before you run the code you need to install the librarys.
    Step 1, open your arduino IDE. Step 2, go to "sketch" up top when you get to the dropdown go to include>Manage librarys.
    Step 3, At the search bar up top search "adafruit servo driver". After you type that in there should be a bar that pops up and says, Adafruit PWM Servo Driver Library.
    If you hover over it there will be a button that says "instal" press that button. After it installs you can press close.
    Now you are ready to code your arduino!
