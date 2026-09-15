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

<img width="1027" height="1248" alt="SKD Flowchart (1)" src="https://github.com/user-attachments/assets/a7118efd-06ec-424b-90cd-cc5b03c74e89" />

[#] Vref (reference): Ini merupakan nilai tegangan yang diinginkan, biasanya diatur dengan potensiometer atau digital screen pada sistem modern.
[#] Comparator: Komponen ini digambarkan sebagai junction antara input dengan komponen umpan balik yang memiliki fungsi untuk mengurangkan nilai tegangan referensi dengan tegangan yang terdeteksi oleh komponen umpan balik untuk memberikan error signal yang membantu menghasilkan tegangan yang semestinya.
[#] Amplifier: Komponen ini berguna untuk menguatkan sinyal galat (error signal) menjadi sinyal kendali dengan besaran yang tepat untuk menggerakan Exciter.
[#] Exciter: Digunakan untuk menyuplai arus medan DC ke rotor generator.
[#] Generator: Ini bagian yang berperan sebagai 'Plant' pada sistem ini, dimana energi mekanik dari putaran rotor (yang digerakkan turbine) diubah menjadi energi listrik. Besar tegangan output yang dihasilkan generator ini bergantung langsung sama seberapa besar arus medan yang disuplai Exciter tadi, jadi kalau arus medannya berubah, tegangan yang dihasilkan generator juga otomatis ikut berubah.
[#] Generator Voltage / Terminal Voltage: Ini sebenarnya tegangan yang sama, cuma disebut dengan dua nama tergantung dari sisi mana kita lihat — sebagai 'Terminal Voltage' dia adalah output akhir yang dikirim ke power grid, tapi sebagian dari tegangan yang sama ini juga "disadap" (di-tap) di titik yang sama untuk dijadikan sinyal umpan balik yang nantinya dibandingkan lagi dengan Vref di Comparator, jadi ini titik yang menutup loop-nya. 
[#] Sensor: Bertugas mendeteksi tegangan generator yang nilainya masih dalam skala tegangan tinggi (biasanya berupa potential transformer), supaya bisa diturunkan ke skala yang lebih aman dan bisa diproses lebih lanjut, soalnya nggak mungkin juga tegangan setinggi itu langsung dibandingkan sama Vref yang levelnya jauh lebih kecil. 
[#] Rectifier & Filter: Setelah tegangan diturunkan sama Sensor, sinyal AC tersebut perlu diubah jadi DC dan dihaluskan (di-filter) dulu supaya bentuknya sebanding dan bisa langsung dibandingkan sama Vref di Comparator, kalau sinyalnya masih kotor/noisy nanti hasil perbandingannya jadi kurang akurat.

[*] Jadi kalau ditarik garis besarnya, keseluruhan sistem ini bekerja secara terus-menerus dan siklikal: begitu ada perbedaan antara Vref dengan tegangan generator yang terdeteksi (entah karena naik-turunnya beban di grid atau faktor eksternal lain), Comparator langsung menghasilkan error signal, yang kemudian dikuatkan sama Amplifier, diteruskan ke Exciter buat ngatur arus medan, sampai akhirnya tegangan generator balik lagi mendekati Vref. Proses ini berulang terus tanpa perlu campur tangan manual, makanya closed-loop system kayak gini cocok banget buat aplikasi yang butuh kestabilan real-time kayak AVR ini — balik lagi ke poin di awal soal kenapa closed-loop dipakai.
