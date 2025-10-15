
# How reading from each power analyzer works:
When connected to a computer with an RS232 USB adapter, the power analyzer will be assigned a port (COM8, ttyUSB0, etc.). Use this line to setup the power analyzer in python:
`serial.Serial(port=COM##, baudrate=115200,timeout=3,dsrdtr=True)`
## 2802:
1. Send the 2802 a query string with all of the quantities you want ("read=DATE,TIME,volts[a],amps[a],watts[a]\n")
2. Send the 2802 just the string "READ?\n"
3. Receive the measurement from the 2802 as a comma separated list
## xt2640:
1. Send the xt2640 a query string with the READ command AND the quantities you want ("READ?,V:CH1:RMS,A:CH1:RMS,W:CH1:RMS")
2. Receive the measurement from the xt2640 as a comma separated list
