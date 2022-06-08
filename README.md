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

## B. Menginstal Mininet dan RYU

1. Pastikan kita sudah terkoneksi dengan server melalui SSH

![image](https://user-images.githubusercontent.com/71396519/172016124-d7ac9b69-6abb-4c67-a912-a00851af159c.png)

2. Unduh file repositori mininet dari `https://mininet.org/download` dengan menggunakan command berikut,

```
git clone https://github.com/mininet/mininet
```

![image](https://user-images.githubusercontent.com/71396519/172016608-3a58754e-4d48-433b-afa3-80e2bad6c1f0.png)

kemudian install dengan menggunakan command berikut,
```
mininet/util/install.sh -nfv
```

![image](https://user-images.githubusercontent.com/71396519/172016706-ac46c5b7-117c-4586-92f2-f67b1346b4e4.png)

3. Unduh file repositori RYU dan install

```
git clone https://github.com/osrg/ryu.git
cd ryu; pip install .
cd
```

![image](https://user-images.githubusercontent.com/71396519/172016749-57170cd1-3b62-44a7-abee-696edc48f633.png)

![image](https://user-images.githubusercontent.com/71396519/172016768-6d05acb5-7679-489e-99aa-8dfb14f39cc1.png)

4. Unduh file repositori Flowmanager

```
git clone https://github.com/martimy/flowmanager
cd
```

![image](https://user-images.githubusercontent.com/71396519/172016852-ca089feb-8d9a-4204-8941-ee3ac072dd71.png)

5. Setelah melakukan instalasi MiniNet dan RYU, lakukan sebuah reboot server menggunakan command `sudo reboot`

6. Setelah melakukan reboot, maka kita bisa mulai tes satu-per-satu aplikasi yang telah kita instal, dimulai dari MiniNet. Untuk membuka MiniNet, kita menggunakan command `sudo mn` pada SSH.

![image](https://user-images.githubusercontent.com/71396519/172017407-463276f1-9c32-441d-9108-9078c3856843.png)

MiniNet akan secara default membuat sebuah jaringan yang terdiri dari 2 host, 1 switch, dan 1 OpenFlow Reference Controller.

7. Untuk menampilkan apa saja yang bisa kita lakukan dengan mininet, kita bisa menggunakan perintah `help`

![image](https://user-images.githubusercontent.com/71396519/172017497-6b535f86-270e-4972-b403-a4244644f79a.png)

8. untuk menampilkan node yang ada, kita bisa menggunakan perintah `node`

![image](https://user-images.githubusercontent.com/71396519/172017579-e6e359c2-5a55-4b29-b807-d893fbd0212a.png)

9. untuk menampilkan link antar node, kita bisa menggunakan perintah `net`

![image](https://user-images.githubusercontent.com/71396519/172017591-6af117cd-f56f-47af-afa7-3fb91a64e47a.png)

10. untuk menampilkan informasi dari semua node, kita bisa menggunakan perintah `dump`

![image](https://user-images.githubusercontent.com/71396519/172017604-71493cc3-080f-4e0d-8f73-9dd44e7127be.png)

11. Kemudian, kita akan mengetes konektivitas antar node pada jaringan default tersebut dengan menggunakan perintah `pingall` dan `h1 ping -c 2 h2`

![image](https://user-images.githubusercontent.com/71396519/172017640-85c78467-449d-49be-88be-45a7982557eb.png)

![image](https://user-images.githubusercontent.com/71396519/172017650-32464e28-c9a7-474c-a102-468f6750ebfd.png)

## C. Membuat Custom Topology

1. Buat file script bernama tugas22sw2h.py menggunakan command `vim tugas22sw2.py` pada SSH

![image](https://user-images.githubusercontent.com/71396519/172587479-9f4c4ad8-1fcc-4191-9a81-4172b13ec671.png)

2. isi dengan script berikut,

```#!/usr/bin/env python

" Custom Topology "

from mininet.topo import Topo
from mininet.log import setLogLevel, info

class MyTopo( Topo ):

    def addSwitch(self, name, **opts ):
        kwargs = {'protocols' : 'OpenFlow13'}
        kwargs.update( opts )
        return super(MyTopo, self).addSwitch( name, **kwargs )
        
    def __init__(self):
        # Inisialisasi Topology
        Topo.__init__( self )
        
        # Tambahkan node, switch, dan host
        info('*** Add switches\n')
        s1 = self.addSwitch('s1')
        s2 = self.addSwitch('s2')
        # ....
        info('*** Add hosts\n')
        h1 = self.addHost('h1', ip='10.1.0.1/24')
        h2 = self.addHost('h2', ip='10.1.0.2/24')
        # ....
        self.addLink(s1, h1, port1=1, port2=1)
        self.addLink(s1, s2, port1=2, port2=1)
        self.addLink(s2, h2, port1=2, port2=1)
        # ....
    topos = {'mytopo': ( lambda: MyTopo() ) }
 ```
    
![image](https://user-images.githubusercontent.com/71396519/172599818-a9ffbf3a-6636-4a66-bad3-61decae32457.png)

3. Ketika sudah selesai membuat script, maka kita akan menjalankan command berikut `sudo mn --controller=none --custom tugas22sw2h.py --topo mytopo --mac --arp`

![image](https://user-images.githubusercontent.com/71396519/172602189-fe5228b9-f64c-48e2-830e-7443849f968a.png)

4. Setelah MiniNet berjalan, jalankan command berikut,

```sh ovs-ofctl add-flow s1 -O OpenFlow13 "in_port=1,action=output:2"
sh ovs-ofctl add-flow s1 -O OpenFlow13 "in_port=2,action=output:1"
sh ovs-ofctl add-flow s2 -O OpenFlow13 "in_port=1,action=output:2"
sh ovs-ofctl add-flow s2 -O OpenFlow13 "in_port=2,action=output:1"
```

![image](https://user-images.githubusercontent.com/71396519/172604317-f2dea9fb-36b1-4b62-9c44-2558188ade88.png)

5. Lakukan uji koneksi dengan menggunakan command `h1 ping -c2 h2`

![image](https://user-images.githubusercontent.com/71396519/172604492-b41a6f11-1608-4ee3-beae-f65270a97b93.png)

6. Topology 2 Switch 2 Host selesai. Maka kita kaan berlanjut ke topologi selanjutnya, yakni 3 switch dengan 6 host menggunakan STP, berikut scriptnya;

```from mininet.topo import Topo

class MyTopo( Topo ):
    "Simple topology example."

    def build( self ):
        "Create custom topo."

        # Add hosts and switches
        H1 = self.addHost( 'h1', ip = '10.1.0.1/24' )
        H2 = self.addHost( 'h2', ip = '10.1.0.2/24' )
        H3 = self.addHost( 'h3', ip = '10.1.0.3/24' )
        H4 = self.addHost( 'h4', ip = '10.1.0.4/24' )
        H5 = self.addHost( 'h5', ip = '10.1.0.5/24' )
        H6 = self.addHost( 'h6', ip = '10.1.0.6/24' )
        S1 = self.addSwitch( 's1' )
        S2 = self.addSwitch( 's2' )
        S3 = self.addSwitch( 's3' )

        # Add links
        self.addLink(S1, S2, port1=4, port2=2)
        self.addLink(S1, S3, port1=1, port2=3) 
        self.addLink(S2, S3, port1=1, port2=4)
        self.addLink(H1, S1, port1=1, port2=2)
        self.addLink(H2, S1, port1=1, port2=3)
        self.addLink(H3, S2, port1=1, port2=3)
        self.addLink(H4, S2, port1=1, port2=4)
        self.addLink(H5, S3, port1=1, port2=2)

topos = { 'mytopo': ( lambda: MyTopo() ) }
```

![image](https://user-images.githubusercontent.com/71396519/172606779-db81d839-59d3-40e1-a5cd-8f05428f9ff5.png)

7. Save scriptnya, kemudian jalankan command `sudo mn --controller=none --custom tugas23sw6h.py --topo mytopo --mac --arp`

![image](https://user-images.githubusercontent.com/71396519/172608285-5b5f3f30-6472-4fd0-8106-076aa75f232a.png)

8. lakukan test pingall

![image](https://user-images.githubusercontent.com/71396519/172613217-dc4c9796-2df8-44bb-a01d-238c3b0fd585.png)

## D. Membuat aplikasi Ryu Load Balancer

## E. Membuat aplikasi Ryu Shortest Path Routing
