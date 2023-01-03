<h1 align="center">Laporan Praktikum Sistem Embedded</h1>
<p>Disusun Oleh:</p>

<ul>
  <li>Naufal Faterna Zakky 4.31.20.0.17</li>
</ul>

<h3>Daftar Jobsheet</h3>
<p></p>

<ul>
  <li><a href="https://github.com/naufalzakky/JobSheet1">JobSheet1</a></li>
  <li><a href="https://github.com/naufalzakky/JobSheet1.1">JobSheet1.1</a></li>
  <li><a href="https://github.com/naufalzakky/JobSheet2">JobSheet2</a></li>
  <li><a href="https://github.com/naufalzakky/JobSheet3">JobSheet3</a></li>
  <li><a href="https://github.com/naufalzakky/Nomor1">Nomor 1</a></li>
  <li><a href="https://github.com/naufalzakky/Nomor2">Nomor 2</a></li>
  <li><a href="https://github.com/naufalzakky/Nomor3">Nomor 3</a></li>
  <li><a href="https://github.com/naufalzakky/Nomor4">Nomor 4</a></li>
</ul>

<h2 align="center">Jobsheet 2</h2>
<h3>Coding</h3>
<p>Sentuh LED Menyala</p>
<pre>
<code>
// set pin numbers
const int touchPin = 4; 
const int ledPin = 16;

// change with your threshold value
const int threshold = 20;
// variable for storing the touch pin value 
int touchValue;

void setup(){
  Serial.begin(115200);
  delay(1000); // give me time to bring up serial monitor
  // initialize the LED pin as an output:
  pinMode (ledPin, OUTPUT);
}

void loop(){
  // read the state of the pushbutton value:
  touchValue = touchRead(touchPin);
  Serial.print(touchValue);
  // check if the touchValue is below the threshold
  // if it is, set ledPin to HIGH
  if(touchValue < threshold){
    // turn LED on
    digitalWrite(ledPin, HIGH);
    Serial.println(" - LED on");
  }
  else{
    // turn LED off
    digitalWrite(ledPin, LOW);
    Serial.println(" - LED off");
  }
  delay(500);
}
</code>
</pre>

<p>Sentuh LED Blink</p>
<pre>
<code>
// set pin numbers
const int touchPin = 4; 
const int ledPin = 16;

// change with your threshold value
const int threshold = 20;
// variable for storing the touch pin value 
int touchValue;

void setup(){
  Serial.begin(115200);
  delay(1000); // give me time to bring up serial monitor
  // initialize the LED pin as an output:
  pinMode (ledPin, OUTPUT);
}

