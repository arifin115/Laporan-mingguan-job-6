Laporan Mingguan Job 6

Nama: Arifin Ilham
NPM: 2410017514006
Prodi: TRKJ
Mata Kuliah: LAB IV Basic Analog Electronic


---

1. Tujuan Praktikum

Tujuan dari praktikum ini adalah untuk:

Mengetahui cara kerja sensor cahaya LDR (Light Dependent Resistor).

Memahami cara kerja Arduino dalam membaca intensitas cahaya melalui LDR.

Menguji hubungan antara perubahan cahaya dengan nilai tegangan output sensor LDR.

Menampilkan hasil pembacaan sensor LDR pada Serial Monitor Arduino.



---

2. Teori

LDR (Light Dependent Resistor) adalah resistor yang nilai hambatannya berubah sesuai dengan intensitas cahaya yang diterimanya. Semakin besar cahaya yang diterima, maka hambatannya semakin kecil. Sebaliknya, jika cahaya yang diterima berkurang, hambatannya meningkat.

LDR banyak digunakan dalam sistem otomatis seperti lampu taman otomatis, alarm cahaya, dan sistem penghemat energi.

Karakteristik LDR:

Hambatan tinggi pada kondisi gelap (hingga megaohm).

Hambatan rendah pada kondisi terang (beberapa kiloohm).

Bersifat non-linear (respon tidak selalu proporsional terhadap intensitas cahaya).


Prinsip Kerja:

LDR dihubungkan dalam rangkaian pembagi tegangan dengan resistor tetap.

Tegangan output dari titik tengah pembagi tegangan dibaca oleh pin analog Arduino.

Nilai tegangan ini digunakan untuk menentukan tingkat pencahayaan.


Rumus pembagi tegangan:

V_{out} = V_{in} \times \frac{R_{LDR}}{R_{LDR} + R_{fixed}}


---

3. Peralatan

Laptop

Board Arduino Uno

Breadboard

Kabel jumper

Sensor LDR

Resistor 10kΩ

Kabel USB Arduino



---

4. Rangkaian Praktikum

Konfigurasi Pin LDR:

Salah satu kaki LDR dihubungkan ke VCC (5V)

Kaki lainnya dihubungkan ke pin A0 Arduino dan resistor 10kΩ

Ujung resistor 10kΩ dihubungkan ke GND


Rangkaian ini membentuk pembagi tegangan, di mana tegangan tengah (Vout) akan berubah mengikuti intensitas cahaya yang diterima oleh LDR.


---

5. Prosedur Praktikum

1. Siapkan semua komponen: Arduino Uno, kabel USB, LDR, resistor 10kΩ, breadboard, dan kabel jumper.


2. Rangkai LDR dan resistor membentuk pembagi tegangan sesuai skema.


3. Hubungkan pin tengah (Vout) ke pin analog A0 pada Arduino.


4. Buka Arduino IDE, lalu buat dan upload program pembacaan intensitas cahaya.


5. Buka Serial Monitor untuk melihat hasil pembacaan nilai analog dari LDR.


6. Uji sensor dengan menutup atau menyinari LDR untuk melihat perubahan nilai pembacaan.




---

6. Screenshot Prosedur Praktikum


![Image](https://github.com/user-attachments/assets/1087744c-847f-4f2a-9eae-187ff88a4948)


---

7. Source Code Arduino

Berikut contoh program untuk membaca intensitas cahaya dari sensor LDR dan menampilkannya pada Serial Monitor:

// Deklarasi pin untuk LDR
const int LDRPin = A0;

void setup() {
  // Memulai komunikasi serial dengan baud rate 9600
  Serial.begin(9600);
}

void loop() {
  // Membaca nilai analog dari pin A0
  int sensorValue = analogRead(LDRPin);

  // Mengonversi nilai analog ke tegangan (0-5V)
  float voltage = sensorValue * (5.0 / 1023.0);

  // Menampilkan nilai sensor dan tegangan
  Serial.print("Nilai LDR: ");
  Serial.print(sensorValue);
  Serial.print("  | Tegangan: ");
  Serial.print(voltage);
  Serial.println(" V");

  // Jeda 1 detik sebelum pembacaan berikutnya
  delay(1000);
}


---

8. Hasil Pengamatan

Kondisi Cahaya	Nilai Analog	Tegangan (V)	Keterangan

Terang	850	4.15	Cahaya kuat
Redup	400	1.95	Cahaya sedang
Gelap	100	0.49	Hampir tidak ada cahaya



---

9. Kesimpulan

Dari hasil praktikum ini dapat disimpulkan bahwa:

Nilai output sensor LDR berubah sesuai dengan intensitas cahaya yang diterima.

Semakin terang cahaya, semakin besar nilai output analog yang terbaca Arduino.

Rangkaian LDR dan resistor bekerja sebagai pembagi tegangan yang responsif terhadap perubahan intensitas cahaya.

Arduino dapat digunakan untuk mengukur intensitas cahaya dan menjadi dasar sistem otomatisasi berbasis sensor.
