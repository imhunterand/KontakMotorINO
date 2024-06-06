# KontakMotorINO
Proyek Kontak Motor Menggunakan Arduino

<h3>Deskripsi:</h3>
Proyek ini adalah tentang membuat sistem kontak motor sederhana menggunakan Arduino. Dengan proyek ini, Anda dapat menghidupkan atau mematikan motor menggunakan tombol push-button yang terhubung ke Arduino. Ketika tombol ditekan, motor akan menyala, dan ketika tombol dilepaskan, motor akan mati. Selain itu, Anda juga bisa menambahkan fitur lain seperti LED indikator atau buzzer untuk memberikan sinyal bahwa motor sedang menyala.

## Requirements:
  * Arduino Uno
  * Motor DC
  * Driver Motor (L298N atau L293D) 
  * Tombol push-button
  * Resistor 10k ohm
  * Breadboard dan kabel jumper
  * Power supply (baterai atau adaptor DC)

## Installation Commands
 1. Persiapan Komponen:
    * Pastikan Anda memiliki semua komponen yang dibutuhkan.
    * Hubungkan Arduino ke komputer Anda menggunakan kabel USB.
 1. Rangkaian:
    * Motor dan Driver Motor:
     * Sambungkan pin IN1 dari driver motor ke pin digital 8 di Arduino.
     * Sambungkan pin IN2 dari driver motor ke pin digital 9 di Arduino.
     * Sambungkan pin ENA dari driver motor ke pin digital 10 di Arduino.
     * Sambungkan terminal motor ke OUT1 dan OUT2 dari driver motor.
     * Sambungkan pin VCC dari driver motor ke pin 5V di Arduino.
     * Sambungkan pin GND dari driver motor ke pin GND di Arduino.
  1. Tombol Push-Button:
     * Sambungkan satu kaki push-button ke pin digital 2 di Arduino.
     * Sambungkan kaki lainnya ke GND melalui resistor 10k ohm.
     * Sambungkan titik tengah antara resistor dan push-button ke 5V.

  1. Source program:
     * Buka Arduino IDE dan tulis kode berikut:
```cpp
const int motorPin1 = 8;
const int motorPin2 = 9;
const int enablePin = 10;
const int buttonPin = 2;

void setup() {
  pinMode(motorPin1, OUTPUT);
  pinMode(motorPin2, OUTPUT);
  pinMode(enablePin, OUTPUT);
  pinMode(buttonPin, INPUT);
  
  digitalWrite(enablePin, LOW);
}

void loop() {
  int buttonState = digitalRead(buttonPin);
  
  if (buttonState == HIGH) {
    digitalWrite(enablePin, HIGH);
    digitalWrite(motorPin1, HIGH);
    digitalWrite(motorPin2, LOW);
  } else {
    digitalWrite(enablePin, LOW);
    digitalWrite(motorPin1, LOW);
    digitalWrite(motorPin2, LOW);
  }
}
```
  5. Upload code:
     * Sambungkan Arduino ke komputer menggunakan kabel USB.
     * Pilih port yang sesuai di Arduino IDE.
     * Klik tombol upload untuk mengunggah kode ke Arduino.
  6. Pengujian:
     * Setelah kode diunggah, coba tekan tombol push-button.
     * Motor seharusnya menyala ketika tombol ditekan dan mati ketika tombol dilepas.
     * Anda bisa menambahkan LED pada pin yang tersisa dan mengatur kode untuk menyalakan LED saat motor aktif.

       
# Credit's
**[Imhunterand](https://github.com/imhunterand)** Cyber Security Research
