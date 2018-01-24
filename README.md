
[![ ADC121C_MQ3](ADC121C_I2CGAS_MQ3.png)](https://store.ncd.io/product/mq-3-alcohol-sensor-adc121c-12-bit-adc-i2c-mini-module/).

#  ADC121C_MQ3
 ADC121C_MQ3 is a MQ-3 Alcohol Sensor.ADC121C is a 12-Bit ADC I2C Mini Module.
This Device is available from www.ncd.io 

[SKU:  ADC121C_MQ3_I2CS]

(https://store.ncd.io/product/mq-3-alcohol-sensor-adc121c-12-bit-adc-i2c-mini-module/)
This Sample code can be used with Arduino.

Hardware needed to interface ADC121C_MQ3 sensor with Arduino

1. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-nano/">Arduino Nano</a>

2. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-micro-with-i2c-expansion-port/">Arduino Micro</a>

3. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-uno/">Arduino uno</a>

4. <a href="https://store.ncd.io/product/dual-i2c-shield-for-arduino-due-with-modular-communications-interface/">Arduino Due</a>

5. <a href="https://store.ncd.io/product/mq-3-alcohol-sensor-adc121c-12-bit-adc-i2c-mini-module/">ADC121C_MQ3 Alcohol Gas Sensor</a>

6. <a href="https://store.ncd.io/product/i%C2%B2c-cable/">I2C Cable</a>

ADC121C_MQ3:

The MQ-3 is capable of sensing air alcohol concentration levels from 0.05mg/L to 10mg/L and also offers a slight sensitivity to Benzene.

Applications:

•They are suitable for alcohol checker, Breathalyser. 

## Arduino
Download and install Arduino Software (IDE) on your machine. Steps to install Arduino are provided at:

https://www.arduino.cc/en/Main/Software

Download (or git pull) the code and double click the file to run the program.
Compile and upload the code on Arduino IDE and see the output on Serial Monitor.

How to Use the ADC121C_MQ3 Arduino Library
The ADC121C_MQ3 has a number of settings, which can be configured based on user requirements.

1.Automatic Conversion mode: When these bits are set to zeros, the automatic conversion mode is disabled. This is the case at power-up.When these bits are set to a non-zero value, the ADC will begin operating in automatic conversion mode.

       mq3.setCycleTime(CYCLE_TIME_32);              // Tconvert x 32, 27 ksps
    
2.Alert Hold:This bit tells the Alert will self clear or not.

   0: Alerts will self-clear when the measured voltage moves within the limits by more than the hysteresis register value.
  
   1: Alerts will not self-clear and are only cleared when a one is written to the alert high flag or the alert low flag in the Alert Status register.

      mq3.setAlertHold(ALERT_HOLD_CLEAR);         // Alerts will self-clear

3.Alert Flag Enable:This bit indicates when an alert condition has occurred. When the Alert Bit Enable is set in the Configuration Register, this bit will be high if either alert flag is set in the Alert Status Register.Otherwise, this bit is a zero.

   0: Disables alert status bit [D15] in the Conversion Result register.
  
   1: Enables alert status bit [D15] in the Conversion Result register.

       mq3.setAlertFlag(ALERT_FLAG_DISABLE);     // Disables alert status bit in the Conversion Result register
       
4.Alert Pin Enable:.

   0: Disables the ALERT output pin. The ALERT output will TRI-STATE when the pin is disabled.
  
   1: Enables the ALERT output pin
  
     mq3.setAlertPin(ALERT_PIN_DISABLE);       // Disables the ALERT output pin

5.Polarity: This bit configures the active level polarity of the ALERT output pin.

   0: Sets the ALERT pin to active low.
 
   1: Sets the ALERT pin to active high
 
      mq3.setPolarity(POLARITY_LOW);        // Sets the ALERT pin to active low
    
6.Output measurement:The following command are used to measure the concentration of alcohal.

  1.Alcohal measurement:The following command is used to measure the alcohal in ppm.
       
        mq3.Measure_Alcoholppm(-0.64, -1.0) * 2.2;  
    
