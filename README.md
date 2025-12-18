Laporan Mingguan Job 6

Nama: Arifin Ilham
NPM: 2410017514006
Prodi: TRKJ
Mata Kuliah: LAB IV Basic Analog Electronic


---

1. Tujuan Praktikum

Tujuan dari praktikum ini adalah untuk:

Mengetahui prinsip kerja display seven segment.

Memahami cara menghubungkan seven segment dengan Arduino Uno.

Menampilkan angka pada seven segment menggunakan kode program Arduino.



---

2. Teori

Seven Segment Display (SSD) adalah komponen elektronik yang terdiri dari tujuh buah LED (segment) yang tersusun membentuk angka 8. Dengan menyalakan kombinasi segmen tertentu, kita dapat menampilkan angka 0–9 atau huruf tertentu.

Setiap segmen diberi label dari a hingga g. Tipe seven segment terbagi menjadi dua:

1. Common Cathode (CC) – semua kaki negatif LED disatukan menjadi ground.


2. Common Anode (CA) – semua kaki positif LED disatukan ke VCC (+5V).



Prinsip kerja seven segment adalah menyalakan kombinasi LED tertentu sesuai dengan angka yang ingin ditampilkan. Arduino akan mengatur kondisi HIGH atau LOW pada pin yang terhubung ke masing-masing segmen.

Angka	Segmen yang Menyala

0	a, b, c, d, e, f
1	b, c
2	a, b, d, e, g
3	a, b, c, d, g
4	b, c, f, g
5	a, c, d, f, g
6	a, c, d, e, f, g
7	a, b, c
8	a, b, c, d, e, f, g
9	a, b, c, d, f, g



---

3. Peralatan

Laptop

Arduino Uno

Breadboard

Kabel jumper

Seven Segment Display (1 digit)

Resistor 220Ω – 330Ω (7 buah)

Kabel USB



---

4. Rangkaian Praktikum

Rangkaian terdiri dari satu buah seven segment yang dihubungkan dengan pin digital Arduino.
Setiap segmen dihubungkan melalui resistor pembatas arus ke pin digital Arduino.

Contoh koneksi pin (Common Cathode):

Segmen	Pin Arduino

a	2
b	3
c	4
d	5
e	6
f	7
g	8
COM	GND



---

5. Prosedur Praktikum

Langkah-langkah yang dilakukan dalam praktikum ini:

1. Persiapkan alat dan bahan seperti Arduino Uno, seven segment, resistor, kabel jumper, dan breadboard.


2. Hubungkan setiap segmen seven segment ke pin Arduino melalui resistor sesuai tabel koneksi.


3. Pastikan kaki COM dihubungkan ke GND (untuk Common Cathode).


4. Buka Arduino IDE dan ketik program untuk menyalakan angka 0–9 secara bergantian.


5. Upload program ke Arduino Uno menggunakan kabel USB.


6. Amati hasil tampilan angka di seven segment display.




---

6. Screenshot Prosedur Praktikum




![Image](https://github.com/user-attachments/assets/1087744c-847f-4f2a-9eae-187ff88a4948)



---

7. Source Code Arduino

Berikut contoh source code untuk menampilkan angka 0–9 secara bergantian pada seven segment:

// Deklarasi pin segmen seven segment
int a = 2;
int b = 3;
int c = 4;
int d = 5;
int e = 6;
int f = 7;
int g = 8;

void setup() {
  pinMode(a, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(c, OUTPUT);
  pinMode(d, OUTPUT);
  pinMode(e, OUTPUT);
  pinMode(f, OUTPUT);
  pinMode(g, OUTPUT);
}

void loop() {
  tampil(0); delay(1000);
  tampil(1); delay(1000);
  tampil(2); delay(1000);
  tampil(3); delay(1000);
  tampil(4); delay(1000);
  tampil(5); delay(1000);
  tampil(6); delay(1000);
  tampil(7); delay(1000);
  tampil(8); delay(1000);
  tampil(9); delay(1000);
}

// Fungsi menyalakan kombinasi segmen
void tampil(int angka) {
  // Semua segmen mati dulu
  digitalWrite(a, LOW);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, LOW);
  digitalWrite(e, LOW);
  digitalWrite(f, LOW);
  digitalWrite(g, LOW);

  switch (angka) {
    case 0: digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH); digitalWrite(d, HIGH); digitalWrite(e, HIGH); digitalWrite(f, HIGH); break;
    case 1: digitalWrite(b, HIGH); digitalWrite(c, HIGH); break;
    case 2: digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(d, HIGH); digitalWrite(e, HIGH); digitalWrite(g, HIGH); break;
    case 3: digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH); digitalWrite(d, HIGH); digitalWrite(g, HIGH); break;
    case 4: digitalWrite(b, HIGH); digitalWrite(c, HIGH); digitalWrite(f, HIGH); digitalWrite(g, HIGH); break;
    case 5: digitalWrite(a, HIGH); digitalWrite(c, HIGH); digitalWrite(d, HIGH); digitalWrite(f, HIGH); digitalWrite(g, HIGH); break;
    case 6: digitalWrite(a, HIGH); digitalWrite(c, HIGH); digitalWrite(d, HIGH); digitalWrite(e, HIGH); digitalWrite(f, HIGH); digitalWrite(g, HIGH); break;
    case 7: digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH); break;
    case 8: digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH); digitalWrite(d, HIGH); digitalWrite(e, HIGH); digitalWrite(f, HIGH); digitalWrite(g, HIGH); break;
    case 9: digitalWrite(a, HIGH); digitalWrite(b, HIGH); digitalWrite(c, HIGH); digitalWrite(d, HIGH); digitalWrite(f, HIGH); digitalWrite(g, HIGH); break;
  }
}


---
