<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ahmad Fathullah - Profile</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    
    <style>
        /* Import font dari Google Fonts (opsional, ganti jika ingin font lain) */
        @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600;700&display=swap');

        /* Reset dasar untuk konsistensi antar browser */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box; /* Model box-sizing yang lebih intuitif */
        }

        body {
            font-family: 'Open Sans', sans-serif; /* Terapkan font yang diimpor */
            display: flex; /* Gunakan flexbox untuk memusatkan container */
            justify-content: center; /* Pusatkan horizontal */
            align-items: center; /* Pusatkan vertikal */
            min-height: 100vh; /* Pastikan body mengambil tinggi viewport penuh */
            /*background-color: #eef1f5; /* Warna latar belakang umum (abu-abu terang) */
            
            /* --- Tambahan untuk Background Image --- */
            background-image: url('gambar/bg.jpg'); /* Ganti 'gambar/bg.jpg' dengan path gambar latar belakang Anda */
            background-size: cover; /* Memastikan gambar mencakup seluruh area */
            background-position: center; /* Memusatkan gambar */
            background-repeat: no-repeat; /* Mencegah pengulangan gambar */
            background-attachment: fixed; /* Membuat latar belakang tetap saat di-scroll (opsional) */
            /* --- Akhir Tambahan Background Image --- */

            color: #333; /* Warna teks default */
            line-height: 1.6; /* Spasi baris untuk keterbacaan */
        }

        /* --- Container Utama --- */
        .main-container {
            display: flex; /* Mengatur dua kolom (sidebar dan konten) */
            width: 90%; /* Lebar responsif */
            max-width: 1050px; /* Lebar maksimum untuk desktop */
            background-color: rgba(255, 255, 255, 0.95); /* Latar belakang putih dengan sedikit transparansi */
            border-radius: 15px; /* Sudut membulat */
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1); /* Bayangan lembut */
            overflow: hidden; /* Penting untuk border-radius pada children */
            min-height: 600px; /* Tinggi minimum untuk layout yang baik */
        }

        /* --- Sidebar Profil (Kiri) --- */
        .profile-sidebar {
            flex: 1; /* Mengambil proporsi lebih kecil (misal: 1/3 lebar total) */
            background-color: rgba(248, 249, 250, 0.9); /* Latar belakang sidebar (abu-abu sangat terang) dengan sedikit transparansi */
            padding: 40px 30px;
            display: flex;
            flex-direction: column; /* Mengatur elemen secara vertikal */
            align-items: center; /* Memusatkan konten horizontal */
            text-align: center;
            border-right: 1px solid #eee; /* Garis pemisah tipis */
        }

        .profile-image-wrapper {
            width: 180px; /* Ukuran wadah gambar */
            height: 180px;
            border-radius: 50%; /* Membuat bentuk lingkaran */
            overflow: hidden; /* Memastikan gambar tetap di dalam lingkaran */
            margin-bottom: 25px;
            border: 6px solid #dee2e6; /* Border di sekitar gambar */
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1); /* Bayangan pada gambar */
        }

        .profile-picture {
            width: 100%;
            height: 100%;
            object-fit: cover; /* Memastikan gambar mengisi area tanpa terdistorsi */
            display: block; /* Menghilangkan spasi bawah yang mungkin ada pada img */
        }

        .profile-name {
            font-size: 2.4em; /* Ukuran font besar untuk nama */
            font-weight: 700; /* Sangat tebal */
            margin-bottom: 8px;
            color: #2c3e50; /* Warna nama yang kuat */
        }

        .profile-category {
            font-size: 1.1em;
            color: #7f8c8d; /* Warna abu-abu untuk kategori */
            letter-spacing: 1.8px; /* Spasi antar huruf untuk efek stylish */
            text-transform: uppercase; /* Huruf kapital semua */
            margin-bottom: 50px; /* Jarak bawah sebelum ikon sosial */
        }

        .social-links {
            margin-top: auto; /* Mendorong ikon ke bagian bawah sidebar */
            display: flex;
            gap: 25px; /* Jarak antar ikon */
        }

        .social-links a {
            color: #95a5a6; /* Warna ikon default (abu-abu sedang) */
            font-size: 2em; /* Ukuran ikon */
            transition: color 0.3s ease, transform 0.2s ease; /* Transisi halus saat hover */
        }

        .social-links a:hover {
            color: #3498db; /* Warna saat hover (biru cerah) */
            transform: translateY(-3px); /* Efek sedikit naik saat hover */
        }

        /* --- Area Konten (Kanan) --- */
        .content-area {
            flex: 2; /* Mengambil proporsi lebih besar (misal: 2/3 lebar total) */
            background-color: rgba(255, 255, 255, 0.98); /* Latar belakang konten (putih) dengan sedikit transparansi */
            padding: 50px;
            display: flex;
            flex-direction: column; /* Mengatur tombol secara vertikal */
            justify-content: center; /* Memusatkan tombol secara vertikal */
            align-items: flex-start; /* Mengatur tombol rata kiri */
        }

        .main-navigation {
            width: 100%;
            max-width: 350px; /* Batasi lebar maksimum navigasi/tombol */
            display: flex;
            flex-direction: column;
            gap: 22px; /* Jarak antar tombol */
        }

        .nav-button {
            background-color: #3498db; /* Warna tombol (biru cerah) */
            color: white;
            border: none;
            padding: 18px 30px; /* Padding di dalam tombol */
            font-size: 1.2em;
            font-weight: 600; /* Semi-tebal */
            text-transform: uppercase; /* Huruf kapital semua */
            border-radius: 10px; /* Sudut membulat pada tombol */
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.2s ease, box-shadow 0.3s ease;
            box-shadow: 0 6px 18px rgba(0, 0, 0, 0.15); /* Bayangan pada tombol */
            text-align: left; /* Teks tombol rata kiri */
            letter-spacing: 1px; /* Spasi antar huruf pada tombol */
        }

        .nav-button:hover {
            background-color: #2980b9; /* Warna tombol saat hover (biru lebih gelap) */
            transform: translateY(-4px); /* Efek sedikit naik yang lebih jelas */
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2); /* Bayangan lebih dalam saat hover */
        }

        /* --- Gaya Konten Placeholder (jika Anda menggunakannya) --- */
        .placeholder-content {
            margin-top: 40px;
            padding: 25px;
            border-left: 6px solid #3498db; /* Garis biru di kiri */
            background-color: #ecf0f1; /* Latar belakang abu-abu terang */
            border-radius: 8px;
            color: #555;
        }
        .placeholder-content h2 {
            font-size: 1.8em;
            margin-bottom: 10px;
            color: #2c3e50;
        }
        .placeholder-content p {
            font-size: 1em;
        }

        /* --- Media Queries untuk Responsivitas --- */

        /* Untuk tablet dan layar yang lebih kecil */
        @media (max-width: 992px) {
            .main-container {
                flex-direction: column; /* Mengubah tata letak menjadi kolom */
                width: 95%; /* Lebar sedikit lebih besar */
                max-width: 600px; /* Batasi lebar di layar menengah */
                min-height: unset; /* Hapus tinggi minimum untuk fleksibilitas */
            }

            .profile-sidebar, .content-area {
                width: 100%; /* Lebar penuh */
                padding: 30px 25px; /* Kurangi padding sedikit */
                border-right: none; /* Hapus border di sidebar */
            }

            .profile-sidebar {
                border-bottom: 1px solid #eee; /* Tambahkan border di bawah sidebar */
            }

            .profile-image-wrapper {
                width: 150px;
                height: 150px;
            }

            .profile-name {
                font-size: 2em;
            }

            .profile-category {
                font-size: 1em;
                margin-bottom: 30px;
            }

            .content-area {
                align-items: center; /* Pusatkan tombol di layar kecil */
            }

            .main-navigation {
                max-width: 90%; /* Tombol lebih lebar di layar kecil */
                align-items: center; /* Pusatkan tombol secara individu */
            }
            .nav-button {
                width: 100%; /* Tombol mengisi lebar maksimal navigasi */
                text-align: center; /* Teks tombol rata tengah */
            }
        }

        /* Untuk ponsel dan layar yang sangat kecil */
        @media (max-width: 576px) {
            .profile-sidebar, .content-area {
                padding: 25px 15px; /* Padding lebih kecil lagi */
            }

            .profile-image-wrapper {
                width: 120px;
                height: 120px;
            }

            .profile-name {
                font-size: 1.8em;
            }

            .profile-category {
                font-size: 0.85em;
                letter-spacing: 1px;
            }

            .social-links {
                gap: 15px;
            }

            .social-links a {
                font-size: 1.6em;
            }

            .nav-button {
                padding: 15px 20px;
                font-size: 1em;
            }
        }
    </style>
</head>
<body>
    <div class="main-container">
        <div class="profile-sidebar">
            <div class="profile-image-wrapper">
                <img src="gambar/pp.jpg" alt="Ahmad Fathullah" class="profile-picture">
            </div>
            <h1 class="profile-name">Ahmad Fathullah</h1>
            <p class="profile-category">Data Analyst and Digital Marketing</p>
            <div class="social-links">
                <a href="https://www.instagram.com/_ahmdfthllh_" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                <a href="https://www.linkedin.com/in/ahmad-fathullah-38119128b/" target="_blank" aria-label="Linkedin"><i class="fab fa-linkedin"></i></a>
                <a href="https://wa.me/087859548565" target="_blank" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
            </div>
        </div>

        <div class="content-area">
            <nav class="main-navigation">
                <button class="nav-button">ABOUT ME</button>
                <button class="nav-button">LOOKBOOK</button>
                <button class="nav-button">COLLABORATIONS</button>
                <button class="nav-button">WORK WITH ME</button>
            </nav>

            </div>
    </div>
</body>
</html>
