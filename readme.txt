DHT11

==========


DHT11 is an [Arduino](http://arduino.cc) library for DHT11 temperature and humidity sensors. 

The code is based on the library by Rob Tilart -  which appears to have an issue with the 
checksum checking.  I have also removed unused code.



Documentation

-------------

Simple example of how to use the library ...


#include <dht.h>

#define DHT11_PIN 7

dht DHT;

void setup() {
  Serial.begin(9600); // Initialize the serial port, set the baud rate into 9600
  Serial.println("UNO is ready!"); // Print the string "UNO is ready!"
}

void loop() {
  int chk = DHT.read(DHT11_PIN);
  switch (chk)
  {
    case DHTLIB_OK: // When read data successfully, print temperature and humidity data
      Serial.print("Humidity: ");
      Serial.print(DHT.humidity);
      Serial.print("%, Temperature: ");
      Serial.print(DHT.temperature);
      Serial.println("C");
      break;
    case DHTLIB_ERROR_CHECKSUM: // Checksum error
      break;
    case DHTLIB_ERROR_TIMEOUT: // Time out error
      Serial.println("Time out error");
      break;
    default: // Unknown error
      Serial.println("Unknown error");
      break;
  }
};






Install

-------


The library can be installed using the [standard Arduino library install procedure](http://arduino.cc/en/Guide/Libraries#.UwxndHX5PtY)  







