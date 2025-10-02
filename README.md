erDiagram
    ANGGOTA {
        string nomor_anggota PK
        string nama_anggota
        string alamat
        string telepon
        string nomor_ktp_sim
    }
    PEMINJAMAN {
        string kode_peminjaman PK
        date tanggal_pinjam
        date tanggal_kembali
        int denda
    }
    COPY_BUKU {
        string kode_copy PK
    }
    BUKU {
        string kode_buku PK
        string judul_buku
        string penerbit
    }
    CABANG {
        string kode_cabang PK
        string nama_cabang
        string alamat_cabang
    }
    PENGARANG {
        string kode_pengarang PK
        string nama_pengarang
    }
    PENULISAN {
        string kode_buku PK, FK
        string kode_pengarang PK, FK
    }
    ANGGOTA ||--o{ PEMINJAMAN : melakukan
    PEMINJAMAN }o--|| COPY_BUKU : melibatkan
    BUKU ||--|{ COPY_BUKU : memiliki
    CABANG ||--o{ COPY_BUKU : menyimpan
    BUKU ||--|{ PENULISAN : ditulis_oleh
    PENGARANG ||--o{ PENULISAN : menulis
