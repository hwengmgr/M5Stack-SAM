# M5Stack-SAM

M5Stack-SAM  =  Simple Application Menu  =  a menu system for the M5Stack + also includes applications.

By Tom Such - https://github.com/tomsuch/M5Stack-SAM - Other contributors listed at bottom.
<br />
<br />

**M5Stack-SAM brings MULTI FUNCTIONALITY to the M5Stack !!**

The SAM menu sketch provides access to what would otherwise be multiple single sketches that would need to be loaded one at a time. 
<br />
The Main Menu provides access to three sections: Applications, System, & Configuration.
<br />
<br />

**Applications:**

	DHT12 Sensor display - Temperature / Humidity
	Stopwatch
	I2C scanner
	Bluetooth BLE Beacon Simulator (iBeacon, Eddystone TLM + URL, ALTBeacon)
	QRCode Generator
	GY-512 (MPU6050) - gyro/accelerometer (requires hardware mod + GY-512)
	SerialBridge - PASS-THRU USB <-> UART2
	WiFi Scanner 

**Settings:**
  
	Sleep / Charging Mode
	M5 System Info - CPU Speed, Flash Size, Flash SPEED, SDK Version

**Configuration:**

	Adjust display brightness  
 
 
<br />
<br />

![](Screenshot.png?raw=true)
 
<br />
<br />
<br />

QRCode showing:

	QRPrint("www.google.com");


<br />
SimpleBeacon:

	ble.iBeacon(10,20,50); // ble.iBeacon(MajorCode,MinorCode,Power);
	ble.EddystoneTLM(2048,512,100,1024); // ble.EddystoneTLM(Voltage,Temperature,packetCount,timeSECfromPowerUp);
	ble.EddystoneURIPlain(1,"brmlab.cz",1); // ble.EddystoneURIPlain(prefix,"url.url",Power);
		prefix:
			0	http://www.
			1	https://www.
			2	http://
			3	https://
	ble.AltBeacon();


<br />
Serial commands:

	Serial control at 115200 8N1 and NL&CR termination

	wifiscan - scan for WiFi networks
	
	i2cscan - scan I2C BUS for devices
	
	bright [0-255] - display bright
        	EXAMPLE: bright 128
		
	clr - clear display
	
	sleep - power sleep, wakeup on BTN_B
	
	qrc [text] - show QRCODE with text
		EXAMPLE: qrc www.google.com
	
	Send iBeacone message
	ibeacon [major code 0-65535] [minor code 0-65535] [power 0-255]
		EXAMPLE: ibeacon 1024 2048 50
	
	Send Eddystone TLM message
	eddystonetlm [voltage 0-65535] [temperature 0-65535] [pocket cound 0-4294967295] [second from up 0-4294967295]
		EXAMPLE: eddystonetlm 100 200 300 400

	Send Eddystone URL message
	eddystoneurl [prefix 0-3] [power 0-255] [url]
		EXAMPLE: eddystoneurl 1 1 google.com
		PREFIXES:
			0	http://www.
			1	https://www.
			2	http://
			3	https://		
		
<br />
<br />

Based on:

	https://github.com/Kongduino/M5_QR_Code
	https://github.com/ricmoo/qrcode
	https://github.com/kroimon/Arduino-SerialCommand
	
	
