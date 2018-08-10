# A/B Testing (Courtesy to Udacity)
## _So, what is A/B Testing?_

Sesuai namanya, A/B Testing adalah metode untuk menguji mana yang lebih baik (_A or B?_). Karena hurufnya berbeda, tentunya A dan B ini adalah dua hal yang berbeda pula, namun tetap pada 'jenis' yang sama. Contohnya, misalkan kita adalah pemilik suatu website dan kita ingin semakin banyak orang yang membuat akun di website kita. Untuk membuat akun tersebut, seseorang dapat meng-klik tombol "Sign Up". Kita ingin mencari tahu apakah mengganti tulisan "Sign Up" menjadi "Sign Up for Free" dapat menaikkan jumlah akun di website kita. Perhatikan bahwa kedua-duanya merupakan website.

<a href="https://ibb.co/c9BF6K"><img src="https://preview.ibb.co/notTRK/1.jpg" alt="1" border="0"></a><br />

Dalam A/B Testing ada 2 variabel yaitu variabel kontrol dan variabel eskperimen. Variabel eksperimen yaitu variabel yang mengalami perubahan. Pada contoh diatas, variabel kontrol adalah "Sign Up" dan variabel ekspresimen adalah "Sign Up for Free". Hasil yang kita harapkan adalah terjadinya peningkatan jumlah akun yang signifikan terhadap variabel eksperimen. Tujuan kita membuat perubahan adalah menaikkan jumlah akun, sehingga jumlah akun merupakan ukuran seberapa baik eksperimen kita (yang selanjutnya akan kita sebut sebagai **metrics**). Cara menentukan **metrics** itu sendiri akan dibahas nanti. Kita juga perlu memperhatikan apakah peningkatan yang terjadi signifikan atau tidak. Misalkan terjadi peningkatan jumlah akun sebanyak 1, apakah peningkatan ini signifikan? Cara menentukannya juga akan dibahas kemudian.

Dalam A/B Testing, user dibagi menjadi 2 kelompok yaitu user yang menggunakan variabel kontrol dan user yang menggunakan variabel eksperimen. Kedua kelompok itu berisi dengan user yang berbeda sehingga tidak ada user yang mencoba kedua-duanya. Data-data dari setiap user ini kemudian akan diteliti.

<a href="https://ibb.co/chqFqe"><img src="https://preview.ibb.co/icmYbK/3.jpg" alt="3" border="0"></a><br /><br />


## Apakah A/B Test Bisa Dipakai untuk Membandingkan Hal Apapun?
_Unfortunately, No_. Ada 2 hal yang tidak bisa diuji menggunakan A/B Testing, yaitu:
1. _New Experience_ bagi user. \
_New experience_ disini berarti user hanya mencoba variabel eksperimen saja dan tidak pernah mencoba variabel kontrol. Ada 2 hal yang dikhawatirkan, yaitu apa dasar dari perbandingan yang kita buat dan berapa waktu yang dibutuhkan agar user lama bisa menyesuaikan diri dengan perubahan tersebut. 

2. Variabel yang membutuhkan waktu cukup lama untuk pengambilan datanya. \
Contohnya sebuah web rental rumah ingin menguji apakah metode _referral_ yang dilakukan berhasil atau tidak. Namun, _customer_ belum tentu kembali bahkan setelah 6 bulan. Sehingga, sangat sulit untuk melakukan A/B Testing pada kasus seperti ini.

<a href="https://ibb.co/bv4Bfe"><img src="https://preview.ibb.co/kvCa6K/2.jpg" alt="2" border="0"></a>

## Kode Etik dalam A/B Testing
1. Risiko \
Kita harus bisa memastikan risiko apa yang bisa terjadi pada user kita dan memberitahukannya apabila dirasa berdampak cukup besar bagi pengguna. Misalkan sebuah aplikasi diet memberitahukan saran diet apa saja yang harus dijalani oleh sang pengguna aplikasi. Apabila saran yang diberikan salah, kesehatan pengguna aplikasi tersebut dapat terganggu, sehingga penting untuk memberitahu konsekuensi dari diet tersebut kepada pengguna.

2. Keuntungan \
Apa saja keuntungan yang bisa didapatkan dari A/B Testing yang kita lakukan. Kita harus bisa menyebutkan tujuan dari eksperimen kita.

