Task: Membuat diagram closed loop dari salah satu desain sistem kontrol di dunia nyata.

Akan menggunakan Automatic Voltage Regulator (AVR) untuk menunjukkan closed-loop system yang efektif dengan penjelasan komponen yang terdapat pada
kategori 'Controller / Actuator', 'Plant', dan 'Feedback Elements'.

Berikut adalah gambar diagram yang akan digunakan yaitu flowchart closed-loop system:
<img width="790" height="528" alt="SKD Flowchart" src="https://github.com/user-attachments/assets/fbf018a9-52df-4a0f-8a73-30aecd7b7d7b" />


[*] Mengapa closed-loop dipakai dibandingkan open-loop?
Salah satu faktor terbesar mengapa closed-loop system digunakan itu oleh karena komponen umpan balik yang bisa membantu sistem untuk mengkoreksi dirinya sendiri
untuk menghasilkan output yang diinginkan, kebanyakan dari output yang diharapkan tidak terpenuhi oleh karena faktor-faktor eksternal yang diluar kendali dari
sistem, mungkin kalau untuk konteks yang saya berikan yaitu AVR, tentunya dibutuhkan suatu alat atau komponen yang bisa membantu menjaga tegangan untuk tidak mencegah
lonjakan pada suatu power grid, makanya regulasi voltage itu dibutuhkan supaya keseluruhan grid bisa stabil dan bekerja secara efektif (i.e. 24/7 like that).

(Open-loop is not necesarilly bad if compared against closed-loop, it's just the situation that calls for closed-loop)

Berikut adalah gambar diagram untuk flowchart closed-loop system bagi AVR serta referensinya:
<img width="1027" height="1248" alt="SKD Flowchart (1)" src="https://github.com/user-attachments/assets/e3d6b074-1f5a-49fc-a36c-566861b610b7" />

[#] Vref (reference): Ini merupakan nilai tegangan yang diinginkan, biasanya diatur dengan potensiometer atau digital screen pada sistem modern.
[#] Comparator: Komponen ini digambarkan sebagai junction antara input dengan komponen umpan balik yang memiliki fungsi untuk mengurangkan nilai tegangan referensi
                dengan tegangan yang terdeteksi oleh komponen umpan balik untuk memberikan error signal yang membantu menghasilkan tegangan yang semestinya.
[#] Amplifier: Komponen ini berguna untuk menguatkan sinyal galat (error signal) menjadi sinyal kendali dengan besaran yang tepat untuk menggerakan Exciter.
[#] Exciter: Digunakan untuk menyuplai arus medan DC ke rotor generator.
[#] 
