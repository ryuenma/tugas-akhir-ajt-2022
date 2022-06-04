# TUGAS AKHIR AJT AULIA NABIH RIZQULLAH TKOM-A 2021-2022

Berikut merupakan dokumentasi Tugas Akhir AJT

## A. Inisialisasi server untuk hosting Mininet

1. Login ke AWS Student Portal, kemudian klik Start Lab pada module Learner Lab. Tunggu hingga indikator Lab berubah menjadi hijau.

![image](https://user-images.githubusercontent.com/71396519/172003805-9fed9af6-7d90-4037-be68-13b73bcde99b.png)

2. Tekan tombol AWS disebelah indikator hijau untuk memasuki portal AWS untuk melakukan setup instance. Tekan EC2 untuk memasuki menu untuk membuat instance EC2.

![image](https://user-images.githubusercontent.com/71396519/172003919-4e2a4133-fbef-46ea-919e-17e07c465b9b.png)

3. Pada dasbor instance EC2, tekan tombol Launch Instance yang berwarna oren untuk membuat sebuah instance EC2.

![image](https://user-images.githubusercontent.com/71396519/172003960-17d0737f-e3ca-466f-ad74-5e4c4dcfd2b8.png)

4. Pada menu pembuatan instance EC2, buat sebuah instance dengan kriteria berikut:
		Name and tags: _Tugas Akhir_
		OS Images: _Ubuntu Server 22.04 LTS 64 bit_
		Instance type: _t2.medium_
		Key pair: _vockey_
		Edit Network settings: _allow SSH, allow HTTP, allow HTTPS, allow TCP port 8080, allow TCP port 8081_
		Configure storage: _30 GiB, gp3_
		
![image](https://user-images.githubusercontent.com/71396519/172004578-13fd92d2-86af-4a8e-9153-acd136829cec.png)
![image](https://user-images.githubusercontent.com/71396519/172004586-ba6870d4-d5eb-4465-be90-5237372d3dd4.png)
![image](https://user-images.githubusercontent.com/71396519/172004592-f4150291-be2e-4fa2-9c7d-f84e25be80c9.png)
![image](https://user-images.githubusercontent.com/71396519/172004597-105b4a18-acd7-46e0-8a26-f0da9472b540.png)
![image](https://user-images.githubusercontent.com/71396519/172004614-d8a087f3-babb-4f16-bc45-5bb86324ff9d.png)
![image](https://user-images.githubusercontent.com/71396519/172004629-9ed8e701-f8c2-45cb-9ed0-cc234a77ff5f.png)
![image](https://user-images.githubusercontent.com/71396519/172004631-6fd6427e-2b3f-490c-8aa3-85f57a507b22.png)
![image](https://user-images.githubusercontent.com/71396519/172004636-5b7cd7d5-baf7-4f92-a7cf-bee4ad865443.png)

 kemudian tekan _Launch Instance_ untuk menyalakan instance EC2 yang telah kita setup.
 
 ![image](https://user-images.githubusercontent.com/71396519/172004961-9b0f5593-9a55-4c29-bc56-b72127d479c4.png)

 
5. Kembali ke dasbor EC2, kemudian tekan refresh agar instance yang baru kita buat terlihat di instance list. Pastikan instance dalam kondisi _Running_ dan tunggu beberapa saat agar instance selesai melakukan booting.

![image](https://user-images.githubusercontent.com/71396519/172005385-15692362-396d-4efe-ac09-5b97567895da.png)

6. Tekan _instance-ID_, kemudian tekan Connect. pada window ini, tekan SSH client, kemudian lakukan copy command yang kita perlukan untuk login ke dalam instance menggunakan SSH.

![image](https://user-images.githubusercontent.com/71396519/172005581-d03bc88f-ae1f-418d-a066-991001333a74.png)
![image](https://user-images.githubusercontent.com/71396519/172005705-b5d3f013-990b-4f7a-b2c3-4962e7b96d1d.png)

7. Buka SSH client yang kita pakai (dalam praktikum ini saya menggunakan Windows PowerShell bawaan dari Windows 10), kemudian paste command yang telah kita copy ke dalam PowerShell. tekan Enter untuk menghubungkan klien dengan server.

![image](https://user-images.githubusercontent.com/71396519/172006017-b2e9f5ce-96df-48b8-a531-91332b1c8916.png)

8. Lakukan syntax berikut untuk memastikan kita sedang menggunakan OS image terbaru dan _up-to-date_

```
sudo apt-get update
sudo apt-get upgrade
```

![image](https://user-images.githubusercontent.com/71396519/172006208-e9dde5da-8ee4-4f87-a3c0-1c0a77bc07d4.png)
![image](https://user-images.githubusercontent.com/71396519/172006440-5f7fd851-14c9-4f8a-889a-269e96714388.png)

setelah upgrade selesai, lakukan sebuah server reboot. Setup instance EC2 selesai
