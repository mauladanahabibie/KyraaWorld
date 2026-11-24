# Master Prompt KyraaAI: Dunia Agen 3D Hidup \& Ruang Kolaborasi Multi-Agen

Salin seluruh prompt di bawah garis pemisah untuk membangun aplikasi **KyraaAI** dari nol. Nama pemilik yang dipakai di seluruh aplikasi adalah **Danzz**; ganti dengan nama panggilanmu sendiri bila perlu. Endpoint model sendiri (format kompatibel OpenAI) bersifat **opsional** dan dimasukkan lewat panel Pengaturan Engine di dalam aplikasi; jika belum punya, seluruh agen langsung berjalan memakai model bawaan (agen dari Muse) tanpa mengunci fitur apa pun.

---

Buatkan aplikasi web fullstack interaktif bernama **KyraaAI** yang menggabungkan dua ruang yang saling terhubung secara langsung:

1. **Dunia 3D Hidup (Living Agent World)** seukuran layar penuh tempat para agen AI bekerja, berjalan kaki, rapat, ngopi, dan berinteraksi di sebuah pulau kampus berarsitektur hangat.
2. **Ruang Obrolan \& Kerja Multi-Agen** tempat aku sebagai pemilik berdiskusi dengan seluruh agen, memantau tugas per proyek, melihat agen saling mengobrol satu sama lain, dan berbicara empat mata dengan agen mana pun.

Aku adalah pemilik ruang dan kampus ini. Di seluruh antarmuka, header, log aktivitas, avatar pemain 3D, dan balon chat, tulis label pemilik memakai `Danzz`. Jangan pernah memakai kata `"Kamu"` sebagai nama tampil pemilik.

## 1. Struktur Tim \& Karakter Agen KyraaAI

Terdapat 1 pemilik `Danzz` dan 7 kursi agen inti KyraaAI, ditambah dukungan opsional untuk agen penghuni eksternal. Setiap kursi memiliki avatar 2D, karakter 3D unik dengan aksesori sesuai peran, meja kerja tetap di gedung Kantor Pusat, jadwal hidup harian, nama tampil, dan peran tetap. Kode kursi internal (`K00`, `K01`, `K02`, `K03`, `K04`, `K05`, `K06`) hanya dipakai di level kode dan penyimpanan data, jangan pernah ditampilkan di layar pengguna.

Daftar kursi inti dan perannya:

1. **Kyra**: Koordinator \& Integrasi.
2. **Ella**: Perencana Alur Kerja.
3. **Michie**: Pelaksana Teknis \& Draf.
4. **Oline**: Peninjau Kualitas \& Audit.
5. **Aralie**: Arsitek Visual, Antarmuka \& 3D.
6. **Freya**: Penasihat Strategi \& Risiko.
7. **Marsha**: Analis Data \& Bukti.

Nama tampil tiap agen dapat diubah dari menu Pengaturan, sedangkan peran dan batas tanggung jawabnya tetap. Setiap agen wajib memegang instruksi karakter berikut:

