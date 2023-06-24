# Sub_Query
sub query

# 1. Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika
My Sql> SELECT k.nik, k.id_dept, k.nama
        FROM k
        WHERE id_dept = (SELECT id_dept, FROM k, WHERE nama ='Dika');
![Gambar 1](https://github.com/dhomuhammad/Sub_Query/blob/main/Output/ss1.png)

# 2. Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua karyawan. Urutkan menurun berdasarkan besaran gaji
My Sql> SELECT AVG (gaji_pokok) AS RerataGaji FROM k;
        SELECT nik, nama, gaji_pokok AS "Rerata Gaji"
        FROM k, WHERE gaji_pokok > (SELECT AVG(gaji_pokok)
        FROM k, ORDER BY gaji_pokok);
![Gambar 2](https://github.com/dhomuhammad/Sub_Query/blob/main/Output/ss2.png)

# 3. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K'
My Sql> SELECT nik, nama, FROM k
        WHERE nama IN (SELECT nama, FROM k, WHERE nama LIKE'__k%');
![Gambar 3](https://github.com/dhomuhammad/Sub_Query/blob/main/Output/ss3.png)

# 4. Tampilkan data karyawan yang bekerja pada departemen yang ada di kantor pusat
My Sql> SELECT nik, nama 
        FROM k, WHERE id_dept = (SELECT id_dept, FROM dept, WHERE id_p =
        (SELECT id_p FROM p WHERE nama='Kantor Pusat'));
![Gambar 4](https://github.com/dhomuhammad/Sub_Query/blob/main/Output/ss4.png)

# 5. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung      huruf 'K' dan yang gajinya lebih besar dari rata-rata gaji semua karyawan
My Sql> SELECT nik, nama, gaji_pokok
        FROM k, WHERE gaji_pokok > (SELECT AVG (gaji_pokok)FROM k)
        AND nama IN (SELECT nama, FROM k, WHERE nama LIKE'__k%');
![Gambar 5](https://github.com/dhomuhammad/Sub_Query/blob/main/Output/ss5.png)



