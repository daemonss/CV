flowchart TD

    %% === LOGIN FLOW ===
    A([Start Program]) --> B{Sudah Punya Akun?}
    B -- Ya --> C[/Login Akun/]
    B -- Tidak --> D[/Registrasi Akun/] --> C
    C --> E{Login Berhasil?}
    E -- Tidak --> C
    E -- Ya --> F[/Pilih Provinsi/]
    F --> G[/Pilih Kota/]
    G --> H[/Pilih Bioskop/]

    %% === MENU UTAMA ===
    H --> I{Pilih Menu}
    I -- Pembelian Tiket --> J[/Pembelian Tiket/]
    I -- Event Gratis --> K[/Event Gratis/]
    I -- Pendataan Penghasilan --> L[/Pendataan Penghasilan/]
    I -- Keluar Aplikasi --> M([Keluar Aplikasi])

    %% === PEMBELIAN TIKET ===
    J --> J1[/Pilih Film/]
    J1 --> J2[/Pilih Jadwal/]
    J2 --> J3[/Pilih Kursi/]
    J3 --> J4[/Pilih Jumlah Tiket/]
    J4 --> J5{Konfirmasi?}
    J5 -- Tidak --> J3
    J5 -- Ya --> J6[Proses: Tiket Disimpan]
    J6 --> J7[Proses: Update Penghasilan]
    J7 --> J8[Proses: Update Tree Pendapatan]
    J8 --> I

    %% === EVENT GRATIS ===
    K --> K1{Daftar Event?}
    K1 -- Tidak --> I
    K1 -- Ya --> K2[/Daftar Tiket 1 User/]
    K2 --> K3[Proses: Masuk Antrian]
    K3 --> K4[Proses: Proses per 2 Sesi]
    K4 --> K5{User Prioritas?}
    K5 -- Ya --> K6[Berikan Tiket Gratis]
    K5 -- Tidak --> K7[Cek Tiket Tersedia]
    K6 --> K8([Selesai])
    K7 --> K8
    K8 --> I

    %% === PENDATAAN PENGHASILAN ===
    L --> L1[Admin Lihat Penghasilan]
    L1 --> L2[/Tampilan Bioskop dan Wilayah/]
    L2 --> I

    %% === KELUAR ===
    M --> Z([Program Selesai])
