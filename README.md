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
