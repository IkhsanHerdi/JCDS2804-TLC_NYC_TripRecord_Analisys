# TLC NYC Trip Record Analysis

Dalam era digital, transportasi berbasis data telah menjadi kunci dalam pengelolaan sistem mobilitas perkotaan. Salah satu sumber data yang sering digunakan dalam analisis transportasi adalah NYC TLC Trip Record Dataset. Dataset ini disediakan oleh New York City Taxi and Limousine Commission (TLC), yang mencatat perjalanan taksi di kota New York, termasuk taksi kuning (Yellow Taxi) dan taksi hijau (Green Taxi).

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
