# source-code
# Program Python untuk membuat faktur penjualan barang atau jasa

def buat_faktur():
    daftar_barang = [("Laptop", 2, 5000000)]  # Data barang sudah ditentukan
    
    subtotal = sum(jumlah * harga for _, jumlah, harga in daftar_barang)
    pajak = subtotal * 0.10  # Pajak 10%
    total = subtotal + pajak
    
    print("\n===== FAKTUR PENJUALAN =====")
    print("Nama Barang/Jasa\tJumlah\tHarga Satuan\tTotal")
    for nama, jumlah, harga in daftar_barang:
        print(f"{nama}\t{jumlah}\t{harga}\t{jumlah * harga}")
    print("----------------------------------")
    print(f"Subtotal: {subtotal:.2f}")
    print(f"Pajak 10%: {pajak:.2f}")
    print(f"Total Harga: {total:.2f}")
    
    with open("faktur_penjualan.txt", "w") as file:
        file.write("===== FAKTUR PENJUALAN =====\n")
        file.write("Nama Barang/Jasa\tJumlah\tHarga Satuan\tTotal\n")
        for nama, jumlah, harga in daftar_barang:
            file.write(f"{nama}\t{jumlah}\t{harga}\t{jumlah * harga}\n")
        file.write("----------------------------------\n")
        file.write(f"Subtotal: {subtotal:.2f}\n")
        file.write(f"Pajak 10%: {pajak:.2f}\n")
        file.write(f"Total Harga: {total:.2f}\n")
    
    print("Faktur telah disimpan sebagai 'faktur_penjualan.txt'")

# Jalankan fungsi
if __name__ == "__main__":
    buat_faktur()
