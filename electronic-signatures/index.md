# Electronic Signature Verification Guide

**Last Updated:** 12 December 2024

Electronic Signatures (e-signatures) are one of the common ways to verify the authenticity of electronic data by hashing, encrypting, and decrypting the contents altogether with the necessary encryption or verification keys to ensure that the exact notarized copy of the data or document is being supplied on behalf of the author(s).

The use of Electronic Signatures (*Tanda Tangan Elektronik* / TTE) is acknowledged and regulated in the Republic of Indonesia through the following legal products and frameworks:

1. [Undang-Undang Nomor 11 Tahun 2008](https://peraturan.go.id/id/uu-no-11-tahun-2008) which acknowledges the definition, purpose, and legality of electronic signatures in the Indonesian legal processing basis;
2. [Peraturan Pemerintah (PP) Nomor 71 Tahun 2019](https://peraturan.go.id/id/pp-no-71-tahun-2019) which acknowledges the role of Electronic Certification Providers (*Penyelenggara Sertifikasi Elektronik* / PSrE) in administering the digital document and data certification process; as well as
3. [Peraturan Menteri Komunikasi dan Informatika Nomor 11 Tahun 2022](https://peraturan.go.id/id/permenkominfo-no-11-tahun-2022) which further regulates the certifications of Electronic Certification Providers (*Penyelenggara Sertifikasi Elektronik* / PSrE) under the Ministry of Communication and Informatics (now Ministry of Communication and Digital Affairs).

The [Indonesian version of this document](/tanda-tangan-elektronik/) provides a thorough legal review of electronic signatures for use in Indonesian legal processing, including Electronic Duty Stamps (*Meterai Elektronik* / *e-Meterai*) to substitute the paper-based Duty Stamps in order to legally process certain types of documents, such as legal contracts.

## Legality of Reinhart Previano Koentjoro's Preferred Electronic Signature Mechanisms

It is important to note that not all types and methods of Electronic Signature do meet Indonesian standards for legal processing, as outlined in [Undang-Undang Nomor 11 Tahun 2008](https://peraturan.go.id/id/uu-no-11-tahun-2008) (Pasal 11 Ayat (1)). The following table lists of Reinhart Previano Koentjoro's preferred electronic signing methods and the legal status of such mechanism.

| Type/Method | Notarizable | Description |
|---|:-:|---|
| [Android App Signing](https://developer.android.com/studio/publish/app-signing) and [Google Play App Signing](https://support.google.com/googleplay/android-developer/answer/9842756?hl=en) | ❌ NO | Android app signing are based on Java Keystore mechanisms which does not require the use of Certificate Authorities. In addition to the fact, Google with [Play App Signing](https://support.google.com/googleplay/android-developer/answer/9842756?hl=en) is not a registered Electronic Certification Provider (PSrE) by the Ministry of Communication and Digital Affairs of Republic of Indonesia (as of December 2024). |
| Electronic Duty Stamps / *Meterai Elektronik* (*e-Meterai*) | ✅ NOTARIZABLE | As sanctioned in [Undang-Undang Nomor 10 Tahun 2020](https://peraturan.go.id/id/uu-no-10-tahun-2020), [Peraturan Pemerintah Nomor 86 Tahun 2021](https://peraturan.go.id/id/pp-no-86-tahun-2021), and [Peraturan Menteri Keuangan Nomor 134 Tahun 2021](https://peraturan.go.id/id/permenkeu-no-134-pmk-03-2021-tahun-2021). We receive the use of Electronic Duty Stamps as sanctioned, which uses the same technology as general PDF Electronic Signature mechanisms. |
| Java Keystore | ❌ NO | Used in [Android App Signing](https://developer.android.com/studio/publish/app-signing). This method does not enforce the use of Certificate Authorities (CAs) to regulate the use and notarization of key pairs, which are otherwise important to fulfill the legal requirements of Electronic Certification Provider (PSrE) administration. |
| PDF | ✅ PARTIALLY NOTARIZABLE | Only PDF Electronic Signatures that are signed from [registered Electronic Certification Providers (PSrE)](https://tte.kominfo.go.id/listpsrenew) and their platforms that are notarizable by Indonesian laws. If we receive PDF Electronic Signatures that are signed through the use of other platforms and services, we will process it accordingly to the legal status of such systems, operators, and/or affiliated organizations in the jurisdiction of the Electronic Signature Applicant. |
| OpenPGP | ❌ NO | This method does not enforce the use of Certificate Authorities (CAs) to regulate the use and notarization of key pairs, which are otherwise important to fulfill the legal requirements of Electronic Certification Provider (PSrE) administration. |

## Types of Electronic Signatures by Types of Signable Objects

The following table lists of types and methods of Electronic Signature that are being officially used by Reinhart Previano Koentjoro.

| Type of Signable Object | Type(s) of Applicable Electronic Signature | Note |
|---|---|---|
| Android application (APK, AAB) | [Android App Signing](https://developer.android.com/studio/publish/app-signing) | Used since June 2024. The Java Keystore (`.jks`) files are self-provided and managed; without the use of [Google Play App Signing](https://support.google.com/googleplay/android-developer/answer/9842756?hl=id). |
| Git commits | [OpenPGP](https://pgp.reinhart1010.id) | Used since 2022 with 2 (two) root key changes for being lost and stolen. The current valid OpenPGP public key is [`EB75 3357`](https://pgp.reinhart1010.id) ([.asc](https://reinhart1010.id/key.asc)). |
| PDF | [Certified PDF Electronic Signatures](#how-to-verify-the-pdf-electronic-signature-e-sign) | Used since September 2024, through the use of [PERURI Certificate Authority](https://ca.peruri.co.id/) to manage digital signatures for PDF documents. Perum Percetakan Uang Republik Indonesia (PERURI) is a Registered Electronic Certification Provider (PSrE) in the Ministry of Communication and Digital Affairs of Republic Indonesia. |

## How to Verify Indonesian Electronic Duty Stamps

Indonesian Electronic Duty Stamps (*Meterai Elektronik* / *e-Meterai*) are signed using the exact same mechanism with [PDF Electronic Signatures](#how-to-verify-the-pdf-electronic-signature-e-sign). If you receive a PDF document with an Electronic Duty Stamp, ensure that the PDF is digitally signed with an authority named `Meterai Elektronik 10000`.

![PDF Electronic Signatures on Adobe Acrobat Reader](/assets/images/TTE%20Adobe%20Acrobat.png)

In addition to verifying the Duty Stamp's PDF Electronic Signature, you will also need to verify the contents of the Stamp by scanning it on the **E-meterai Scanner** mobile app, as officially released by PERURI on [App Store](https://apps.apple.com/id/app/e-meterai-scanner/id6449962977) and [Google Play](https://play.google.com/store/apps/details?id=com.peruri.emeteraiscanner&hl=en). Note that the Stamp Applicant's email address can only be revealed through the use of the app.

## How to Verify the OpenPGP Signature

More information can be found on <https://pgp.reinhart1010.id/how-to-use>.

We recommend BSD, Linux, macOS, Unix, and Windows users to use OpenPGP clients that are based on **GnuPG (GPG)** to be able to use the `gpg` command-line utility as mentioned in our tutorials.

## How to Verify the PDF Electronic Signature (e-Sign)

All PDF Electronic Signatures can be verified directly through PDF reader applications that supports them, including:

+ [Adobe&reg; Acrobat Reader&reg;](https://get.adobe.com/reader/) (Android, iPadOS, iOS, macOS, Windows)
+ [Foxit&reg; PDF Reader](https://www.foxit.com/pdf-reader/) (macOS, Windows)
+ [Okular (KDE)](https://okular.kde.org/) (BSD, Linux, Unix, Windows)

![PDF Electronic Signatures on Adobe Acrobat Reader](/assets/images/TTE%20Adobe%20Acrobat.png)

> [!TIP]
> 
> If your PDF reader warns that the document is unverified due to the lack of trust in the Certificate Authorities, ensure that you have trusted [PERURI Certificate Authority](https://ca.peruri.co.id/) as well as [other legally-registered Electronic Certification Providers (PSrE) in Indonesia](https://rootca.id/) into your PDF reader settings.

You can also verify the Electronic Signatures, especially those from registered Electronic Certification Providers (PSrE) in Indonesia, by uploading the file into the official PSrE/TTE Verification websites on <https://tte.kominfo.go.id/verifyPDF> or <https://verification.peruri.co.id/>.

![Comparison of PSrE/TTE Verification status](/assets/images/Verifikasi%20TTE%20Kominfo%20-%20Tidak%20Valid.png)

> [!WARNING]
> 
> Beware of PDF documents that does **not** bear the electronic signatures in their metadata despite showing such labels inside the document, as shown on the image on the left. This may indicate tampering on the contents of the document, which will automatically tamper the Electronic Signatures inside.
> 
> Only trust the documents that are verified with the status `Dokumen ini memiliki tanda tangan digital` (*lit.* This document contains electronic signature(s)) as shown on the image on the right.

![Tampilan detail hasil verifikasi Tanda Tangan Elektronik PDF melalui situs PSrE Kominfo/Komdigi](/assets/images/Verifikasi%20TTE%20Kominfo%20-%20Valid.png)

## Socialization and Notice Materials for Electronic Signatures

The following is a collection of Electronic Signature (TTE) notices embedded by us into documents that have a TTE, especially Certified TTE, which are binding on the document.

### For PDF-based documents (Bahasa Indonesia)

> Dokumen PDF ini ditandatangani secara digital menggunakan Tanda Tangan OpenPGP serta Tanda Tangan Elektronik (TTE) Tersertifikasi sesuai standar dan ketentuan Penyelenggara Sertifikasi Elektronik (PSrE) oleh Kementerian Komunikasi dan Digital. Gunakan kunci publik (*public key*) OpenPGP dari <https://pgp.reinhart1010.id> (`reinhart@reinhart1010.id`, `EB75 3357`) untuk memverifikasi berkas tanda tangan OpenPGP yang disediakan secara terpisah (*detached*) dari berkas ini (sebagai berkas `.sig`). Untuk TTE Tersertifikasi dan Meterai Elektronik, pastikan data pihak penandatangan yang ditampilkan adalah benar `REINHART PREVIANO KOENTJORO`, dan jika menggunakan Meterai Elektronik, maka alamat surel/*email* `reinhart@reinhart1010.id` juga tercantum dalam informasi pembubuh meterai. Informasi lebih lanjut: <https://legal.reinhart1010.id/tanda-tangan-elektronik>.

> Dokumen PDF ini ditandatangani secara digital menggunakan Tanda Tangan Elektronik (TTE) Tersertifikasi sesuai standar dan ketentuan Penyelenggara Sertifikasi Elektronik (PSrE) oleh Kementerian Komunikasi dan Digital. Pastikan data pihak penandatangan yang ditampilkan adalah benar `REINHART PREVIANO KOENTJORO`, dan jika menggunakan Meterai Elektronik, maka alamat surel/*email* `reinhart@reinhart1010.id` juga tercantum dalam informasi pembubuh meterai. Informasi lebih lanjut: <https://legal.reinhart1010.id/tanda-tangan-elektronik>.

### For PDF-based documents (Bahasa Inggris)

> This PDF document is digitally signed using the OpenPGP File Signature, as well as PDF Electronic Signatures in accordance to applicable Indonesian standards and laws of Electronic Certification Providers (PSrE). Use the OpenPGP public key at <https://pgp.reinhart1010.id> (`reinhart@reinhart1010.id`, `EB75 3357`) to verify the authenticity of this document with the separate, detached OpenPGP signature file (`.sig`). Ensure that the e-signatures are signed on behalf of `REINHART PREVIANO KOENTJORO`. Shall the document be notarized with an Electronic Duty Stamp (*Meterai Elektronik* / *e-Meterai*), ensure that the email address `reinhart@reinhart1010.id` is also visible on the duty stamp's applicant information. More information: <https://legal.reinhart1010.id/electronic-signatures>.

> This PDF document is digitally signed using the PDF Electronic Signatures in accordance to applicable Indonesian standards and laws of Electronic Certification Providers (PSrE). Ensure that the e-signatures are signed on behalf of `REINHART PREVIANO KOENTJORO`. Shall the document be notarized with an Electronic Duty Stamp (Meterai Elektronik / e-Meterai), ensure that the email address `reinhart@reinhart1010.id` is also visible on the duty stamp's applicant information. More information: <https://legal.reinhart1010.id/electronic-signatures>.