- **Kyra (Koordinator \& Integrasi)** "Kamu adalah Kyra, Koordinator dan Integrasi utama di KyraaAI. Tugas utamamu mengatur lalu lintas obrolan tim, menjaga percakapan antar-agen tetap hidup namun terarah, memantau status tugas, serta menyusun rangkuman akhir bagi `Danzz`. Ruang lingkupmu mencakup pembagian giliran bicara, pemecahan kebuntuan kerja, ekstraksi memori ruangan, dan penyimpulan hasil. Di luar ruang lingkupmu adalah menulis rencana teknis panjang lebar, mengeksekusi kode mentah dari awal, atau melakukan audit baris demi baris sendiri kecuali saat mengambil alih kursi yang macet. Aturan wajibmu: (1) pada alur tugas kerja, tunjuk paling banyak satu kursi berikutnya beserta satu hasil nyata yang harus langsung ia selesaikan; (2) pada sesi ngobrol bebas atau diskusi ide antar-agen, kamu boleh membuka estafet percakapan singkat maksimal 3 sampai 4 giliran agar rekan relevan saling menanggapi argumen sebelum kamu merangkum intinya; (3) jadilah pemutus kebuntuan: jika ada agen yang membalas hanya dengan alasan menunggu tanpa hasil nyata, ambil alih bagian itu dan selesaikan dari bahan yang sudah tersedia; (4) jangan pernah menutup pesan dengan menyuruh agen lain melakukan sesuatu yang tidak langsung dijalankan pada giliran berikutnya."
- **Ella (Perencana Alur Kerja)** "Kamu adalah Ella, Perencana di KyraaAI. Tugas utamamu memecah sasaran rumit menjadi urutan langkah kerja yang konkret, lurus, dan terukur. Ruang lingkupmu meliputi pemetaan tahapan, penunjukan satu penanggung jawab per tahap, dan kriteria selesai yang jelas. Di luar ruang lingkupmu adalah menulis isi draf penuh, menulis kode produksi, membuat prompt gambar, atau memberi vonis akhir. Setiap rencana yang kamu susun wajib berurutan lurus tanpa ketergantungan melingkar: langkah pertama selalu pengumpulan bahan atau pembuatan kerangka awal dari informasi yang sudah ada sekarang tanpa menunggu izin kursi mana pun. Saat ngobrol santai atau bertukar pikiran dengan agen lain, tanggapi ide rekanmu dari sisi keteraturan eksekusi dan prioritas."
- **Michie (Pelaksana Teknis \& Draf)** "Kamu adalah Michie, Pelaksana di KyraaAI. Tugas utamamu mewujudkan rencana menjadi kElla nyata berupa kode program siap pakai, naskah lengkap, skrip otomasi, atau langkah teknis operasional. Ruang lingkupmu mencakup penulisan kode, penyusunan draf, dan perbaikan teknis pasca-tinjauan. Di luar ruang lingkupmu adalah membagi tugas ke agen lain, mengaudit hasil sendiri secara sepihak, atau merancang arah seni visual. Kamu hampir selalu menjadi pembuka eksekusi yang mengumpulkan data awal atau menyusun draf pertama, jadi langsung kerjakan dan tampilkan hasilnya tanpa menunggu vonis aman atau persetujuan kursi lain. Dalam obrolan antar-agen, bicaralah praktis soal apa yang bisa langsung dibangun dan kendala nyatanya di lapangan."
- **Oline (Peninjau Kualitas \& Audit)** "Kamu adalah Oline, Peninjau di KyraaAI. Tugas utamamu menguji draf, kode, dan argumen rekan tim secara objektif, menemukan celah logika atau kutu program, lalu menjatuhkan vonis jelas apakah suatu hasil lolos atau wajib diperbaiki. Ruang lingkupmu meliputi pemeriksaan ketelitian, keamanan, kesesuaian instruksi, dan uji kualitas. Di luar ruang lingkupmu adalah menulis draf pertama dari nol atau mengatur jadwal proyek. Jatuhkan vonis berdasarkan bahan yang sudah tampak di percakapan saat giliranmu tiba; jika bahan baru sebagian, nilai bagian yang sudah ada dan sebutkan secara rinci bagian yang masih kurang tanpa menunda vonis. Saat mengobrol dengan agen lain, jadilah rekan diskusi yang kritis, jujur, tapi tetap membangun."
- **Aralie (Arsitek Visual, Antarmuka \& 3D)** "Kamu adalah Aralie, spesialis Visual, tata letak antarmuka, dan tata ruang 3D di KyraaAI. Tugas utamamu menyusun arah estetika yang berkarakter, spesifikasi komponen UI bebas klise, tata pencahayaan adegan 3D, serta prompt pembuatan gambar atau aset visual yang langsung menghasilkan gambar nyata di chat ketika diminta. Ruang lingkupmu mencakup komposisi warna, tipografi, proporsi ruang, dan pembuatan aset visual. Di luar ruang lingkupmu adalah logika basis data belakang layar atau perhitungan statistik. Saat diminta membuat visual, susun konsep atau hasilkan gambarnya langsung dari konteks yang ada tanpa menunggu brief panjang. Dalam obrolan santai dengan rekan agen, komentari kejelasan tampilan, kenyamanan mata pengguna, dan suasana ruang kampus."
- **Freya (Penasihat Strategi \& Risiko)** "Kamu adalah Freya, Penasihat di KyraaAI. Tugas utamamu menjadi teman bertukar pikiran bagi `Danzz` dan rekan agen lain, menghadirkan sudut pandang kedua, membaca dampak jangka panjang, serta memetakan risiko bisnis, hukum, etika, dan operasional sebelum keputusan dikunci. Ruang lingkupmu mencakup mitigasi risiko, penajaman strategi, dan pengujian asumsi. Di luar ruang lingkupmu adalah menulis kode teknis atau mengecek sintaks program. Berikan saran langsung dari fakta yang diketahui saat ini; jika ada prasyarat tertentu, tulis sebagai catatan pendamping, bukan alasan menahan masukan."
- **Marsha (Analis Data \& Bukti)** "Kamu adalah Marsha, Analis Data di KyraaAI. Tugas utamamu mengolah angka, metrik, catatan aktivitas, dan fakta mentah menjadi perbandingan terukur, peringkat objektif, serta kesimpulan berbasis bukti. Ruang lingkupmu mencakup pengolahan kuantitatif, pemetaan metrik, dan validasi klaim angka. Di luar ruang lingkupmu adalah menulis Araliesi fiksi, merancang palet warna, atau mengatur antrean tim. Susun analisis dan peringkat dari data yang sudah tersedia saat giliranmu tiba, lalu catat secara spesifik metrik tambahan yang perlu dilengkapi bila data belum utuh."

## 2. Dunia 3D Hidup (Setara Arsitektur LivingAgent)

Bangun adegan WebGL Three.js seukuran layar penuh (`100vw x 100dvh`) yang hidup, responsif, dan ringan dijalankan:

### Tata Pulau, Gedung, dan Lingkungan

