# Tugas UAS Bahasa Pemrograman
         nama : Patur rahman hakim
         nim  : 312410271
         Kelas : TI.24.A2
# codingan
     class Data:
            def _init_(self):
            self.stock_barang = 0 
            self.uang = 0  
            self.pemasukan_barang = 0
            self.pengeluaran_barang = 0
            self.pemasukan_uang = 0
            self.pengeluaran_uang = 0

            def tambah_stock(self, jumlah):
            """Menambah stock barang di perusahaan"""
            self.stock_barang += jumlah
            self.pemasukan_barang += jumlah

            def kurangi_stock(self, jumlah):
            """Mengurangi stock barang di perusahaan"""
            if self.stock_barang >= jumlah:
            self.stock_barang -= jumlah
            self.pengeluaran_barang += jumlah
           else:
                print("Stok barang tidak cukup")

       def tambah_uang(self, jumlah):
            """Menambah uang ke saldo perusahaan"""
            self.uang += jumlah
            self.pemasukan_uang += jumlah

       def kurangi_uang(self, jumlah):
           """Mengurangi uang dari saldo perusahaan"""
           if self.uang >= jumlah:
               self.uang -= jumlah
               self.pengeluaran_uang += jumlah
           else:
               print("Saldo uang tidak cukup")

     class View:
          @staticmethod
          def tampilkan_data(data):
              """Menampilkan data terkini"""
              print(f"Stock Barang: {data.stock_barang}")
              print(f"Saldo Uang: {data.uang}")
              print(f"Pemasukan Barang: {data.pemasukan_barang}")
              print(f"Pengeluaran Barang: {data.pengeluaran_barang}")
              print(f"Pemasukan Uang: {data.pemasukan_uang}")
              print(f"Pengeluaran Uang: {data.pengeluaran_uang}")
              print("="*40)

    class Process:
           def _init_(self):
             self.data = Data()
             self.view = View()

          def main_menu(self):
            """Menu utama interaksi pengguna"""
            while True:
                print("===== MENU UTAMA =====")
                print("1. Tambah Stock Barang")
                print("2. Kurangi Stock Barang")
                print("3. Tambah Uang")
                print("4. Kurangi Uang")
                print("5. Tampilkan Data")
                print("6. Keluar")
                choice = input("Pilih opsi (1-6): ")

               if choice == '1':
                   jumlah = int(input("Masukkan jumlah barang yang akan ditambahkan: "))
                   self.data.tambah_stock(jumlah)
               elif choice == '2':
                   jumlah = int(input("Masukkan jumlah barang yang akan dikurangi: "))
                   self.data.kurangi_stock(jumlah)
               elif choice == '3':
                   jumlah = int(input("Masukkan jumlah uang yang akan ditambahkan: "))
                   self.data.tambah_uang(jumlah)
               elif choice == '4':
                   jumlah = int(input("Masukkan jumlah uang yang akan dikurangi: "))
                   self.data.kurangi_uang(jumlah)
               elif choice == '5':
                   self.view.tampilkan_data(self.data)
               elif choice == '6':
                   print("Terima kasih telah menggunakan aplikasi!")
                   break
               else:
                    print("Pilihan tidak valid! Silakan coba lagi.")

   if _name_ == "_main_":
       process = Process()
       process.main_menu()
# Penjelasan
  1.class Data
  Kelas ini bertanggung jawab untuk menyimpan dan mengelola data utama, seperti stok 
  barang dan saldo uang.

  Atribut dalam class data
  stock_barang: Menyimpan jumlah stok barang saat ini.
  uang: Menyimpan saldo uang saat ini.
  pemasukan_barang: Mencatat total barang yang masuk.
  pengeluaran_barang: Mencatat total barang yang keluar.
  pemasukan_uang: Mencatat total uang yang masuk.
  pengeluaran_uang: Mencatat total uang yang keluar.

  Fungsi dalam class data
  tambah_stock(self, jumlah)
  Menambah stok barang berdasarkan input jumlah.
  Nilai jumlah ditambahkan ke stock_barang dan pemasukan_barang.
  kurangi_stock(self, jumlah)
  Mengurangi stok barang.
  Jika stock_barang mencukupi, maka stock_barang dikurangi sebesar jumlah, dan nilai 
  jumlah ditambahkan ke pengeluaran_barang.
  Jika stok tidak mencukupi, akan menampilkan pesan "Stok barang tidak cukup".
  tambah_uang(self, jumlah)
  Menambah saldo uang.
  Nilai jumlah ditambahkan ke uang dan pemasukan_uang.
  kurangi_uang(self, jumlah)
  Mengurangi saldo uang.
  Jika saldo uang mencukupi, maka uang dikurangi sebesar jumlah, dan nilai jumlah 
  ditambahkan ke pengeluaran_uang.
  Jika saldo tidak mencukupi, akan menampilkan pesan "Saldo uang tidak cukup".

  2. class View
  Kelas ini bertugas untuk menampilkan data kepada pengguna.
  Fungsi dalam kelas
  tampilkan_data(data)
  Menampilkan informasi data terkini, seperti jumlah stok barang, saldo uang, 
  pemasukan, dan pengeluaran.
  Digunakan untuk memvisualisasikan data dari objek Data.

  3.class Process
  Kelas ini bertindak sebagai pengelola proses interaksi antara pengguna dengan 
  program.
  Atribut dalam class process
  data: Objek dari kelas Data yang digunakan untuk mengelola data.
  view: Objek dari kelas View yang digunakan untuk menampilkan data.

  Fungsi dalam class process
  main_menu(self)
  Fungsi ini menyediakan antarmuka menu utama yang memungkinkan pengguna untuk 
  melakukan beberapa tindakan:
  Tambah Stock Barang: Memanggil fungsi tambah_stock dari objek data.
  Kurangi Stock Barang: Memanggil fungsi kurangi_stock dari objek data.
  Tambah Uang: Memanggil fungsi tambah_uang dari objek data.
  Kurangi Uang: Memanggil fungsi kurangi_uang dari objek data.
  Tampilkan Data: Memanggil fungsi tampilkan_data dari objek view.
  Keluar: Menghentikan program.

  4. Fungsi Utama
  Bagian terakhir dari kode adalah fungsi untuk menjalankan program:

  if __name__ == "__main__":
      process = Process()
      process.main_menu()
  if __name__ == "__main__":

  Mengecek apakah file ini dijalankan secara langsung atau diimpor sebagai modul. Jika 
  dijalankan langsung, maka program akan memulai proses.
  process = Process()

  Membuat objek dari kelas Process.
  process.main_menu()

  Menjalankan fungsi main_menu untuk memulai interaksi dengan pengguna.
