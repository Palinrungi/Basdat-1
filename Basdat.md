# Tugas Basis Data  :Membuat Database dengan DBMS XAMPP✨
### Created by Bintang Palinrungi ✔️

setelah start mysql pada xampp (pastikan tidak ada error)
1. buka command prompt
2. ketik    cd C:\xampp\mysql\bin  (lalu enter)
3. ketik    mysql -u root -p       (lalu enter)
4. kemudian nampak tulisan "Enter password" langsung saja klik enter
5. ketik    create database db_data_mhs;  (lalu enter)
6. ketik    show databases;      (lalu enter)

-------------------------------------------TABEL PRODI---------------------------------------------------

Buat tabel Prodi dengan kode :
   
   CREATE TABLE Prodi (
    Kode_prodi CHAR(6) PRIMARY KEY,
    Nama_prodi CHAR(30)
    );
    (lalu enter)

 ketik    show tables;  (lalu enter)
 
 ketik    desc prodi;   (lalu enter)

---------------------------------------------------------------------------------------------------------

---------------------------------------TABEL MAHASISWA---------------------------------------------------

 Buat Tabel mahasiswa dengan kode:
    
    CREATE TABLE Mahasiswa (
     NIM INT,
     Nama_mhs CHAR(50),
     Sex ENUM('L', 'P') DEFAULT 'L',
     Alamat VARCHAR(20) DEFAULT 'Pare-pare',
     Asal_SMA CHAR(30),
     NoHp VARCHAR(12),
     Login CHAR(20),
     Pass CHAR(20),
     Umur INT,
     Kode_prodi CHAR(6),
     FOREIGN KEY (Kode_prodi) REFERENCES Prodi(Kode_prodi)
     );
     (lalu enter)

 ketik    show tables;      (lalu enter)
 
 ketik    desc mahasiswa;   (lalu enter)

 --------------------------------------------------------------------------------------------------------

---------------------------------------TABEL MATA KULIAH-------------------------------------------------

 Buat tabel mata kuliah dengan kode :
 
     CREATE TABLE mata_kuliah (
     Mk_id CHAR(10) PRIMARY KEY,
     Nama_mk CHAR(10),
     Jumlah_jam INT,
     SKS INT
     );
    (lalu enter)

 ketik    show tables;         (lalu enter)
 
 ketik    desc mata_kuliah;    (lalu enter)

---------------------------------------------------------------------------------------------------------

-------------------------------------------TABEL RUANG---------------------------------------------------

Buat tabel ruang dengan kode :
    
    CREATE TABLE Ruang(
     Ruang_id CHAR(3) PRIMARY KEY,
     Nama_ruang CHAR(20),
     Kapasitas INT
     );
    (lalu enter)

 ketik    show tables;     (lalu enter)
 
 ketik    desc ruang;      (lalu enter)

---------------------------------------------------------------------------------------------------------

------------------------------------------TABEL DOSEN----------------------------------------------------

Buat tabel dosen dengan kode :

    CREATE TABLE dosen (
     NIP INT PRIMARY KEY,
     Inisial CHAR(3) UNIQUE KEY,
     Nama_dosen CHAR(50),
     Status ENUM('T','LB') DEFAULT 'T',
     Sex ENUM('L','P') DEFAULT 'L',
     Agama CHAR(20),
     Lgin CHAR(20),
     Pass CHAR(20),
     Alamat VARCHAR(50),
     Kota VARCHAR(20),
     Email VARCHAR(50),
     NoHp VARCHAR(12),
     Salary INT
     );
     (lalu enter)

 ketik    show tables;     (lalu enter)
 
 ketik    desc dosen;      (lalu enter)

---------------------------------------------------------------------------------------------------------

----------------------------------------TABEL MENGAJAR---------------------------------------------------

Buat tabel mengajar dengan kode :
    
    CREATE TABLE mengajar (
     Id_mengajar INT AUTO_INCREMENT PRIMARY KEY,
     Jam_ke INT,
     Hari VARCHAR(10),
     Mk_id CHAR(10),
     Inisial CHAR(3),
     Kode_prodi CHAR(6),
     Ruang_id CHAR(3),
     FOREIGN KEY (Mk_id) REFERENCES mata_kuliah(Mk_id),
     FOREIGN KEY (Inisial) REFERENCES dosen(Inisial),
     FOREIGN KEY (Ruang_id) REFERENCES ruang(Ruang_id)
     );
    (lalu enter) 

 ketik    show tables;        (lalu enter)
 
 ketik    desc mengajar;      (lalu enter)

---------------------------------------------------------------------------------------------------------

-------------------------------------------TABEL NILAI---------------------------------------------------

Buat tabel nilai dengan kode :

    CREATE TABLE nilai (
     NIM INT,
     Mk_id CHAR(10),
     Kode_prodi CHAR(6),
     Inisial CHAR(3),
     Nilai_uts INT,
     Nilai_uas INT,
     Nilai_akhir INT,
     FOREIGN KEY (NIM) REFERENCES mahasiswa(NIM),
     FOREIGN KEY (Mk_id) REFERENCES mata_kuliah(Mk_id),
     FOREIGN KEY (Kode_prodi) REFERENCES prodi (Kode_prodi),
     FOREIGN KEY (Inisial) REFERENCES dosen(Inisial)
     );
    (lalu enter)
 ketik    show tables;        (lalu enter)
 
 ketik    desc nilai;         (lalu enter)

---------------------------------------------------------------------------------------------------------

------------------------------------MENAMBAH KOLOM AGAMA-------------------------------------------------

Menambah kolom agama pada tabel mahasiswa :
   
    ALTER TABLE student ADD COLUMN Agama VARCHAR(10) AFTER Kode_prodi;  
    (lalu enter)

---------------------------------------------------------------------------------------------------------

----------------------------------MENAMBAH KOLOM RID-----------------------------------------------------

Menambah kolom Rid pada tabel ruang :

    ALTER TABLE ruang ADD COLUMN Rid  CHAR(10) FIRST;     
    (lalu enter)

--------------------------------------------------------------------------------------------------------    
-----------------------------------MENAMBAH KOLOM GRADE--------------------------------------------------

Menambah kolom Grade pada tabel nilai setelah kolom inisial :

     ALTER TABLE nilai ADD COLUMN Grade CHAR AFTER Inisial;  
     (lalu enter)

--------------------------------------------------------------------------------------------------------

-------------------------------MENGUBAH NAMA TABEL MAHASISWA---------------------------------------------

Mengubah nama tabel mahasiswa menjadi student :
    
     ALTER TABLE mahasiswa RENAME TO student;
     (lalu enter)

 -------------------------------------------------------------------------------------------------------

 -------------------------------JADIKAN NIM SEBAGAI PRIMARY KEY---------------------------------------   

 Jadikan NIM sebagai PRIMARY KEY pada tabel mahasiswa :

     ALTER TABLE student ADD PRIMARY KEY (NIM);
     (lalu enter)

---------------------------------------------------------------------------------------------------------
## Selamat Kerja Laporan 📑
