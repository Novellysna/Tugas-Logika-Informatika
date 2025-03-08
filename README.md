# Tugas-Logika-Informatika
# DATA DIRI
## NAMA : NOVELLYSNA NURZISKA
## KELAS : TI.24.A1
## NIM : 312410131
# input dan output Logika Informatika Pertemuan 2
## Input
```Python
def hitung_biaya_pengiriman(berat, jarak, jenis_pengiriman, is_member):
    """
    Fungsi untuk menghitung total biaya pengiriman berdasarkan beberapa faktor.

    Parameter:
    - berat (float): Berat paket dalam kilogram.
    - jarak (float): Jarak pengiriman dalam kilometer.
    - jenis_pengiriman (str): Jenis pengiriman, bisa "biasa" atau "express".
    - is_member (bool): Status keanggotaan pelanggan, True jika member, False jika non-member.

    Output:
    - int: Total biaya pengiriman setelah mempertimbangkan semua faktor.
    """

    # 1. Biaya dasar pengiriman
    total_biaya = 10000

    # 2. Tambahan biaya jika berat melebihi 5 kg
    if berat > 5:
        total_biaya += 5000  # Tambahan Rp 5.000

    # 3. Tambahan biaya jika jarak lebih dari 10 km
    if jarak > 10:
        total_biaya += 8000  # Tambahan Rp 8.000

    # 4. Tambahan biaya jika menggunakan layanan express
    if jenis_pengiriman.lower() == "express":  # Konversi ke huruf kecil untuk menghindari kesalahan input
        total_biaya += 20000  # Tambahan Rp 20.000

    # 5. Diskon 10% jika pelanggan adalah member
    if is_member:
        total_biaya *= 0.9 # Potongan 10%

    return int(total_biaya)  # Mengembalikan nilai dalam bentuk integer agar tidak ada desimal

# =====================================================
# Program Utama (Meminta Input dari Pengguna)
# =====================================================
if __name__ == "__main__":
    print("=== Program Perhitungan Biaya Pengiriman ===")

    # 1. Memasukkan berat paket
    while True:
        try:
            berat_paket = float(input("Masukkan berat paket (kg): "))
            if berat_paket < 0:
                print("Berat paket tidak bisa negatif. Silakan masukkan kembali.")
                continue
            break
        except ValueError:
            print("Input tidak valid! Masukkan angka.")

    # 2. Memasukkan jarak pengiriman
    while True:
        try:
            jarak_pengiriman = float(input("Masukkan jarak pengiriman (km): "))
            if jarak_pengiriman < 0:
                print("Jarak tidak bisa negatif. Silakan masukkan kembali.")
                continue
            break
        except ValueError:
            print("Input tidak valid! Masukkan angka.")

    # 3. Memasukkan jenis pengiriman (biasa/express)
    while True:
        jenis_pengiriman = input("Masukkan jenis pengiriman (biasa/express): ").strip().lower()
        if jenis_pengiriman not in ["biasa", "express"]:
            print("Jenis pengiriman hanya bisa 'biasa' atau 'express'. Silakan masukkan kembali.")
        else:
            break

    # 4. Memasukkan status keanggotaan pelanggan (member atau bukan)
    while True:
        is_member_input = input("Apakah pelanggan member? (ya/tidak): ").strip().lower()
        if is_member_input in ["ya", "tidak"]:
            is_member = is_member_input == "ya"
            break
        else:
            print("Harap masukkan 'ya' atau 'tidak'.")

    # 5. Menghitung biaya pengiriman
    biaya = hitung_biaya_pengiriman(berat_paket, jarak_pengiriman, jenis_pengiriman, is_member)

    # 6. Menampilkan hasil
    print("\n=== Rincian Biaya Pengiriman ===")
    print(f"Berat paket         : {berat_paket} kg")
    print(f"Jarak pengiriman    : {jarak_pengiriman} km")
    print(f"Jenis pengiriman    : {jenis_pengiriman.capitalize()}")
    print(f"Status Member       : {'Ya' if is_member else 'Tidak'}")
    print(f"Total Biaya Pengiriman: Rp {biaya:,.0f}")

print("="*64)
print("NAMA : NOVELLYSNA NURZISKA".center(64))
print(f'NIM : {312410002}'.center(64))
print("="*64)
```
## Output
```markdown
=== Program Perhitungan Biaya Pengiriman ===
Masukkan berat paket (kg): 20
Masukkan jarak pengiriman (km): 20
Masukkan jenis pengiriman (biasa/express): express
Apakah pelanggan member? (ya/tidak): ya

=== Rincian Biaya Pengiriman ===
Berat paket         : 20.0 kg
Jarak pengiriman    : 20.0 km
Jenis pengiriman    : Express
Status Member       : Ya
Total Biaya Pengiriman: Rp 38,700
================================================================
                 NAMA : NOVELLYSNA NURZISKA
                        NIM : 312410131
================================================================
PS C:\Users\Novellysna Nurziska\Documents\Tugas Logika Informatika novell> 
```
## Penjelasan 
Fungsi hitung_biaya_pengiriman(berat, jarak, jenis_pengiriman, is_member)
Fungsi ini menghitung total biaya pengiriman berdasarkan parameter yang diberikan.
Parameter:
berat (float): Berat paket dalam kilogram.
jarak (float): Jarak pengiriman dalam kilometer.
jenis_pengiriman (str): Jenis pengiriman ("biasa" atau "express").
is_member (bool): Status keanggotaan (True jika member, False jika bukan).
Biaya dasar pengiriman adalah Rp 10.000.
Jika berat paket > 5 kg, ada tambahan biaya Rp 5.000.
Jika jarak pengiriman > 10 km, ada tambahan biaya Rp 8.000.
Jika jenis pengiriman adalah "express" (case-insensitive), ada tambahan biaya Rp 20.000.
Jika pelanggan adalah member, ada diskon 10% dari total biaya.
Fungsi mengembalikan total biaya pengiriman dalam bentuk integer.
Program Utama (Bagian if __name__ == "__main__":)
Bagian ini adalah titik masuk program (main program) yang dijalankan ketika file Python dieksekusi.
Menampilkan judul program. Meminta input berat paket dari pengguna. Menggunakan while True loop dan try-except untuk memastikan input adalah angka positif.
Meminta input jarak pengiriman dari pengguna. Sama seperti input berat, memastikan input adalah angka positif. Meminta input jenis pengiriman ("biasa" atau "express").
Memastikan input adalah salah satu dari dua pilihan tersebut (case-insensitive).
Meminta input status keanggotaan ("ya" atau "tidak"). Mengubah input menjadi boolean (True jika "ya", False jika "tidak"). Memanggil fungsi hitung_biaya_pengiriman() dengan input yang diperoleh. Menampilkan rincian biaya pengiriman,
termasuk:
Berat paket
Jarak pengiriman
Jenis pengiriman (dengan huruf kapital di awal)
Status member ("Ya" atau "Tidak")
Total biaya pengiriman (diformat dengan pemisah ribuan)
Poin-poin Penting:
Validasi Input: Program melakukan validasi input untuk memastikan pengguna memasukkan data yang benar (angka positif untuk berat dan jarak, pilihan yang valid untuk jenis pengiriman dan status member).
Penanganan Error: Menggunakan try-except untuk menangani ValueError jika input bukan angka.
Case-Insensitive Input: Menggunakan .lower() untuk membuat input jenis pengiriman dan status member case-insensitive.
F-String: Menggunakan f-string untuk memformat output dengan lebih mudah.
Pemisah Ribuan: Menggunakan :, .0f untuk memformat biaya pengiriman dengan pemisah ribuan. Menampilkan hasil perhitungan
Rincian biaya ditampilkan dengan format rapi. Biaya diformat menggunakan {biaya:,.0f} untuk memisahkan ribuan dengan koma
Mencetak karakter "=" sebanyak 64 kali sebagai garis pembatas atas.
Mencetak teks "NAMA : NOVELLYSNA NURZISKA", lalu menggunakan .center(64) agar teks tersebut diratakan ke tengah dalam ruang sepanjang 64 karakter.
f'NIM : {312410131}' adalah f-string yang akan menghasilkan teks "NIM : 312410131".
Kemudian, .center(64) digunakan untuk meratakan teks tersebut ke tengah dalam 64 karakter. Mencetak kembali karakter "=" sebanyak 64 kali sebagai garis pembatas bawah.


## Cara Kerja Program
Program memulai dengan meminta input dari pengguna untuk berat paket, jarak pengiriman, jenis pengiriman, dan status keanggotaan.
Setiap input divalidasi untuk memastikan data yang dimasukkan sesuai dengan yang diharapkan (misalnya, angka positif untuk berat dan jarak, pilihan yang valid untuk jenis pengiriman dan status keanggotaan).
Setelah semua input valid diperoleh, program memanggil fungsi hitung_biaya_pengiriman() untuk menghitung total biaya pengiriman.
Program menampilkan rincian input dan total biaya pengiriman kepada pengguna.
