# Latar Belakang
Sejak didirikan pada tahun 1971, New York City Taxi and Limousine Commission (TLC) telah berperan penting dalam mengatur industri transportasi umum berbayar di kota New York, yang mencakup taksi medali (taksi kuning ikonik New York), kendaraan sewa (seperti layanan antar-jemput komunitas, black car, dan limusin mewah), van komuter, dan kendaraan paratransit. Sebagai badan pengatur utama, TLC menetapkan standar tinggi bagi lebih dari 200.000 pemegang lisensi TLC yang beroperasi setiap hari, dengan jumlah perjalanan mencapai sekitar 1.000.000 perjalanan di seluruh kota. 

TLC kini menghadapi tantangan besar. Kota ini mengalami pertumbuhan jumlah penumpang yang sangat pesat, dan tren perjalanan di berbagai wilayah terus berubah. Dengan hampir satu juta perjalanan setiap hari, manajemen TLC berupaya untuk menjaga keseimbangan antara jumlah kendaraan di jalan dan permintaan transportasi di berbagai wilayah. Hal ini terutama penting mengingat kebutuhan pengaturan rute dan distribusi kendaraan sesuai dengan zona permintaan yang bervariasi, baik untuk menghindari penumpukan kendaraan di satu wilayah maupun untuk memastikan aksesibilitas di wilayah lain.

Sumber: [Di sini](https://www.nyc.gov/site/tlc/about/about-tlc.page).

# Stake Holder
**Manajer Operasional Armada**: Memiliki peran utama dalam mengoordinasikan distribusi dan mobilitas armada, memastikan armada selalu tersedia di area dengan permintaan tinggi untuk meminimalkan biaya operasional.

# Goal
Goals dari data analysis ini adalah:

1. Mengidentifikasi wilayah dengan kebutuhan armada tinggi: Menentukan wilayah mana yang memerlukan perhatian khusus dalam distribusi kendaraan agar armada lebih merata dan tersedia di area dengan permintaan tinggi.
  
2. Menganalisis penyesuaian harga yang tepat: Menentukan wilayah atau periode waktu yang mungkin memerlukan penyesuaian tarif, baik untuk meningkatkan efisiensi maupun untuk mengendalikan permintaan.

3. Merekomendasikan layanan tambahan yang dibutuhkan: Mengidentifikasi layanan tambahan yang dapat meningkatkan pengalaman pengguna dan memenuhi kebutuhan unik di setiap wilayah.

4. Meningkatkan efisiensi operasional: Menggunakan data untuk membantu mengurangi biaya operasional melalui distribusi armada yang optimal, pengelolaan permintaan yang lebih akurat, dan peningkatan layanan yang sesuai dengan pola perjalanan warga.


# Pernyataan Masalah
Dalam upaya menciptakan efisiensi operasional dan memenuhi kebutuhan warga New York yang terus berkembang, TLC menyadari pentingnya **menggali lebih dalam pola perjalanan dan permintaan di tiap wilayah**. Namun, berbagai keterbatasan data dan kendala di lapangan membuat upaya pengambilan keputusan ini tidak selalu berjalan mulus. TLC kini berupaya untuk mengeksplorasi data perjalanan agar tetap relevan dan efisien dalam melayani kota yang tak pernah tidur ini. 

 Sebagai Data Analyst, kita akan mencoba menjawab pertanyaan berikut: 
 **Bagaimana cara mengoptimalkan distribusi armada, penyesuaian tarif, dan penambahan layanan sesuai pola permintaan di berbagai wilayah untuk meningkatkan efisiensi operasional dan pengalaman pengguna?**

# Data
 Dataset ini berisi informasi terkait Waktu, lokasi dan informasi biaya perjalanan penumpang. Ada 20 kolom didalam dataset NYC TLC Trip Record, yaitu:

* VendorID    : ID untuk vendor taksi yang menyediakan record ini. 
     1 = Creative Mobile Technologies, LLC.
     2 = VeriFone Inc.

* lpep_pickup_datetime    :	Tanggal dan waktu pickup
* lpep_dropoff_datetime   :	Tanggal dan waktu dropoff
* store_and_fwd_flag      : Menunjukkan   apakah catatan perjalanan disimpan dalam memori kendaraan sebelum dikirim ke vendor, dikenal sebagai “simpan dan kirim”, karena kendaraan tidak memiliki koneksi ke server.

    Y = simpan dan kirim perjalanan
    N = bukan simpan dan kirim perjalanan
* RatecodeID	       : Kode tarif akhir berlaku di akhir perjalanan.
    1 = Tarif standar  
    2 = JFK  
    3 = Newark  
    4 = Nassau atau Westchester  
    5 = Tarif yang dinegosiasikan  
    6 = Perjalanan kelompok

* PULocationID : ID Lokasi Pickup yang sesuai dengan zona taksimeter diaktifkan
* DOLocationID : ID Lokasi Dropoff yang sesuai dengan zona taksimeter dinonaktifkan
* passenger_count	: Jumlah penumpang didalam kendaraan. 
* trip_distance : Jarak perjalanan yang ditempuh dalam mil yang dicatat oleh taksimeter.
* fare_amount	extra : Tarif berdasarkan waktu dan jarak dihitung oleh meteran.
* extra : Biaya tambahan. Saat ini, hanya mencakup biaya $0,50 untuk jam sibuk dan $1 untuk tarif malam hari.
* mta_tax : Pajak MTA sebesar $0,50 yang secara otomatis dikenakan berdasarkan tarif meteran yang digunakan.
* tip_amount	: Jumlah tip yang menggunakan kartu kredit. Tip tunai tidak termasuk.
* tolls_amount : Total seluruh biaya tol yang dibayarkan dalam perjalanan
* ehail_fee : Biaya tambahan sebesar 1 dolar yang otomatis dikenakan untuk setiap perjalanan yang dipesan melalui platform ehail.
* improvement_surcharge : Biaya peningkatan sebesar $0,30 dikenakan pada perjalanan yang dihentikan di tempat. Biaya peningkatan ini mulai diberlakukan pada tahun 2015.
* total_amount : Total biaya yang ditagih kepada penumpang. Tip Cash tidak termasuk
* payment_type	: Kode numerik mengejai bagaimana tipe pembayaran penumpang
 1 = Credit card
 2 = Cash
 3 = No charge
 4 = Dispute
 5 = Unknown
 6 = Voided trip

* trip_type	: Perjalanan ini merupakan hasil dari penumpang menghentikan taksi di jalan atau dari pemesanan yang otomatis ditetapkan berdasarkan tarif meteran yang digunakan, tetapi dapat diubah oleh pengemudi.

 1 = Hentian di jalan  
 2 = Pemesanan
* congestion_surcharge    : Biaya kemacetan sebesar 2,75 dolar untuk perjalanan dengan taksi kuning dan hijau di Manhattan selatan dari 96th St. Biaya tambahan ini mulai dikenakan pada tahun 2019