3. Alternatif \
Pilihan apalagi yang dimiliki oleh user? Seperti contohnya kita ingin mengubah suatu fitur dari _search engine_. User memiliki pilihan untuk menggunakan _search engine_ yang lain. Semakin sedikit alternatif yang dimiliki seseorang, semakin muncul pertimbangan apakah sebenarnya user memiliki pilihan lain atau tidak. 

4. Sensitivitas Data \
Kita harus memastikan apakah user tau data apa saja yang diambil dari mereka, risiko apa saja yang akan mereka tanggung apabila informasi tersebut dibuat menjadi informasi publik, dan apakah user lebih mengingingkan data mereka bersifat privasi atau publik.

## _Next_, Bagaimana Cara untuk Melakukan A/B Testing?
Secara singkat, ada 5 tahap untuk melakukan A/B Testing:
1. Pilih metrics untuk mengevaluasi eksperimen
2. Pilih _significance level (alpha), statistical power (1-beta)_ dan _practical significance level_
3. Hitung berapa jumlah sampel yang dibutuhkan
4. Tentukan sampel untuk variabel kontrol dan eksperimen
5. Analisa hasilnya dan tarik kesimpulan

Kelima tahap ini akan dibahas satu per satu dibawah.

## 1a. Bagaimana cara memilih metrics?
Metric yang kita pilih untuk _sanity check_ disebut sebagai metric invarian. Metric invarian tidak dipengaruhi oleh eksperimen.

Metric evaluasi yang kita pilih digunakan untuk mengukur variasi mana yang lebih baik.

Ada 4 tipe metric yang harus diperhatikan:
1. _Sums_ dan _counts_

2. Mean, Median, Persentil

3. _Probabilities_ and _Rates_

4. Ratios

Selain memilih kategori dari metrics, ada 2 hal yang harus diperhatikan dalam memilih metric yaitu sensitivitas dan _robustness_. Kita ingin memilih metric yang memiliki sensitivitas yang tinggi, artinya metric tersebut dapat mencatat hasil yang kita cari. Kita juga ingin memilih metric yang _robust_, artinya metric tersebut tidak akan berubah banyak ketika ada sesuatu yang tidak kita inginkan terjadi. 

## 1b. Metode menentukan metrics 
1. Data Eksternal: Data dari orang luar perusahaan
2. In-Depth Data:
    - UER (_User Experience Research_) \
      Metode paling dalam dan intensif, dan bisa pula merupakan gabungan dari memerhatikan kebiasaan user dan memberi pertanyaan.

    - _Focus Groups_ \
      Mengumpulkan sekelompok user atau user potensial untuk membentuk sebuah diskusi forum.

    - Surveys \
      Kelemahan dari metode ini yaitu belum tentu data yang diberikan oleh user benar.

3. _Restropective Analysis_ \
   Menganalisa data observasi tanpa harus melakukan eksperimen. Metode ini sangat berguna untuk mencari ide yang akan digunakan dalam A/B Test dan menvalidasi metrics.

4. _Long-term Prospective Experiments_ \
   Mencari metric yang dapat diukur dalam jangka waktu pendek dan dapat digunakan untuk memprediksi perubahan pada jangka waktu panjang.

5. _Human Evaluation_ atau _Crowd Sourcing_ \
   Membayar orang (_raters_) untuk melakukan pekerjaan tertentu.

## 2. Menentukan _significance level ($\alpha$), statistical power ($1-\beta$)_, dan _practical significance level_

- _Significance level_ ($\alpha$): Peluang menolak $H_0$ saat $H_0$ benar.

- _Statistical power_ ($1-\beta$): Peluang menolak $H_0$ saat $H_0$ salah.

- _Practical significance level_: Ukuran seberapa besar pengaruh eksperimen. 