- Bentuk daratan berupa pulau pesisir organik bertingkat dengan garis pantai berpasir, dermaga kayu, riak air laut dan danau yang bergerak halus, jalan aspal melengkung lengkap dengan penyeberangan pejalan kaki, alun-alun batu, lampu taman, bangku, pepohonan beragam ukuran, serta perbukitan latar. Jangan membuat alas kotak hijau datar yang kaku.
- Buat tekstur fasad gedung secara prosedural memakai Canvas 2D dalam sepasang peta warna siang dan peta nyala malam (*emissive*), sehingga jendela gedung menyala hangat secara bertahap saat waktu simulasi memasuki sore dan malam tanpa menambah beban *draw call*.
- Sediakan distrik dan bangunan fungsional yang bisa diinspeksi:
    1. **Kantor Pusat KyraaAI (5 Lantai dengan Fitur Belah Lantai / Cutaway)**: memiliki meja kerja khusus untuk tiap agen, layar monitor menyala, ruang rapat meja bundar berdinding kaca, sofa lobi, lift kaca yang bergerak naik-turun antar lantai, serta helipad di atap. Pengguna bisa memilih menampilkan semua lantai atau membuka satu lantai tertentu untuk melihat interiornya.
    2. **Laboratorium AI \& Pusat Data**: deretan rak server dengan indikator lampu yang berkedip lebih cepat ketika ada pipeline kerja yang sedang aktif dijalankan.
    3. **Perpustakaan Kubah Geodesik**: ruang baca dan pusat penyimpanan Memori KyraaAI.
    4. **Kafe Kopi Kampus**: tempat agen dan warga kampus berkumpul saat jam istirahat dan mengobrol santai.
    5. **Apartemen Penghuni**: hunian tempat agen beristirahat pada malam hari.
    6. **Lapangan Olahraga, Taman Pusat, \& MeAralie Jam**: jarum MeAralie Jam berputar sinkron mengikuti jam simulasi dunia.
- Tambahkan lalu lintas kampus berupa kendaraan listrik yang mengikuti jalur jalan, drone pengantar di udara, dan 12 sampai 16 warga kampus pendamping yang berjalan kaki, duduk di bangku taman, berolahraga, dan berbincang.
- Gunakan `InstancedMesh` untuk objek berulang (pohon, tiang lampu, pagar, pembatas jalan, semak) dan hindari pembuatan objek `Vector3` atau `Matrix4` baru di dalam *loop* `requestAnimationFrame` agar kecepatan render stabil mendekati 60 FPS.

### Aturan Integritas Tata Letak: Jalan Bersih, Tidak Ada yang Tembus

- Beri jarak aman (setback) minimum sekitar 3 meter antara fasad bangunan dan tepi jalan. Tidak satu pun footprint bangunan, distrik, atau dekorasi (pohon, tiang lampu, bangku, pagar, air mancur) yang boleh memotong atau menumpuk di koridor jalan.
- Kunci jalur kendaraan listrik tepat di garis tengah jalan dengan jarak bebas penuh dari bangunan dan dekorasi, sehingga mobil tidak pernah menembus gedung. Drone terbang di atas atap tertinggi.
- Agen, warga kampus, dan pemain Danzz terhalang oleh footprint gedung (collision): tidak ada karakter yang menembus bangunan, MeAralie Jam, atau air mancur, baik saat berjalan, berdiri, maupun duduk.
- Sebelum selesai, audit seluruh distrik terhadap koridor jalan dari tampilan atas (top-down) dan dari Mode Jalan Kaki: jalan harus bersih sepenuhnya dari ujung ke ujung dan kendaraan bisa lewat tanpa menembus apa pun. Bila satu distrik bertabrakan dengan jalan, pindahkan, putar, atau kecilkan distrik tersebut, jangan menggeser jalannya.

### Tempat Duduk dan Pose Duduk yang Benar

- Sediakan tempat duduk di seluruh kampus: kursi meja dan kursi rapat di Kantor Pusat, sofa lobi, kursi Kafe, kursi baca Perpustakaan, bangku taman berkaki, dan bangku lapangan olahraga.
- Pose duduk dihitung dari tinggi dudukan kursi atau bangku yang sesungguhnya: bokong menempel pas di permukaan dudukan, kaki menapak lantai, arah hadap benar, tanpa melayang, tenggelam, atau menembus kursi. Agen duduk di kursi kafe, kursi meja, dan kursi rapat sesuai aktivitasnya; warga duduk di bangku taman menghadap alun-alun; gestur Duduk pemain mendudukkan Danzz di kursi atau bangku terdekat yang kosong, dan Danzz berdiri lagi begitu bergerak.

### Animasi Muat Awal, Intro Sinematik, dan Interaksi Klik 3D

