# UAS

    class Buku:
    def _init_(self, judul, pengarang, tahun):
        self.judul = judul
        self.pengarang = pengarang
        self.tahun = tahun
    
    def _str_(self):
        return f"Judul: {self.judul}, Pengarang: {self.pengarang}, Tahun: {self.tahun}"

    class KoleksiBuku:
    def _init_(self):
        self.buku = []
    
    def tambah_buku(self, buku):
        self.buku.append(buku)
        print(f"Buku '{buku.judul}' telah ditambahkan.")
    
    def daftar_buku(self):
        if not self.buku:
            print("Tidak ada buku.")
        else:
            print("Daftar Buku:")
            for buku in self.buku:
                print(buku)
    
    def hapus_buku(self, judul):
        for buku in self.buku:
            if buku.judul == judul:
                self.buku.remove(buku)
                print(f"Buku '{judul}' telah dihapus.")
                return
        print(f"Tidak ada buku dengan judul '{judul}'.")

    def main():
    # Membuat koleksi buku
    koleksi = KoleksiBuku()

    # Menambahkan buku
    while True:
        print("\nMenu:")
        print("1. Tambah Buku")
        print("2. Daftar Buku")
        print("3. Hapus Buku")
        print("4. Keluar")

        pilihan = input("Pilih opsi: ")

        if pilihan == '1':
            judul = input("Masukkan judul buku: ")
            pengarang = input("Masukkan pengarang buku: ")
            tahun = input("Masukkan tahun terbit buku: ")

            # Membuat objek buku dengan data yang dimasukkan pengguna
            buku = Buku(judul, pengarang, tahun)
            koleksi.tambah_buku(buku)
        
        elif pilihan == '2':
            koleksi.daftar_buku()
        
        elif pilihan == '3':
            judul = input("Masukkan judul buku yang ingin dihapus: ")
            koleksi.hapus_buku(judul)
        
        elif pilihan == '4':
            print("Keluar dari program...")
            break
        
        else:
            print("Opsi tidak valid, silakan coba lagi.")

    if __name__ == "__main__":
    main()

  Penjelasan
    1. Kelas Buku
    Kelas ini digunakan untuk merepresentasikan sebuah buku dengan atribut judul, pengarang, dan tahun.
    - __init__: Merupakan konstruktor yang digunakan untuk menginisialisasi objek Buku. Ketika sebuah objek Buku dibuat, kita perlu memberikan nilai untuk judul, pengarang, dan tahun        agar objek tersebut dapat diisi datanya.
    - __str__: Ini adalah metode spesial yang digunakan untuk mendefinisikan bagaimana representasi string dari objek Buku. Ketika objek Buku dicetak, metode ini akan dipanggil dan          mengembalikan string yang mencakup informasi tentang judul, pengarang, dan tahun.
    2. Kelas KoleksiBuku
    Kelas ini bertanggung jawab untuk mengelola koleksi buku, seperti menambah, menampilkan, dan menghapus buku dari koleksi.
    - __init__: Konstruktor untuk menginisialisasi objek KoleksiBuku. Di sini, kita membuat sebuah list kosong buku yang akan digunakan untuk menyimpan objek-objek Buku.
    - tambah_buku: Metode ini digunakan untuk menambahkan buku ke dalam koleksi. Ketika sebuah objek Buku ditambahkan, ia akan dimasukkan ke dalam list self.buku dan mencetak pesan bahwa     buku telah ditambahkan.
    - daftar_buku: Metode ini akan mencetak daftar buku yang ada dalam koleksi. Jika koleksi buku kosong, ia akan mencetak pesan "Tidak ada buku".
    - hapus_buku: Metode ini memungkinkan pengguna untuk menghapus buku berdasarkan judul yang diberikan. Jika buku ditemukan, maka buku tersebut akan dihapus dari koleksi. Jika tidak        ditemukan, akan muncul pesan kesalahan. 
    3. Fungsi main
    - Fungsi main adalah tempat utama eksekusi program. Di sini, pengguna dapat memilih opsi untuk menambah buku, melihat daftar buku, menghapus buku, atau keluar dari program.
    - Program ini berjalan dalam loop yang terus berlanjut sampai pengguna memilih opsi untuk keluar.
    - Setiap kali pengguna memilih untuk menambah buku, program meminta input untuk judul, pengarang, dan tahun, kemudian objek Buku akan dibuat dan ditambahkan ke dalam koleksi                menggunakan metode tambah_buku.
    - Program juga menyediakan opsi untuk melihat daftar buku yang ada dengan memanggil metode daftar_buku.
    - Jika pengguna memilih untuk menghapus buku, mereka diminta untuk memasukkan judul buku yang akan dihapus, dan metode hapus_buku akan dipanggil untuk menghapusnya.
    https://youtu.be/x75mBhlypec?si=1fPkANrpefvC_wMr 