void loop(){
  // read the state of the pushbutton value:
  touchValue = touchRead(touchPin);
  Serial.print(touchValue);
  // check if the touchValue is below the threshold
  // if it is, set ledPin to HIGH
  if(touchValue < threshold){
    // turn LED on
    digitalWrite(ledPin, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(500);
    Serial.println(" - LED on");
    digitalWrite(ledPin, LOW);
    delay(500);
    Serial.println(" - LED off");
  }
  else{
    // turn LED off
    digitalWrite(ledPin, LOW);
    delay(500);
    Serial.println(" - LED off");
  }
}

</code>
</pre>

<p>Sentuh LED Running</p>
<pre>
<code>
// set pin numbers
const int touchPin = 4; 
const int ledPin = 16;
const int ledPin1 = 17;
const int ledPin2 = 18;

// change with your threshold value
const int threshold = 20;
// variable for storing the touch pin value 
int touchValue;

void setup(){
  Serial.begin(115200);
  delay(1000); // give me time to bring up serial monitor
  // initialize the LED pin as an output:
  pinMode (ledPin, OUTPUT);
  pinMode (ledPin1, OUTPUT);
  pinMode (ledPin2, OUTPUT);
}

void loop(){
  // read the state of the pushbutton value:
  touchValue = touchRead(touchPin);
  Serial.print(touchValue);
  // check if the touchValue is below the threshold
  // if it is, set ledPin to HIGH
  if(touchValue < threshold){
    // turn LED on
    digitalWrite(ledPin, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    digitalWrite(ledPin1, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin2, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin1, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    digitalWrite(ledPin2, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin1, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin2, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin1, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin2, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin1, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    digitalWrite(ledPin2, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    delay(500);                       // wait for a second
    digitalWrite(ledPin, HIGH);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED on");
    digitalWrite(ledPin1, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    digitalWrite(ledPin2, LOW);   // turn the LED on (HIGH is the voltage level)
    Serial.println(" - LED off");
    delay(500);                       // wait for a second
  }
  else{
    // turn LED off
    digitalWrite(ledPin, LOW);
    Serial.println(" - LED off");
    digitalWrite(ledPin1, LOW);
    Serial.println(" - LED off");
    digitalWrite(ledPin2, LOW);
    Serial.println(" - LED off");
  }
  delay(500);
}

</code>
</pre>

<p>Sensor DHT LED Menyala</p>
<pre>
<code>
// REQUIRES the following Arduino libraries:
// - DHT Sensor Library: https://github.com/adafruit/DHT-sensor-library
// - Adafruit Unified Sensor Lib: https://github.com/adafruit/Adafruit_Sensor
#include "DHT.h"
#define DHTPIN 4 // Digital pin connected to the DHT sensor
// Uncomment whatever type you're using!
#define DHTTYPE DHT11 // DHT 11
//#define DHTTYPE DHT22 // DHT 22 (AM2302), AM2321
//#define DHTTYPE DHT21 // DHT 21 (AM2301)
DHT dht(DHTPIN, DHTTYPE);
void setup() {
Serial.begin(9600);
Serial.println(F("DHT11 Embedded System Test!"));
dht.begin();
}
void loop() {
// Wait a few seconds between measurements.
delay(2000);
// Reading temperature or humidity takes about 250 milliseconds!
// Sensor readings may also be up to 2 seconds 'old' (its a very slow sensor)
float h = dht.readHumidity();
// Read temperature as Celsius (the default)
float t = dht.readTemperature();
// Read temperature as Fahrenheit (isFahrenheit = true)
float f = dht.readTemperature(true);
// Check if any reads failed and exit early (to try again).
if (isnan(h) || isnan(t) || isnan(f)) {
Serial.println(F("Failed to read from DHT sensor!"));
return;
}
// Compute heat index in Fahrenheit (the default)
float hif = dht.computeHeatIndex(f, h);
// Compute heat index in Celsius (isFahreheit = false)
float hic = dht.computeHeatIndex(t, h, false);
Serial.print(F("Humidity: "));
Serial.print(h);
Serial.print(F("% Temperature: "));
Serial.print(t);
Serial.print(F("°C "));
Serial.print(f);
Serial.print(F("°F Heat index: "));
Serial.print(hic);
Serial.print(F("°C "));
Serial.print(hif);
Serial.println(F("°F"));
}

</code>
</pre>

<p>RFID</p>
<pre>
<code>
#include <SPI.h>
#include <MFRC522.h>
#define SS_PIN 21 // ESP32 pin GIO21
#define RST_PIN 22 // ESP32 pin GIO22
MFRC522 rfid(SS_PIN, RST_PIN);
byte keyTagUID[4] = {0xE3, 0x1A, 0xD6, 0x03};
void setup() {
Serial.begin(9600);
SPI.begin(); // init SPI bus
rfid.PCD_Init(); // init MFRC522
Serial.println("Tap RFID/NFC Tag on reader");
}
void loop() {
if (rfid.PICC_IsNewCardPresent()) { // new tag is available
if (rfid.PICC_ReadCardSerial()) { // NUID has been readed
MFRC522::PICC_Type piccType = rfid.PICC_GetType(rfid.uid.sak);
if (rfid.uid.uidByte[0] == keyTagUID[0] &&
rfid.uid.uidByte[1] == keyTagUID[1] &&
rfid.uid.uidByte[2] == keyTagUID[2] &&
rfid.uid.uidByte[3] == keyTagUID[3] ) {
Serial.println("Access is granted");
}
else
{
Serial.print("Access denied for user with UID:");
for (int i = 0; i < rfid.uid.size; i++) {
  Serial.print(rfid.uid.uidByte[i] < 0x10 ? " 0" : " ");
Serial.print(rfid.uid.uidByte[i], HEX);
}
Serial.println();
}
rfid.PICC_HaltA(); // halt PICC
rfid.PCD_StopCrypto1(); // stop encryption on PCD
}
}
}

</code>
</pre>


<h3>Hasil</h3>