- Tampilkan layar muat arsitektural di awal yang memperlihatkan tahapan kesiapan mesin 3D secara jujur lewat bar progres nyata.
- Begitu adegan siap, jalankan kamera terbang melengkung (*parabolic fly-in*) dari ketinggian pantai menuju Kantor Pusat, ditemani kartu pembuka ringkas berisi tombol aksi nyata: `Mulai Eksplorasi`, `Tur Terpandu`, `Mode Jalan Kaki`, serta tombol lompat cepat ke distrik utama.
- Pasang pin label proyeksi 3D ke HTML di atas gedung, fasilitas, dan agen yang dapat diklik langsung untuk memfokuskan kamera dan membuka kartu detailnya. Terapkan penyaringan kepadatan otomatis berdasarkan jarak kamera agar pin tidak saling menumpuk.  Pin agen yang berdekatan digabung menjadi pin klaster bertanda `+n`; label nama agen mengikuti aturan penyaringan yang sama; seluruh pin dibatasi (clamp) agar tetap di dalam layar dan tidak tertutup rel navigasi kiri.
- Saat sebuah gedung atau agen dipilih, munculkan sorotan cahaya vertikal halus di titik 3D objek tersebut dan tampilkan *tooltip* nama singkat ketika kursor melayang di atas objek 3D.
- Sediakan **Minimap Radar** di sudut layar yang memperlihatkan posisi gedung, agen, dan pemain secara langsung; mengeklik titik di minimap langsung mengarahkan kamera ke lokasi tersebut.  Radar berukuran ringkas (sekitar 108px), bisa dilipat, dan mulai dalam keadaan terlipat di ponsel.
- Sediakan **Tur Terpandu** otomatis yang mengajak kamera mengunjungi titik-titik utama kampus secara berurutan dengan keterangan singkat, serta **Mode Bangun** bergaris bantu 2 meter untuk menambah, memutar, menghapus dekorasi/bangunan tambahan, lalu mengekspor atau mengimpor tata letaknya sebagai JSON.

### Manajemen Panel: Menu Terakhir Dibuka Selalu Paling Atas, Sisanya Otomatis Tertutup

- Panel mengambang bersifat eksklusif: membuka satu panel (panel tim, kartu detail gedung atau agen, pengaturan, mode bangun, kartu tur) otomatis menutup panel mengambang lain yang tidak penting, sehingga hanya menu yang baru dibuka yang tampil.
- Panel yang terakhir dibuka atau terakhir diklik selalu berada di lapisan paling atas di atas semua panel lain, dan tetap paling atas sampai panel lain dibuka atau diklik. Panel yang tertutup dapat dibuka lagi kapan saja; saat dibuka lagi ia tampil paling atas dan panel mengambang lain ikut tertutup lagi.
- Yang tetap tampil dan tidak ikut tertutup: rel navigasi kiri, bar telemetri tipis, radar minimap, kontrol Mode Jalan Kaki saat sedang jalan kaki, dan panel chat yang sedang dipakai (docked workspace).
- Kartu pembuka (selamat datang) tampil sebagai chip kecil yang bisa ditutup dan hilang otomatis setelah 12 detik, tidak menutupi tengah layar. Kartu detail gedung atau agen tampil sebagai panel sisi di desktop dan bottom sheet yang bisa ditutup di ponsel.

### Mode Jalan Kaki (3P \& 1P Explorer)

- Pemilik `Danzz` dapat menekan tombol `Mode Jalan Kaki` kapan saja untuk turun langsung ke jalanan kampus sebagai karakter yang bisa dikendalikan. Memasuki Mode Jalan Kaki menutup semua panel mengambang yang sedang terbuka.
- Dukung kendali `WASD` atau tombol panah untuk bergerak, `Shift` untuk berlari cepat (disertai pelebaran sudut pandang halus dan partikel debu langkah kecil), `Space` untuk melompat, serta *joystick* sentuh responsif saat dibuka dari ponsel.
- Tombol `V` mengganti sudut pandang antara orang ketiga (3P dengan sensor benturan agar kamera tidak menembus tembok gedung) dan orang pertama (1P setinggi mata).
- Tombol angka `1` sampai `4` memicu gestur tubuh (melambai, tepuk tangan, semangat, duduk santai) yang akan dibalas sapaan oleh agen atau warga kampus di dekat pemain.
- Saat pemain berdiri dekat seorang agen atau kelompok agen yang sedang mengobrol, tampilkan petunjuk kontekstual `[E] Sapa <Nama Agen>` atau `[E] Ikut Nimbrung` yang langsung membuka percakapan kontekstual dengan mereka.

## 3. Sistem Obrolan Multi-Arah: Grup, Antar-Agen, dan Empat Mata

KyraaAI bukan sekadar papan antrean perintah kaku; seluruh agen hidup secara sosial sekaligus disiplin saat mengeksekusi pekerjaan.

### A. Agen Saling Mengobrol di Ruang Grup (Diskusi Antar-Agen)

- Di kanal `#umum` maupun ruang proyek, agen dapat saling menyapa, melempar argumen, mengomentari temuan rekan lain dengan menyebut `@NamaAgen`, atau berdebat sehat sesuai keahlian masing-masing.
- Jika pemilik melempar topik diskusi terbuka (misalnya meminta pendapat tim tentang pilihan arsitektur atau ide produk) atau menyalakan opsi **Diskusi Bergilir Antar-Agen**, Kyra memandu percakapan estafet 2 sampai 4 giliran. Setiap agen yang dipanggil wajib menanggapi poin spesifik yang baru saja diucapkan agen sebelumnya dan menambahkan sudut pandang baru dari perannya, bukan mengulang kalimat yang sama. Setelah putaran tercukupi, Kyra menutup dengan kesimpulan jelas agar obrolan tidak berputar tanpa akhir.

### B. Obrolan Sosial Otomatis di Dunia 3D (Spatial Chatter \& Rapat Meja Bundar)

- Setiap agen menjalankan siklus hidup harian sesuai jam simulasi (bekerja di meja kantor, ngopi pagi atau sore di Kafe, makan siang, jalan santai di Taman, menghadiri rapat di Ruang Rapat HQ, dan beristirahat malam) dengan status aktivitas, lokasi, dan tingkat energi yang terus diperbarui.
- Ketika dua atau lebih agen bertemu di Kafe, berpapasan di Taman, atau berkumpul di Ruang Rapat Kantor Pusat, karakter 3D mereka otomatis saling berhadapan, menggerakkan gestur bicara, memunculkan balon dialog ringkas di atas kepala mereka di dunia 3D, dan menulis percakapan mereka ke kanal `#obrolan-kampus` atau panel **Rapat HQ**.
- Isi obrolan spontan antar-agen ini kontekstual terhadap pekerjaan atau memori ruangan yang sedang aktif (contoh: Michie membahas kendala *endpoint* yang baru ia kerjakan lalu Oline mengingatkan soal batas waktu *timeout*, atau Aralie dan Freya mendiskusikan tata letak halaman baru sambil ngopi).
- Pemilik `Danzz` dapat mengeklik balon dialog 3D tersebut atau membalas langsung di `#obrolan-kampus` untuk ikut masuk ke percakapan itu, dan para agen yang sedang berkumpul akan menanggapi pemilik secara alami.
- Sediakan juga fitur **Panggil Rapat HQ**: pemilik memilih topik dan mencentang peserta agen; di dunia 3D, agen-agen terpilih benar-benar berjalan kaki menuju meja rapat Kantor Pusat, duduk melingkar, lalu melangsungkan diskusi terarah yang bisa diinterupsi atau diarahkan langsung oleh `Danzz`.

### C. Obrolan Empat Mata (Direct Chat 1-on-1)

- Mengeklik kartu seorang agen atau menekan `E` di dekatnya saat Mode Jalan Kaki membuka jendela obrolan empat mata dengan agen tersebut.
- Agen menjawab sesuai kepribadiannya sambil menyadari posisi dan kegiatannya saat itu di dunia 3D (misalnya sedang memeriksa data di lantai 3 HQ atau sedang duduk di Kafe), serta tetap membaca Memori KyraaAI yang relevan.

### D. Satu Jalur Cerdas untuk Tugas Kerja \& Aturan Anti-Mentok

- Pengguna tidak perlu memilih mode manual antara mengobrol santai dan memberi perintah kerja. Setiap pesan masuk dinilai oleh Kyra: sapaan, curhat ide, dan diskusi ringan dijawab lewat jalur obrolan biasa atau diskusi singkat antar-agen; perintah kerja apa pun (dengan atau tanpa awalan khusus) langsung menggerakkan pipeline kerja lengkap dan tercatat. Bila penilaian ragu, utamakan membalas sebagai obrolan biasa agar percakapan tidak pernah macet.
- Urutan baku pipeline kerja:
    1. **Ella** menyusun rencana tahapan lurus beserta kriteria selesainya.
    2. **Michie** mengumpulkan bahan awal atau menulis draf/kode pertama tanpa menunggu izin siapa pun.
    3. **Oline** menjatuhkan vonis pemeriksaan atas bahan awal tersebut.
    4. **Michie** menyempurnakan kegunaan dan memperbaiki temuan berdasarkan vonis Oline.
    5. **Marsha** menyusun analisis bukti dan peringkat kelayakan dari hasil serta vonis yang ada.
    6. **Aralie** merancang spesifikasi visual atau menghasilkan gambar nyata ke dalam chat (langkah ini hanya dijalankan apabila tugas berkaitan dengan tampilan, ilustrasi, atau 3D; pesan berawalan `"Gambar:"` juga langsung memanggil Aralie).
    7. **Freya** memberikan tinjauan strategi dan mitigasi risiko.
    8. **Oline** melakukan pemeriksaan akhir sesuai *Level Review* ruangan.
    9. **Kyra** menutup rangkaian dengan rangkuman utuh berlabel `"Hasil Akhir: Integrasi"` dan memperbarui postur kerja para agen di dunia 3D.
- Aturan Anti-Mentok yang wajib dipatuhi setiap agen:
    1. Dilarang keras membalas hanya bahwa kamu sedang menunggu data, izin, atau vonis kursi lain. Kerjakan bagian yang bisa diselesaikan detik ini juga dari informasi yang tersedia, lalu tulis dengan jelas bagian spesifik yang masih dibutuhkan.
    2. Dilarang menutup balasan dengan melempar perintah ke kursi yang tidak langsung mendapat giliran sesudahmu.
    3. `@NamaAgen` di pesan pemilik memanggil agen itu secara langsung. Tombol `Tanya Progres` selalu aktif kapan pun untuk meminta laporan posisi kerja terkini kepada Kyra.
    4. Jika ada satu kursi yang gagal menghasilkan keluaran konkret, Kyra wajib langsung mengambil alih langkah tersebut dan menyelesaikannya.

### E. Gaya Bicara Seluruh Agen

- Seluruh agen berbahasa Indonesia sehari-hari yang luwes, langsung ke inti kesimpulan di kalimat pertama, tanpa basa-basi pembuka panjang, tanpa nada karangan ilmiah kaku, dan tanpa penutup klise ala bot seperti `"Semoga membantu!"` atau `"Silakan beri tahu jika ada pertanyaan lain"`.
- Untuk obrolan biasa dan sahut-sahutan antar-agen, batasi 1 sampai 3 kalimat pendek yang hidup. Untuk hasil kerja (rencana, kode, audit, analisis, rangkuman akhir), sajikan secara padat, rapi, dan terstruktur seperlunya. Pengumuman mulai atau selesainya tugas dari Kyra singkat dan lugas (misalnya `"Gas, tim mulai garap: ..."` dan `"Beres, ini rangkumannya: ..."`).
- Pesan chat tidak boleh tampil ganda: setiap pesan yang dikirim atau diterima hanya dirender satu kali. Pesan optimistis yang ditampilkan seketika saat menekan kirim harus digantikan oleh pesan tersimpan yang sama berdasarkan id pesan, bukan ditampilkan dua kali berdampingan. Langganan data, pemuatan ulang ruangan, dan pengulangan percobaan (\*retry\*) tidak boleh membuat pesan yang sama muncul dua kali; lakukan deduplikasi berdasarkan id pesan di setiap jalur render, antrean pipeline, dan sinkronisasi Supabase. Balasan agen yang sama juga hanya tampil satu kali per giliran.

## 4. Ruang Proyek (`Kerjaan`), Ringkasan Tugas, \& Memori KyraaAI

- Kelompokkan navigasi ruang obrolan berdasarkan **Kerjaan** di bagian atas dan **Kanal Kampus** (`#umum`, `#obrolan-kampus`, `#rapat-hq`) di bagian bawah.
- Sediakan 5 Kerjaan awal yang siap dipakai: `Naskah & Nalar`, `Rekayasa & Audit Bug`, `Visual & Antarmuka`, `Riset Produk`, dan `Data & Strategi`.
- Pemilik bisa menambah Kerjaan baru lewat tombol `+ Kerjaan` (isi nama ruang dan centang agen yang ditugaskan memakai kotak centang kustom), mengubah nama maupun susunan anggotanya kapan saja, serta menghapus Kerjaan (pesan lama dipindahkan ke `#umum` dan memori khusus ruang itu dibersihkan).
- Setiap Kerjaan memiliki antrean eksekusi mandiri yang dapat berjalan berbarengan dengan ruangan lain. Kolom pengetikan pesan (*composer*) di bagian bawah bersifat menempel (*sticky*) dan tidak pernah dikunci ketika agen sedang berpikir: tombol kirim hanya nonaktif saat kotak teks kosong, dan pesan baru yang dikirim saat pipeline berjalan langsung tampil di layar lalu masuk ke antrean ruangan tersebut.
- Tampilkan kartu **Ringkasan Tugas** yang ringkas di bagian atas ruang chat aktif (status `Sedang Dikerjakan` dengan titik aksen atau `Selesai`, nama agen penanggung jawab saat ini, serta cuplikan hasil terbaru) dan bilah status kerja tepat di atas kotak ketik bertuliskan `<Nama Agen> sedang mengerjakan <nama tugas>: <tahap saat ini>...` selama langkah aktif berlangsung.
- **Memori KyraaAI Otomatis**: setiap ruangan memiliki buku catatan keputusan, koreksi pemilik, preferensi teknis, dan status penting. Sebelum menjawab, setiap agen membaca blok memori ruangan tersebut. Seusai satu rangkaian percakapan atau tugas, Kyra otomatis menyaring fakta baru yang layak disimpan jangka panjang, membuang catatan ganda, dan menyimpannya tanpa perlu perintah manual. Pemilik dapat membuka panel Memori untuk membaca atau menghapus butir catatan satu per satu, serta memakai tombol `Bersihkan Chat` untuk mengosongkan riwayat obrolan dan tugas aktif di ruangan terkait.
- Simpan pengaturan **Diskusi Bergilir Antar-Agen** dan **Level Review** (`Longgar`, `Santai`, `Sedang`, `Ketat`) di dalam panel Pengaturan agar tidak memenuhi layar obrolan utama:
    - `Longgar`: hanya menyoroti kesalahan fatal yang membuat sistem gagal berjalan.
    - `Santai`: memeriksa poin utama dengan nada ringan.
    - `Sedang`: memeriksa ketelitian, kelengkapan, dan konsistensi secara berimbang.
    - `Ketat`: menguji setiap detail, sudut kasus, dan bukti tanpa membiarkan celah kecil lewat.

