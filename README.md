# TLC NYC Trip Record Analysis

Dalam era digital, transportasi berbasis data telah menjadi kunci dalam pengelolaan sistem mobilitas perkotaan. Salah satu sumber data yang sering digunakan dalam analisis transportasi adalah NYC TLC Trip Record Dataset. Dataset ini disediakan oleh New York City Taxi and Limousine Commission (TLC), yang mencatat perjalanan taksi di kota New York, termasuk taksi kuning (Yellow Taxi) dan taksi hijau (Green Taxi). Taxi & Limousine Commission (TLC NYC) merupakan lembaga pemerintah Kota New York yang bertanggung jawab untuk mengatur seluruh yang berhubungan dengan kendaraan taksi. Tanggung jawab dari komisi NYC TLC termasuk dalam melindungi keselamatan publik, menerbitkan dan mengatur izin serta menetapkan dan membatasi tarif taksi. Di mana Komisi NYC TLC ingin data analyst untuk menganalisa pengoperasian perjalanan taksi selama di bulan Januari 2023.

# Exploratory Data Analysis

- **VendorID** : Perusahaan yang memiliki armada taksi merekam data transaksi perjalanan taksi
    - 1 = Creative Mobile Technologies, LLC.
    - 2 = VeriFone Inc.
- **lpep_pickup_datetime** : tanggal dan waktu saat argometer taksi dinyalakan bisa juga di artikan saat penumpang masuk atau perjalanan dimulai
- **lpep_dropoff_datetime** : tanggal dan waktu saat argometer taksi dimatikan bisa juga di artikan saat penumpang turun atau perjalanan selesai
- **store_and_fwd_flag** : Menunjukkan apakah catatan perjalanan disimpan di memori kendaraan sebelum dikirimkan ke vendor.
    - Y = data disimpan
    - N = data tidak disimpan
- **RatecodeID** : Kode numerik yang menunjukkan kode tarif untuk perjalanan 
    - 1 = Standard rate
    - 2 = JFK
    - 3 = Newark
    - 4 = Nassau or Westchester
    - 5 = Negotiated fare
    - 6 = Group ride
- **PULocationID** : Pengidentifikasi lokasi penjemputan yang sesuai dengan area geografis tertentu.
- **DOLocationID** : Pengidentifikasi lokasi penurunan yang sesuai dengan area geografis tertentu.
- **passenger_count** : Jumlah penumpang dalam taksi.
- **trip_distance** : Jarak perjalanan dalam mil.
- **fare_amount** : Jumlah yang dibebankan untuk perjalanan sebelum biaya tambahan.
- **extra** : Biaya tambahan (misalnya, biaya jam sibuk atau biaya penginapan).
- **mta_tax** : Pajak Otoritas Transportasi Metropolitan (MTA) ($0.5 otomatis ditambahkan berdasarkan rate).
- **tip_amount** : Jumlah tip (otomatis ditambahkan jika menggunakan kartu kredit, cash tidak dihitung).
- **tolls_amount** : Biaya tol selama perjalanan.
- **ehail_fee** : Biaya terkait layanan e-hailing (E-Hail (pemesanan elektronik) memungkinkan seorang penumpang menggunakan aplikasi berlisensi TLC untuk memesan taksi kuning atau Street-Hail Livery (taksi hijau) menggunakan tarif resmi. E-Hail hanya berlaku untuk taksi kuning dan taksi hijau.).
- **improvement_surcharge** : Biaya peningkatan.
- **total_amount** : Jumlah total yang dibayarkan oleh penumpang kecuali tip dengan cash. 
- **payment_type** : Tipe pembayaran yang digunakan (misalnya, kartu kredit, tunai).
    - 1 = Credit card
    - 2 = Cash
    - 3 = No charge
    - 4 = Dispute
    - 5 = Unknown
    - 6 = Voided trip
- **trip_type** : Jenis perjalanan (misalnya, street-hail, dispatch).
    - 1 = Street-hail
    - 2 = Dispatch
- **congestion_surcharge** : Biaya tambahan untuk tarif kepadatan lalu lintas.

  # Problem

