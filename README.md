# Minggu-6
Tugas Praktikum dan latihan

Type in CLI Mysql
# Data Definition Language

```sql
create database pendaftaran;

create table data_diri (
no int(3), nama varchar(35), alamat varchar(60),
email varchar(40), no_telepon varchar(15), sex char(1));

desc data_diri;
drop table data_diri;

create table pribadi (
kd_pribadi CHAR(3) primary key,
panggilan char(4), nama varchar(35), email varchar(50),
sex char(1), UNIQUE (kd_pribadi,panggilan));

rename table pribadi to data_pribadi;
alter table data_pribadi add gol_darah char(1);
desc data_pribadi;
alter table data_pribadi drop gol_darah;
```
# Data Manipulation Language
```sql
insert into tb_tamu values('1','Boi trimoyo','ujung 
berung','bo_i77@yahoo.com','085613548789');

update tb_tamu set nama='irfan nurhudin' where nama="Boi 
trimoyo";
select * from tb_tamu;

insert into tb_tamu 
values('2','Wasmui','Jatimulyo','boy@gmail.com','084567897890');

insert into tb_tamu 
values('3','Sumarno','Surodadi','man@ymail.com','082469823578');

insert into tb_tamu 
values('4','Sukamto','Kradenan','doi@gmail.com','083648763845');

delete from tb_tamu where no='4';
select no, nama, alamat from tb_tamu;
select * from tb_tamu where alamat ='Kradenan';
select * from tb_tamu where nama like '%su%';
select * from tb_tamu order by nama;

```

# Data Control Language
```sql
CREATE DATABASE universitas;
USE universitas;
CREATE TABLE mahasiswa_rmik ( nim CHAR(9), nama CHAR(50), umur 
INT, tempat_lahir CHAR(50), IPK DECIMAL (3,2) );
INSERT INTO mahasiswa_rmik VALUES ('089045001', 'Andi Suryo', 23, 
'Jakarta', 2.7);
CREATE TABLE mahasiswa_ekonomi ( nim CHAR(9), nama CHAR(50), umur 
INT, tempat_lahir CHAR(50), IPK DECIMAL (3,2) );
INSERT INTO mahasiswa_ekonomi VALUES ('089023013', 'Alex 
Supriyanto', 23, 'Surabaya', 2.9);
CREATE USER 'udinus' IDENTIFIED BY '123';
flush privileges;

\q

mysql -u udinus -p

show databases;

\q

grant all privileges on universitas.* to udinus@localhost;
flush privileges;

\q

mysql -u udinus -p
show databases;
```