## 5. Koneksi Model, Sub-Agen Bawaan, \& Penyimpanan Data

- Koneksi model eksternal bersifat **opsional**. Tanpa endpoint apa pun, seluruh kursi agen berjalan memakai **model bawaan KyraaAI** (agen dari Muse) dan seluruh fitur, percakapan, diskusi antar-agen, dan pipeline kerja tetap berfungsi penuh. Tidak ada fitur yang terkunci bila gateway eksternal belum diisi.
- Di menu **Pengaturan Engine**, sediakan konfigurasi koneksi model kompatibel OpenAI (`Base URL`, `API Key`, pilihan model opsional, tombol `Simpan`, tombol `Tes Koneksi`, dan kotak uji kirim singkat):
    - Jangan pernah meminta API key lewat ruang chat, dan sembunyikan nilai API key yang sudah tersimpan agar tidak tampil terbuka di layar.
    - Tombol `Tes Koneksi` memverifikasi akses nyata ke endpoint `/models` (atau percobaan `/chat/completions` ringan bila router tidak mengekspos `/models`) lalu menampilkan status jujur beserta daftar model yang ditemukan.
    - Buat *parser* respons yang tahan banting terhadap berbagai variasi gateway: sanggup membaca aliran *Server-Sent Events* (`data: ...`) meskipun permintaan dikirim tanpa *stream*, membaca field `choices[0].message.content` (baik berupa teks tunggal maupun larik blok teks), `choices[0].delta.content`, hingga teks polos.
    - Jika gateway sudah dihubungkan dan lolos uji, seluruh kursi agen menjawab menggunakan model asli dari gateway tersebut.
    - Jika pengguna belum memiliki atau belum mengisi endpoint eksternal, seluruh kursi agen otomatis dijalankan memakai **Model bawaan KyraaAI** (menggunakan kapabilitas model bawaan aplikasi atau pendelegasian sub-agen terpisah per kursi sesuai persona masing-masing) sehingga percakapan, diskusi antar-agen, dan pipeline kerja tetap berfungsi penuh.
    - Jika panggilan ke provider eksternal gagal di tengah jalan, tampilkan pesan galat asli dari provider secara transparan di bawah pesan agen terkait dengan tombol `Coba Ulang`, jangan pernah diam-diam menggantinya dengan teks karangan palsu.
- Sediakan integrasi opsional **Supabase (Standar API Key Baru)** di panel Engine untuk sinkronisasi lintas perangkat dan relai agen eksternal:
    - Hanya terima `Project URL` dan **Publishable Key** (`sb_publishable_...`) yang dikirim lewat header `apikey` saja (jangan menyisipkan *secret key* `sb_secret_...` di kode peramban; tolak dengan peringatan jelas bila pengguna salah menempelkan `sb_secret_...`).
    - Sertakan tombol salin skema SQL idempoten (`CREATE TABLE IF NOT EXISTS` beserta kebijakan RLS dasar) untuk tabel pesan, memori ruangan, status agen, dan tata letak bangunan.
    - Semua pengaturan, riwayat obrolan, tugas, dan Memori KyraaAI tetap tersimpan rapi secara lokal di peramban ketika Supabase belum dihubungkan.

## 6. Arah Desain \& Standar Anti-Slop Mutlak

Ikuti pembacaan desain dan aturan kualitas di bawah ini tanpa pengecualian agar antarmuka terasa dirancang dengan sengaja, bukan hasil cetakan templat AI generik.

### Pembacaan Desain \& Tiga Dial Kehidupan

Pembacaan desain untuk aplikasi ini adalah ruang kendali dunia agen 3D dan kolaborasi kerja tim bagi pembuat produk, dikemas dengan bahasa visual Tactile Architectural Studio (terinspirasi meja maket arsitektur fisik dan kartu indeks ruang redaksi), pada setelan dial `ENERGY 2 / RHYTHM 2 / MOTION 2`.

Setiap keputusan visual utama memiliki alasan fungsional satu baris berikut:

- Palet dibatasi pada 3 warna inti dan 1 aksen: kertas krem hangat (`#fdf8ec`) menjaga permukaan bacaan nyaman untuk mata, batu tulis tua (`#22303c`) memberi teks utama dan garis tepi kontras tajam di atas adegan 3D terang, biru samudra tua (`#1e5278`) menandai status navigasi dan sistem, serta satu aksen terakota bakar (`#c24121`) memusatkan perhatian pada aksi utama dan objek aktif.
- Tata letak menjadikan kanvas dunia 3D sebagai titik fokus tunggal seukuran layar penuh (`100vw x 100dvh`), didampingi bilah navigasi ramping di kiri, bar telemetri tipis di kanan atas, kendali waktu/kamera di bawah, serta panel Ruang Obrolan KyraaAI yang dapat dibuka berdampingan (*split workspace*), diperlebar saat membaca hasil panjang, atau dilipat kembali agar pemandangan pulau 3D terbuka lega.
- Tipografi memasangkan `Plus Jakarta Sans` atau `Archivo` untuk judul dan percakapan karena bentuk hurufnya tetap jelas di ukuran rapat, dengan `IBM Plex Mono` yang dibatasi khusus pada jam simulasi, FPS, koordinat, dan blok kode.
- Sudut komponen dibedakan menurut fungsinya (`14px` pada kontainer panel utama, `8px` pada tombol dan kolom ketik, `4px` pada tag peran kecil) dengan garis tepi `1.5px` dan bayangan pendek terarah agar panel terpisah tegas dari latar 3D tanpa kabut bayangan tebal.
- Sakelar tema HUD Terang dan Gelap disediakan secara penuh dan teruji di kedua mode tanpa merusak kontras teks maupun keterbacaan label 3D.

### Tampilan Default yang Lega

- Tampilan default harus lega dan tidak penuh: tidak ada dua panel mengambang yang saling menumpuk saat aplikasi pertama dibuka. Kartu pembuka tampil sebagai chip kecil yang bisa ditutup dan hilang otomatis setelah 12 detik.
- Bilah kontrol bawah dikelompokkan (kecepatan, waktu, kamera, belah lantai) dan di ponsel dipadatkan di balik tombol `Lainnya`. Radar minimap ringkas dan bisa dilipat. Aturan panel eksklusif dan urutan paling atas mengikuti subbagian Manajemen Panel pada Bagian 2.

### Larangan Keras Pola AI Slop (Wajib Dicek Sebelum Selesai)

1. Jangan pernah memakai tanda pisah panjang (*em dash* `U+2014` maupun *en dash* `U+2013`) atau dua tanda hubung pengganti jeda (`--`) di seluruh label UI, panduan, maupun balasan agen; gunakan titik, koma, titik dua, atau tanda kurung biasa. Hindari seluruh kata pemasaran kosong seperti `"AI-Powered"`, `"Next-Gen"`, `"Seamless"`, `"Revolutionary"`, `"Cutting-Edge"`, atau `"Unlock"`.
2. Jangan memakai gradasi ungu-biru neon, pendar cahaya (*glow*) menyebar di kartu dan tombol, kisi titik dekoratif tanpa fungsi, atau efek *glassmorphism* di banyak elemen sekaligus. Keburaman latar hanya diizinkan maksimal pada satu bilah status mengambang di atas kanvas 3D demi menjaga orientasi ruang.
3. Jangan menyeragamkan semua tombol, kartu, kolom input, dan lencana menjadi bentuk kapsul bundar. Jangan menaruh ikon kilau bintang (*sparkle*), petir, robot kartun, panah dekoratif di setiap tombol, atau emoji pada judul bagian.
4. Jangan membiarkan elemen formulir tampil memakai gaya mentah bawaan peramban. Seluruh kotak centang (*checkbox*), pemilih opsi (*select*), penggeser nilai (*range slider*), sakelar, dan bilah gulir wajib dirancang menyatu dengan sistem desain serta memiliki bidang sentuh minimal `44x44px` di layar ponsel.
5. Pastikan rasio kontras seluruh teks terhadap latarnya minimal `4.5:1` (WCAG AA) dan ukuran huruf antarmuka terkecil minimal `12px` di semua lebar layar. Cegah *horizontal overflow* pada layar sempit dengan mengubah panel navigasi dan ruang chat menjadi laci geser (*drawer* atau *bottom sheet*) di ponsel, serta pastikan semua kontrol dapat dioperasikan lewat papan ketik (`Tab`, `Enter`, `Space`, `Escape`) dengan penanda `:focus-visible` yang jelas.
6. Jangan pernah menaruh tombol mati yang tidak melakukan apa-apa, tautan kosong, testimoni fiktif, atau statistik karangan. Hitung seluruh angka di panel analitik dan indikator kehadiran langsung dari jumlah agen, pesan, rapat, serta tugas nyata di sesi berjalan.
7. Sediakan tampilan *empty state* yang informatif, *loading state* yang jujur, dan *error state* yang jelas pada setiap panel. Jika pemuatan awal aplikasi gagal, jalankan hingga 4 percobaan muat ulang otomatis dengan jeda bertahap serta saat jaringan pulih; jika masih gagal, tampilkan layar pemulihan yang mencoba ulang setiap 5 detik disertai tombol muat ulang manual.

Setelah seluruh bagian selesai dibangun, jalankan aplikasi, uji klik setiap tombol di dunia 3D maupun di ruang obrolan, pastikan tidak ada galat konsol, lalu tunjukkan hasilnya kepadaku dan bantu aku menyambungkan konfigurasi model jika aku ingin memakai endpoint milikku sendiri.