**Stakeholder** : NYC TLC

Dalam memberikan rekomendasi untuk meningkatkan profit bagi NYC TLC serta para pengemudi taksi juga mendapatkan pendapatan yang lebih baik maka seorang Data Analyst akan menjawab beberapa pertanyaan :

1. Di wilayah mana pendapatan taksi terbesar dan pendapatan taksi terbesar terjadi di hari apa ? 
2. Pukul berapa penumpang umumnya memerlukan layanan taksi untuk melakukan perjalanan?
3. Berapa banyak persentase penumpang yang menggunakan metode pembayaran tertentu?
4. Berapa banyak penumpang yang paling banyak memberikan tip berdasarkan zona dan pickup time?
5. Di wilayah mana jumlah pickup terbesar dan kapan jumlah pickup terbesar terjadi (weekdays/weekend) ?
6. Perjalanan pickup-dropoff mana yang paling sering dilakukan saat trip ?
7. Apakah penumpang lebih sering menggunakan taxi untuk perjalanan jarak pendek, menengah, atau jarak jauh?

# Goals

Untuk meningkatkan profit bagi NYC TLC dan meningkatkan pendapatan pengemudi taksi maka dalam analisa ini terdiri atas :

1. Mengidentifikasi wilayah dan dispesifikasikan ke dalam zona di setiap wilayah serta waktu (hari) yang memiliki potensi untuk mendapatkan income yang besar.
2. Mengidentifikasi waktu (jam) yang menjadi peak dalam permintaan untuk menggunakan layanan taksi di setiap wilayah. 
3. Mengidentifikasi penumpang yang menggunakan metode pembayaran tertentu 
4. Mengidentifikasi pemberian tip terbanyak berdasarkan zona, waktu pickup, dan borough 
5. Mengidentifikasi wilayah serta waktu (weekdays / weekend) yang memiliki jumlah permintaan penumpang terhadap layanan taksi.
6. Mengidentifikasi perjalanan yang banyak sering dilakukan oleh penumpang.
7. Mengkategorikan perjalanan mana antara pendek, menengah, panjang yang paling sering dilakukan oleh penumpang

# HASIL DARI PENGERJAAN ANALISIS DATASET TLC NYC Trip Record 

# Kesimpulan Utama:

1. Wilayah dengan pendapatan terbesar berada di wilayah Manhattan. Dapat dilihat dari heatmap juga bahwa pendapatan yang tinggi di Manhattan itu didapatkan pada hari weekday (Senin-Jumat). Di mana seperti diketahui bahwa Manhattan merupakan pusat kota bisnis sehingga tentunya pada hari weekdays merupakan peluang yang besar untuk pengemudi mencari penumpang di sekitaran Manhattan sehingga mendapatkan pendapatan yang maksimal. Jika dilihat saat weekend (Sabtu-Minggu) terlihat bahwa wilayah Brooklyn selain Manhattan juga memiliki prospek untuk meraup keuntungan di mana terlihat pada heatmapnya keuntungan yang didapatkan besar jika dibandingkan saat weekdays.
Apabila dispesifikan ke dalam suatu zona dari setiap wilayah, berikut ini merupakan zona yang memiliki prospek untuk mendapatkan keuntungan yang besar di wilayah tersebut dilihat berdasarkan pendapatannya selama Januari 2023:
- **Manhattan**     : East Harlem North dan East Harlem South
- **Brooklyn**      : Fort Greene dan Downtown Brooklyn/Metrotech
- **Queens**        : Forest Hills dan Elmhurst
- **Bronx**         : East Concourse/Concourse Village, West Concourse, Mott Haven/Port Morris dan Melrose South
- **Staten Island** : Saint George/New Brighton dan Bloomfield/Emerson Hill

2. Wilayah dengan permintaan pickup terbanyak juga terdapat pada wilayah Manhattan dan setiap wilayah menunjukkan permintaan tinggi terjadi saat weekdays sedangkan di weekend masih tergolong rendah untuk permintaan pickupnya.