*Pengertian mengenai ketiga hal diatas dapat ditemukan di [sini](https://atrium.lib.uoguelph.ca/xmlui/bitstream/handle/10214/1869/A_Statistical_versus_Practical_Significance.pdf?sequence=7) \
** Pengertian mengenai $H_0$ (_Null Hypothesis_) dan $H_1$ dapat ditemukan di [sini](https://study.com/academy/lesson/what-is-a-null-hypothesis-definition-examples.html)

## 3. Cara menentukan jumlah sampel yang dibutuhkan ##
Sebelum menentukan jumlah sampel yang dibutuhkan, harus diperhatikan pilihan metric, pilihan subjek, dan pilihan populasi karena mempengaruhi variabilitas dari metric.

Hal -hal yang perlu dipertimbangkan dalam mementukan jumlah sampel:
- Subjek (_unit of diversion_)  

- Populasi: siapa saja yang cocok untuk eksperimen ini \
Contohnya eksperimen untuk menguji coba tipe obat batuk baru cocok untuk diujikan ke pasien yang sedang batuk.

Cara mengurangi jumlah sampel eksperimen supaya eksperimennya berjalan lebih cepat:
1. Menambah nilai $\alpha$
2. Menambah nilai ($1-\beta$)
3. Mengganti _unit of diversion_ menjadi _unit of analysis_ (subjek pada metric yang akan dipakai untuk membandingkan hasil)

Gunakan web [ini](http://www.evanmiller.org/ab-testing/sample-size.html) untuk menguji coba parameter apa saja yang dapat menurunkan jumlah sampel.

## 4. Cara menentukan sampel dari variabel kontrol maupun eksperimen

Hal-hal yang perlu diperhatikan:
1. Kapan waktu paling pas untuk melakukan eksperimen

2. Berapa % dari populasi yang ingin diuji coba

3. _Learning Effect_ \
Saat ada perubahan, awalnya users mungkin tidak terbiasa dengan perubahan tersebut. Namun seiring berjalannya waktu, kebiasaan dari user akan semakin stabil. Tentunya proses ini memakan waktu dan perlu diperhatikan juga lama waktu yang diperlukan ini.

## 5. Cara menganalisa hasil dan membuat kesimpulan

Langkah-langkah:
1. _Sanity Check_ \
Periksa apakah metric memiliki perubahan. Jika tidak ada perubahan, periksa kenapa tidak ada perubahan. Bisa dengan _reprospective analysis_ atau lihat apakah ada _learning effect_.

2. Analisa hasil 
    * Jika metric hanya satu dan tidak signifikan, perlu dilakukan langkah-langkah berikut ini:
        * Pastikan memang hasil dari eksperimen benar-benar tidak memberikan perbedaan yang signifikan. 
        *  _Cross-check_ dengan metode yang berbeda
    * Jika mengamati banyak metric dalam waktu yang bersamaan
        * Masalah yang mungkin terjadi yaitu terlihat perbedaan tapi penyebabnya tidak sesuai. Ada beberapa cara untuk menanggulangi ini:
            1. Lakukan bootstrap dan jalankan eksperimen selama beberapa kali. Metric yang signifikan akan hilang apabila memang perbedaan itu hanya kebetulan

            2. _Bonferroni correction_ \
            Bagi $\alpha$ dengan 20.

            3. Mengontrol _Family Wise Error Rate_ (FWER)\
             peluang suatu metric menghasilkan hasil yang signifikan tapi sebenarnya tidak demikian (_false positives_)

            4. Mengontrol _False Discovery Rate_ (FDR):

            $$\frac{\text{banyak} \hspace{1mm} false \hspace{1mm} positives}{ \text{banyak} \hspace{1mm} total \hspace{1mm} rejections}$$ 
        * Masalah lain yang mungkin terjadi yaitu ketika beberapa metric tidak bersesuaian dengan apa yang kita mau. \
        Misalnya kita berharap banyaknya orang yang melihat web kita dan lamanya orang tersebut di web kita sama-sama bertambah. Namun, yang terjadi adalah banyaknya orang yang melihat web kita berkurang namun lamanya orang di web bertambah. Sehingga, perlu di cek lagi apa yang menyebabkan itu terjadi. \
        Hal ini menyebabkan banyak orang memiliki suatu OEC (_Overall Evaluation Criterion_). Sebuah OEC yang baik memberikan keseimbangan antara tujuan jangka pendek dan tujuan jangka jauh atau keseimbangan antara tiap metrics. Memiliki OEC juga membantu kita mengerti tentang apa yang bisnis kita inginkan, dan bagaimana cara menyeimbangkan metrics.

3. Terakhir, ambil kesimpulan! \
 Jika kita punya hasil yang signifikan dari eksperimen kita, maka akan muncul beberapa pertanyaan: apakah kita mengerti perubahannya? Apakah kita mau mau memakai eksperimen kita? Bagaimana jika eksperimen kita hanya berdampak positif untuk sebagian user aja? \
 _Gimana cara menentukan apakah eksperimen ini harus kita pakai atau tidak?_
> Tanyakan kepada diri kita sendiri beberapa hal ini:
> * Apakah hasil kita cukup _statistically significant_ dan _practically significant_ untuk bisa dipakai?
> * Apakah kita mengerti akibat dari perubahan terhadap _experience_ user kita?
> * Apakah eksperimen kita _worth it_ untuk digunakan?            