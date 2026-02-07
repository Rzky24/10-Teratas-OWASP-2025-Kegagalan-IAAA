# 10-Teratas-OWASP-2025-Kegagalan-IAAA

Apa itu IAAA?
IAAA adalah cara sederhana untuk memahami bagaimana pengguna dan tindakan mereka diverifikasi pada aplikasi. Setiap item memainkan peran penting dan tidak mungkin untuk melewati satu level pun. Artinya, jika item sebelumnya tidak dilakukan, Anda tidak dapat melakukan item berikutnya. Keempat item tersebut adalah:

Identitas - akun unik (misalnya, ID pengguna/email) yang mewakili seseorang atau suatu layanan.
Autentikasi - membuktikan identitas (kata sandi, OTP, kode akses).
Otorisasi - apa yang diizinkan untuk dilakukan oleh identitas tersebut.
Akuntabilitas - pencatatan dan pemberian peringatan tentang siapa melakukan apa, kapan, dan dari mana.
Tiga kategori OWASP Top 10:2025 yang dibahas di ruangan ini berkaitan dengan kegagalan dalam implementasi IAAA . Kelemahan di sini dapat sangat merugikan, karena dapat memungkinkan pelaku ancaman untuk mengakses data pengguna lain atau mendapatkan hak akses lebih dari yang seharusnya.

Jawablah pertanyaan-pertanyaan di bawah ini.
IAAA itu singkatan dari apa?

Identity, Authentication, Authorisation, Accountability

# A01: Kontrol Akses Rusak

Lihat Situs
Kontrol Akses yang Rusak terjadi ketika server tidak menerapkan aturan yang tepat tentang siapa yang dapat mengakses apa pada setiap permintaan. Contoh umum dari hal ini adalah  IDOR (Insecure Direct Object Reference): jika mengubah ID (seperti ?id=7 → ?id=6) memungkinkan Anda untuk melihat atau mengedit data orang lain, maka kontrol akses telah rusak.

Dalam praktiknya, hal ini muncul sebagai eskalasi hak akses horizontal (peran yang sama, akses pengguna lain) atau eskalasi hak akses vertikal (melompat ke tindakan yang hanya dapat dilakukan oleh administrator) karena aplikasi terlalu mempercayai klien.

Buka situs statis yang terkait dengan tugas ini dan mainkan nilai accountIDdi URL-nya. Jadi, Anda dapat mengidentifikasi pengguna mana yang memiliki lebih dari $1 juta di akun mereka!

Jika Anda ingin mempelajari lebih dalam atau variasi lain dari tema ini ( ID yang dikodekan , ID yang di-hash , dll.), pelajari ruangan-ruangan berikut ini:

Kontrol Akses Rusak
Referensi Objek Langsung yang Tidak Aman
Jawablah pertanyaan-pertanyaan di bawah ini.
Jika Anda tidak mendapatkan akses ke lebih banyak peran tetapi dapat melihat data pengguna lain, jenis peningkatan hak akses apa ini?

Horizontal

Apa catatan yang Anda temukan saat melihat akun pengguna yang memiliki lebih dari $1 juta?


<img width="673" height="638" alt="image" src="https://github.com/user-attachments/assets/ad834ad5-cc25-469e-8317-6ad135c08d63" />

THM{Found.the.Millionare!}



# A09: Kegagalan Pencatatan dan Peringatan

Lihat Situs
Ketika aplikasi tidak merekam atau memberi peringatan pada peristiwa yang relevan dengan keamanan, pihak yang bertahan tidak dapat mendeteksi atau menyelidiki serangan. Pencatatan yang baik mendukung akuntabilitas (kemampuan untuk membuktikan siapa yang melakukan apa, kapan, dan dari mana). Dalam praktiknya, kegagalan terlihat seperti hilangnya peristiwa otentikasi, log kesalahan yang tidak jelas, tidak adanya peringatan pada serangan brute-force atau perubahan hak akses, penyimpanan yang singkat, atau log yang disimpan di tempat yang dapat dimanipulasi oleh penyerang.

Mari kita lihat apa yang diperlukan untuk melakukan investigasi terhadap aplikasi yang diserang. Jalankan situs statis yang terlampir pada tugas ini, lakukan investigasi Anda, dan jawab pertanyaan di bawah ini. Kemudian, pikirkan betapa sulitnya memahami apa yang terjadi selama serangan ini jika bagian-bagian penting dari informasi log ini hilang. 

Jika Anda ingin mempelajari lebih lanjut tentang pencatatan untuk akuntabilitas, lihat ruangan ini .

Jawablah pertanyaan-pertanyaan di bawah ini.
Tampaknya penyerang mencoba melakukan serangan brute-force, apa alamat IP penyerang tersebut?

<img width="664" height="561" alt="image" src="https://github.com/user-attachments/assets/10d090e5-abe4-48ee-a71e-d3260f80cbe8" />

203.0.113.45

Memeriksa
Sepertinya mereka berhasil mengakses sebuah akun! Apa nama pengguna yang terkait dengan akun tersebut?

admin

Memeriksa
Tindakan apa yang coba dilakukan penyerang dengan akun tersebut? Sebutkan endpoint yang diakses.


<img width="844" height="636" alt="image" src="https://github.com/user-attachments/assets/856f2384-acaf-4825-8317-79cb64dd99a6" />


/supersecretadminstuff

Memeriksa

Kesimpulan
Anda baru saja mempelajari hal-hal penting tentang Identitas, Otentikasi, Otorisasi, dan Akuntabilitas dalam aplikasi web dan bagaimana hal itu dapat menyebabkan beberapa kategori kerentanan yang dibahas dalam OWASP Top 10:2025. Ide-ide besar yang perlu diingat:

A01 Kontrol Akses yang Rusak: Terapkan pemeriksaan sisi server pada setiap permintaan
A07 Kegagalan Otentikasi: Terapkan indeks unik pada formulir kanonik, batasi laju/blokir serangan brute force, dan rotasi sesi saat terjadi perubahan kata sandi/hak akses.
A09 Pencatatan dan Peringatan Kegagalan: Catat seluruh siklus otentikasi (gagal/berhasil, perubahan kata sandi/2FA/peran, tindakan admin), sentralisasikan log di luar host dengan retensi, dan berikan peringatan jika terjadi anomali (misalnya, serangan brute-force, peningkatan hak akses).
