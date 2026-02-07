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