3. Metode pembayaran terbanyak menggunakan credit card dengan 63% dan cash dengan 36%, untuk no charge(gratis) atau dispute proporsi sangat kecil sehingga tidak perlu di perhitungkan 

4. Pemberian TIP paling banyak terdapat di Manhattan, dilanjutkan oleh Queens, Brooklyn, Bronx, dan Staten Island. Pada grafik TIP atas dapat dilihat bahwa tip tertinggi berada pada rush-hour yaitu pukul 16.00 - 18.00, dan  Beberapa zona memiliki rata-rata tip yang lebih tinggi dari $3. Zona dengan tip tertinggi bisa menjadi indikator area premium atau tempat dengan lebih banyak pelanggan yang memberi tip besar.
Data ini bisa digunakan oleh pengemudi untuk menargetkan lokasi dengan peluang tip lebih besar.

5. Perbandingan pickup lebih signifikan terlihat pada weekday, data tersebut bisa menjadi patokan untuk pada pengemudi memperbanyak armada pada saat weekday

6. Mayoritas perjalanan tergolong Pendek (Short trips), menunjukkan banyaknya perjalanan dalam jarak dekat. Perjalanan Menengah (Medium trips) juga cukup umum, sementara perjalanan Panjang (Long trips) lebih jarang terjadi. Hal ini bisa mengindikasikan bahwa taksi lebih sering digunakan untuk perjalanan dalam kota dibandingkan perjalanan jauh.

# Rekomendasi:

1. Fokus pada wilayah Manhattan di zona East Harlem North dan East Harlem South selama weekdays. Hal ini dapat dilakukan dengan cara meningkatkan armada taksi di zona tersebut sedangkan saat weekend mencoba untuk membagi distribusi peningkatan armada taksi antara Manhattan dan Brooklyn dikarenakan dilihat dari data menunjukkan bahwa Brooklyn ketika weekend memiliki potensi untuk meningkatkan penghasilan dikarenakan saat bulan Januari 2023, penghasilan di wilayah Brooklyn saat weekend lebih tinggi jika dibandingkan dengan weekdays.

2. Untuk mempertahankan banyaknya permintaan pickup dari penumpang maka dapat dicoba untuk memberikan penawaran khusus bagi penumpang yang sering naik taksi. Hal ini dapat dilakukan dengan cara membuat program loyalty card dengan teknik mengumpulkan poin berdasarkan miles perjalanan taksi yang ditumpangi sehingga nantinya bisa memperoleh potongan harga untuk perjalanan selanjutnya.

3. Setiap taxi dipasangkan fasilitas pembayaran untuk credit card karena mayoritas penumpang membayar menggunakan credit card. Dapat melakukan kerjasama dengan perusahaan penyedia credit card supaya dapat mendorong pelanggan menggunakan credit card dengan benefit yang menguntungkan pelanggan, contoh bentuk kerjasama nya yaitu (https://www.bluebirdgroup.com/promo/diskon-rp-10-ribu-di-mybluebird-pakai-kartu-kredit-bca?lang=id)

4. Fokuskan Operasi di Wilayah Manhattan pada Jam Sibuk karena Manhattan memiliki jumlah dan rata-rata tip tertinggi. Prioritaskan area Manhattan terutama saat rush-hour (16:00–18:00). Edukasi Pengemudi tentang Pengaruh Pelayanan terhadap Tip karena Tip juga dipengaruhi oleh kualitas layanan (ramah, membantu, tepat waktu).

5. Memfokuskan armada pada area manhattan, queens, dan brooklyn untuk weekday

6. Operator taksi bisa meningkatkan tarif dasar untuk perjalanan pendek agar tetap menguntungkan, Menawarkan insentif untuk perjalanan panjang, seperti diskon atau harga tetap untuk rute tertentu.

# Link Tableu Public 
https://public.tableau.com/app/profile/ikhsan.herdi.fajriyanto/viz/IkhsanHerdi/Dashboard1

# Link PPT 
https://www.canva.com/design/DAGj6Q8GysI/WHgEsSMu4N5iXAeZGQpVwQ/edit?utm_content=DAGj6Q8GysI&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton
