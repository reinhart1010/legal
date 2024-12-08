# Panduan Verifikasi Tanda Tangan Elektronik

**Terakhir Dimutakhirkan:** 12 Desember 2024

Tanda Tangan Elektronik (TTE) merupakan salah satu metode untuk memverifikasi keaslian data elektronik menggunakan metode *hashing*, enkripsi, dan dekripsi untuk memastikan isi berkas atau objek secara digital telah sesuai dengan kunci verifikasi objek digital dan hasil verifikasi yang diharapkan.

Dalam hukum Republik Indonesia, penggunaan Tanda Tangan Elektronik disahkan melalui:

1. pengakuan umum terhadap maksud, tujuan, dan keabsahan hukum Tanda Tangan Elektronik dalam [Undang-Undang Nomor 11 Tahun 2008](https://peraturan.go.id/id/uu-no-11-tahun-2008);
2. pengakuan terhadap syarat dan peran Penyelenggara Sertifikasi Elektronik (PSrE) sebagaimana tercantum dalam [Peraturan Pemerintah (PP) Nomor 71 Tahun 2019](https://peraturan.go.id/id/pp-no-71-tahun-2019); serta
3. penetapan lembaga dan teknis pendaftaran Penyelenggara Sertifikasi Elektronik (PSrE) di bawah naungan Kementerian Komunikasi dan Informatika (kini Kementerian Informasi dan Digital) dalam [Peraturan Menteri Komunikasi dan Informatika Nomor 11 Tahun 2022](https://peraturan.go.id/id/permenkominfo-no-11-tahun-2022).

> [!NOTE]
> 
> **Keabsahan Tanda Tangan Elektronik menurut Undang-Undang**
> 
> Berikut adalah Isi dan Penjelasan atas [Undang-Undang Nomor 11 Tahun 2008 Tentang Informasi Dan Transaksi Elektronik](https://peraturan.go.id/id/uu-no-11-tahun-2008) Pasal 11 ayat (1), sebagaimana tetap berlaku menurut [Undang-Undang Nomor 19 Tahun 2016](https://peraturan.go.id/id/uu-no-19-tahun-2016) dan [Undang-Undang Nomor 1 Tahun 2024](https://peraturan.go.id/id/uu-no-1-tahun-2024):
> 
> ---
>
> **ISI**
> 
> Tanda Tangan Elektronik memiliki kekuatan hukum dan
akibat hukum yang sah selama memenuhi persyaratan
sebagai berikut:
> + a. data pembuatan Tanda Tangan Elektronik terkait hanya kepada Penanda Tangan;
> + b. data pembuatan Tanda Tangan Elektronik pada saat proses penandatanganan elektronik hanya berada dalam kuasa Penanda Tangan;
> + c. segala perubahan terhadap Tanda Tangan Elektronik yang terjadi setelah waktu penandatanganan dapat diketahui;
> + d. segala perubahan terhadap Informasi Elektronik yang terkait dengan Tanda Tangan Elektronik tersebut setelah waktu penandatanganan dapat diketahui;
> + e. terdapat cara tertentu yang dipakai untuk mengidentifikasi siapa Penandatangannya; dan
> + f. terdapat cara tertentu untuk menunjukkan bahwa Penanda Tangan telah memberikan persetujuan terhadap Informasi Elektronik yang terkait.
> 
> ---
>
> **PENJELASAN**
> 
> Undang-Undang ini memberikan pengakuan secara tegas bahwa meskipun hanya merupakan suatu kode, Tanda Tangan Elektronik memiliki kedudukan yang sama dengan tanda tangan manual pada umumnya yang memiliki kekuatan hukum dan akibat hukum.
> 
> Persyaratan sebagaimana dimaksud dalam Pasal ini merupakan persyaratan minimum yang harus dipenuhi dalam setiap Tanda Tangan Elektronik. Ketentuan ini membuka kesempatan seluas-luasnya kepada siapa pun untuk mengembangkan metode, teknik, atau proses pembuatan Tanda Tangan Elektronik.

## Legalitas Metode Tanda Tangan Elektronik yang Digunakan Reinhart Previano Koentjoro

Perlu diketahui bahwa tidak semua Tanda Tangan Elektronik yang digunakan secara resmi oleh Reinhart Previano Koentjoro merupakan bagian dari penyelenggaraan sertifikasi elektronik yang memenuhi ketentuan hukum Republik Indonesia. Tabel berikut menjelaskan daftar jenis/metode penandatanganan berkas, dokumen, dan/atau objek elektronik yang digunakan beserta status kekuatan hukum beserta alasannya.

| Jenis/Metode | Memiliki Kekuatan Hukum | Keterangan |
|---|:-:|---|
| [Android App Signing](https://developer.android.com/studio/publish/app-signing) dan [Google Play App Signing](https://support.google.com/googleplay/android-developer/answer/9842756?hl=id) | ❌ TIDAK | Penandatanganan berkas Android berasal dari metode Java Keystore yang tidak memiliki lembaga penengah. Selain itu, [Google Play App Signing](https://support.google.com/googleplay/android-developer/answer/9842756?hl=id) tidak memiliki kekuatan hukum karena Google tidak merupakan PSrE yang terdaftar secara resmi oleh Kementerian Komunikasi dan Digital (Desember 2024). |
| Java Keystore | ❌ TIDAK | Digunakan dalam penandatanganan berkas aplikasi Android ([Android App Signing](https://developer.android.com/studio/publish/app-signing)). Metode penandatanganan ini tidak menunjuk lembaga penengah apapun untuk menerbitkan dan mengatur pasangan kunci publik dan privat untuk melakukan proses penandatanganan berkas, sehingga tidak layak untuk memenuhi persyaratan pendaftaran Penyelenggara Sertifikasi Elektronik. |
| Meterai Elektronik (e-Meterai) | ✅ BERKEKUATAN | Ketentuan Meterai Elektronik diatur dalam [Undang-Undang Nomor 10 Tahun 2020](https://peraturan.go.id/id/uu-no-10-tahun-2020), [Peraturan Pemerintah Nomor 86 Tahun 2021](https://peraturan.go.id/id/pp-no-86-tahun-2021), dan [Peraturan Menteri Keuangan Nomor 134 Tahun 2021](https://peraturan.go.id/id/permenkeu-no-134-pmk-03-2021-tahun-2021). Kami menerima penggunaan Meterai Elektronik sebagaimana mestinya, dan secara teknis, pembubuhan Meterai Elektronik dalam berkas PDF mengikuti standar Tanda Tangan Elektronik PDF sebagaimana umumnya ditawarkan oleh PSrE terdaftar di Indonesia. |
| PDF | ✅ SEBAGIAN | Hanya tanda tangan yang disahkan melalui platform [PSrE yang terdaftar](https://tte.kominfo.go.id/listpsrenew) saja yang memiliki kekuatan hukum Republik Indonesia. Apabila kami menerima dokumen PDF yang ditandatangani oleh platform lainnya, maka keabsahan akan ditentukan berdasarkan status registrasi PSrE serupa dalam jurisdiksi asal pembubuh Tanda Tangan Elektronik. |
| OpenPGP | ❌ TIDAK | Metode penandatanganan ini tidak menunjuk lembaga penengah apapun untuk menerbitkan dan mengatur pasangan kunci publik dan privat untuk melakukan proses penandatanganan berkas, sehingga tidak layak untuk memenuhi persyaratan pendaftaran Penyelenggara Sertifikasi Elektronik. |

## Jenis Tanda Tangan Elektronik yang Digunakan per Objek

Berikut adalah rangkuman jenis Tanda Tangan Elektronik yang dikelola secara resmi oleh Reinhart Previano Koentjoro.

| Jenis Objek | Jenis Tanda Tangan Elektronik | Catatan |
|---|---|---|
| Aplikasi Android (APK, AAB) | [Android App Signing](https://developer.android.com/studio/publish/app-signing) | Berlaku sejak Juni 2024. Kunci privat Java Keystore (`.jks`) dikelola secara mandiri; tidak menggunakan [Google Play App Signing](https://support.google.com/googleplay/android-developer/answer/9842756?hl=id). |
| Komit Git | [OpenPGP](https://pgp.reinhart1010.id) | Berlaku sejak 2022 dengan pergantian kunci privat sebanyak 2 (dua) kali karena alasan kehilangan. Kunci publik yang saat ini berlaku adalah [`EB75 3357`](https://pgp.reinhart1010.id) ([.asc](https://reinhart1010.id/key.asc)). |
| PDF | [TTE Tersertifikasi (PDF)](#cara-memverifikasi-tanda-tangan-pdf) | Berlaku sejak September 2024, dengan menunjuk Perum Percetakan Republik Indonesia (PERURI) melalui [PERURI Certificate Authority](https://ca.peruri.co.id/) sebagai pengelola Tanda Tangan Elektronik Tersertifikasi berbasis PDF. Perum Percetakan Uang Republik Indonesia (PERURI) adalah Penyelenggara Sertifikasi Elektronik (PSrE) yang terdaftar dalam Kementerian Komunikasi dan Digital Republik Indonesia. |

## Cara Memverifikasi Meterai Elektronik

Secara teknis, Meterai Elektronik menggunakan metode penandatangan yang sama dengan [Tanda Tangan Elektronik PDF](#cara-memverifikasi-tanda-tangan-pdf). Jika Anda menerima dokumen dengan gambar Meterai Elektronik ini, pastikan metadata berkas PDF tersebut juga memuat Tanda Tangan Elektronik PDF dengan nama lembaga penandatanganan `Meterai Elektronik 10000`.

![Tanda Tangan Elektronik pada Adobe Acrobat Reader](/assets/images/TTE%20Adobe%20Acrobat.png)

Keaslian Meterai Elektronik juga perlu dibuktikan melalui aplikasi **E-meterai Scanner** yang tersedia secara resmi oleh PERURI di [App Store](https://apps.apple.com/id/app/e-meterai-scanner/id6449962977) dan [Google Play Store](https://play.google.com/store/apps/details?id=com.peruri.emeteraiscanner&hl=id). Informasi tentang alamat surel (*email*) pembubuh meterai hanya dapat dilihat melalui aplikasi ini.

## Cara Memverifikasi Tanda Tangan OpenPGP

Informasi selengkapnya dapat dilihat pada <https://pgp.reinhart1010.id/id/how-to-use>.

Kami merekomendasikan pengguna perangkat BSD, Linux, macOS, Unix, dan Windows untuk menggunakan piranti lunak OpenPGP berbasis **GnuPG (GPG)** agar dapat menggunakan perintah-perintah `gpg` sebagaimana tercantum dalam tutorial kami.

## Cara Memverifikasi Tanda Tangan PDF

Tanda Tangan PDF dapat divalidasi dengan menggunakan aplikasi pembaca dokumen PDF (PDF Reader) yang juga mampu membaca metadata Tanda Tangan Digital, di antaranya:

+ [Adobe&reg; Acrobat Reader&reg;](https://get.adobe.com/reader/) (Android, iPadOS, iOS, macOS, Windows)
+ [Foxit&reg; PDF Reader](https://www.foxit.com/pdf-reader/) (macOS, Windows)
+ [Okular (KDE)](https://okular.kde.org/) (BSD, Linux, Unix, Windows)

![Tanda Tangan Elektronik pada Adobe Acrobat Reader](/assets/images/TTE%20Adobe%20Acrobat.png)

> [!TIP]
> 
> Jika Anda diberitahu bahwa Tanda Tangan Elektronik tersebut tidak valid karena Anda belum mempercayai keabsahan sertifikat inti, pastikan bahwa Anda memasukkan sertifikat inti [PERURI Certificate Authority](https://ca.peruri.co.id/) beserta [PSrE Terdaftar lainnya](https://rootca.id/) ke dalam daftar sertifikat yang dipercayai oleh aplikasi pembuka berkas PDF Anda.

Anda juga dapat mengetahui apakah berkas tersebut juga memiliki Tanda Tangan Elektronik (TTE) yang berasal dari Penyelenggara Sertifikasi Elektronik (PSrE) terdaftar dengan mengunggah berkas tersebut ke dalam situs <https://tte.kominfo.go.id/verifyPDF> maupun <https://verification.peruri.co.id/>.

![Perbandingan hasil tampilan verifikasi Tanda Tangan Elektronik PDF melalui situs PSrE Kominfo/Komdigi](/assets/images/Verifikasi%20TTE%20Kominfo%20-%20Tidak%20Valid.png)

> [!WARNING]
> 
> Hati-hati atas dokumen yang dinyatakan **tidak** memiliki Tanda Tangan Digital Tersertifikasi meskipun memiliki gambar Tanda Tangan Elektronik dan Meterai Elektronik sebagaimana dimaksud (seperti pada gambar sebelah kiri). Hal ini dapat menandakan adanya perubahan atau pemrosesan ulang atas sebagian atau keseluruhan isi dokumen yang tertandatangan, sehingga secara otomatis merusak segel Tanda Tangan Elektronik.

![Tampilan detail hasil verifikasi Tanda Tangan Elektronik PDF melalui situs PSrE Kominfo/Komdigi](/assets/images/Verifikasi%20TTE%20Kominfo%20-%20Valid.png)

## Media Sosialisasi dan Pemberitahuan Tanda Tangan Elektronik

Berikut adalah kumpulan pemberitahuan Tanda Tangan Elektronik (TTE) yang disematkan oleh kami ke dalam dokumen yang memiliki TTE, terutama TTE Tersertifikasi, yang mengikat kepada dokumen tersebut.

### Dalam Berkas PDF (Bahasa Indonesia)

> Dokumen PDF ini ditandatangani secara digital menggunakan Tanda Tangan OpenPGP serta Tanda Tangan Elektronik (TTE) Tersertifikasi sesuai standar dan ketentuan Penyelenggara Sertifikasi Elektronik (PSrE) oleh Kementerian Komunikasi dan Digital. Gunakan kunci publik (*public key*) OpenPGP dari <https://pgp.reinhart1010.id> (`reinhart@reinhart1010.id`, `EB75 3357`) untuk memverifikasi berkas tanda tangan OpenPGP yang disediakan secara terpisah (*detached*) dari berkas ini (sebagai berkas `.sig`). Untuk TTE Tersertifikasi dan Meterai Elektronik, pastikan data pihak penandatangan yang ditampilkan adalah benar `REINHART PREVIANO KOENTJORO`, dan jika menggunakan Meterai Elektronik, maka alamat surel/*email* `reinhart@reinhart1010.id` juga tercantum dalam informasi pembubuh meterai. Informasi lebih lanjut: <https://legal.reinhart1010.id/tanda-tangan-elektronik>.

> Dokumen PDF ini ditandatangani secara digital menggunakan Tanda Tangan Elektronik (TTE) Tersertifikasi sesuai standar dan ketentuan Penyelenggara Sertifikasi Elektronik (PSrE) oleh Kementerian Komunikasi dan Digital. Pastikan data pihak penandatangan yang ditampilkan adalah benar `REINHART PREVIANO KOENTJORO`, dan jika menggunakan Meterai Elektronik, maka alamat surel/*email* `reinhart@reinhart1010.id` juga tercantum dalam informasi pembubuh meterai. Informasi lebih lanjut: <https://legal.reinhart1010.id/tanda-tangan-elektronik>.

### Dalam Berkas PDF (Bahasa Inggris)

> This PDF document is digitally signed using the OpenPGP File Signature, as well as PDF Electronic Signatures in accordance to applicable Indonesian standards and laws of Electronic Certification Providers (PSrE). Use the OpenPGP public key at <https://pgp.reinhart1010.id> (`reinhart@reinhart1010.id`, `EB75 3357`) to verify the authenticity of this document with the separate, detached OpenPGP signature file (`.sig`). Ensure that the e-signatures are signed on behalf of `REINHART PREVIANO KOENTJORO`. Shall the document be notarized with an Electronic Duty Stamp (*Meterai Elektronik* / *e-Meterai*), ensure that the email address `reinhart@reinhart1010.id` is also visible on the duty stamp's applicant information. More information: <https://legal.reinhart1010.id/electronic-signatures>.

> This PDF document is digitally signed using the PDF Electronic Signatures in accordance to applicable Indonesian standards and laws of Electronic Certification Providers (PSrE). Ensure that the e-signatures are signed on behalf of `REINHART PREVIANO KOENTJORO`. Shall the document be notarized with an Electronic Duty Stamp (*Meterai Elektronik* / *e-Meterai*), ensure that the email address `reinhart@reinhart1010.id` is also visible on the duty stamp's applicant information. More information: <https://legal.reinhart1010.id/electronic-signatures>.
