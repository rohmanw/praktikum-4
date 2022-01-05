

**modul praktikum 4**

```markdown
https://github.com/aldonesia/Sistem-Administrasi-Server-2021/blob/master/modul-4/silabus.md
```

**soal praktikum 4**

```markdown
1.	Terapkan loadbalancer untuk /blog dan /app dengan ketentuan
	i./blog menggunakan least_conn
	ii./app menggunakan ip hash
	iii.disarakan menggunakan ansible untuk instalasi
2.	Gunakan apache Jmeter untuk menganalisa perbedaan antara /, /app, /blog dengan loadbalancer dan tanpa loadbalancer pada traffic 50, 100 dan 150 users. Analisa dari segi waktu saja. Tulis langkah testing dan analisa dengan bahasa sendiri.
```

**laporan**

```markdown
1.	Stop dulu debian_php5.6 dan ubuntu_php7.4, lalu clone
```

![1](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\1.png)

```markdown
2.	Start semua termasuk clone debian_php5.6 dan ubuntu_php7.4
```

![2](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\2.png)

```markdown
3.	Masuk ke ubuntu_landing_2
	nano /etc/hosts
```

![3](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\3.png)

```markdown
4.	nano /etc/nginx/sites-available/lxc_landing.dev
```

![4](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\4.png)

```markdown
5.	Check konfigurasi
```

```markdown
	nginx -t
	service nginx restart
	curl -i http://lxc_landing_2.dev
```

![5](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\5.png)

```markdown
exit
```

```markdown
6.	Pastikan semua lxc kondisi running
	lxc-ls-f
```

![6](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\6.png)

```markdown
7.	- Rename test plan menjadi Landing Load test
	- Tambahkan User Defined VariablesPermalink (klik kanan node Test Plan (Landing Load Test) -> Add -> Config Element -> User Defined Variables)
	- Tambahkan host dan port
	- Menambahkan Thread Group 
	- Menambahkan HTTP Request Defaults
		Dengan cara klik kanan Landing Load Test-> add -> config element -> HTTP Request Default
	- Menambahkan HTTP Request untuk users access (Threads Group)
		Dengan cara klik kanan di user access-> add -> Sampler -> HTTP Request (lakukan 3 kali untuk landing, blog, dan app)
	- Menambahkan Graph Result
		Dengan cara klik kanan Landing Load Test -> Add > Listener > Graph Result
	- Menambahkan View Result in Table
		Dengan cara klik kanan Landing Load Test -> Add > Listener > View Result in Table
	- Menambahkan Summary Report
		Dengan cara klik kanan Landing Load Test -> Add > Listener > Summary Report
```

```markdown
lalu Run Testing Menjalankan Test secara otomatis. Caranya :
-	Simpan terlebih dahulu Test Plan yang telah kita buat di File > Save ( Ctrl + S ).
-	Klik Run atau Ctrl + R, jMeter akan mulai mensimulasi sejumlah user dalam mengakses web server yang telah ditentukan.
```

```markdown
Hasil Graph Result traffic 50 users Tanpa loadbalancer
```

![7](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\7.png)

```markdown
8.	Lihat Hasil View Result in Table 50 users Tanpa loadbalancer
```

![8](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\8.png)

```markdown
9. Hasil Summary Report 50 users Tanpa loadbalancer
```

![9](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\9.png)

```markdown
10.	Hasil Graph Result traffic 100 users Tanpa loadbalancer
```

![10](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\10.png)

```markdown
11.	Lihat Hasil View Result in Table 100 users Tanpa loadbalancer
```

![11](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\11.png)

```markdown
12.	Hasil Summary Report 100 users Tanpa loadbalancer
```

![12](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\12.png)

```markdown
13.	Konfigurasi Load balancer
	sudo nano /etc/nginx/sites-available/vm.local
```

![13](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\13.png)

```markdown
Setelah selesai.
Check konfigurasi
	sudo nginx -t
```

Menggunakan loadbalancer dapat mengoptimalkan pemanfaatan sumber daya, memaksimalkan throughput, mengurangi latensi, dan memastikan konfigurasi yang toleran terhadap kesalahan.

```markdown
14.	Hasil Graph Result traffic 50 users Dengan loadbalancer
```

![14](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\14.png)

```markdown
15.	Lihat Hasil View Result in Table 50 users Dengan loadbalancer
```

![15](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\15.png)

```markdown
16.	Hasil Summary Report 50 users Dengan loadbalancer
```

![16](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\16.png)

```markdown
17.	Hasil Graph Result traffic 100 users Dengan loadbalancer
```

![17](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\17.png)

```markdown
18.	Lihat Hasil View Result in Table 100 users Dengan loadbalancer
```

![18](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\18.png)

```markdown
19.	Hasil Summary Report 100 users Dengan loadbalancer
```

![19](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\19.png)

```markdown
20.	Hasil Graph Result traffic 150 users Dengan loadbalancer
```

![20](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\20.png)

```markdown
21.	Lihat Hasil View Result in Table 150 users Dengan loadbalancer
```

![21](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\21.png)

```markdown
22.	Hasil Summary Report 150 users Dengan loadbalancer
```

![22](D:\IT Telkom Surabaya\Semester V\Sistem Administrasi\New folder\prak4\untitled folder\22.png)
