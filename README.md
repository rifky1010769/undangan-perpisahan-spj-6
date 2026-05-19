<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Undangan Perpisahan SDN Sepanjang Jaya VI</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --bg-dark: #0a0a0a;
            --card-bg: #161616;
            --accent: #d4af37; /* Warna Emas */
            --text-light: #f5f5f5;
            --text-dim: #a0a0a0;
        }

        * {
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            background-color: var(--bg-dark);
            color: var(--text-light);
            scroll-behavior: smooth;
            
            /* Desain Bunga di Tepi Kiri Atas dan Kanan Bawah */
            background-image: 
                url('https://www.transparentpng.com/download/floral/floral-frame-transparent-background-5.png'),
                url('https://www.transparentpng.com/download/floral/floral-frame-transparent-background-5.png');
            background-position: top left, bottom right;
            background-repeat: no-repeat;
            background-size: 220px;
            background-attachment: fixed;
        }

        /* Tombol Musik Melayang (Floating Audio Button) */
        .music-control {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 2000;
            background: rgba(22, 22, 22, 0.7);
            border: 1px solid var(--accent);
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            color: var(--accent);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
            transition: all 0.3s ease;
        }

        .music-control:hover {
            transform: scale(1.1);
        }

        /* Efek berputar kalau musik menyala */
        .rotating {
            animation: spin 4s linear infinite;
        }

        @keyframes spin {
            100% { transform: rotate(360deg); }
        }

        /* Bagian Atas / Header */
        header {
            height: 50vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px;
        }

        /* Gaya Tulisan UNDANGAN Utama */
        header .main-title {
            font-family: 'Arial', sans-serif;
            font-size: 1.2rem;
            color: var(--accent);
            letter-spacing: 6px;
            font-weight: bold;
            text-transform: uppercase;
            margin-bottom: 10px;
        }

        /* Gaya Huruf Sambung */
        header .sambung {
            font-family: 'Brush Script MT', 'Comic Sans MS', 'Georgia', cursive;
            font-style: italic;
            font-size: 1.8rem; 
            color: var(--text-light);
            margin-bottom: 5px;
            text-transform: none;
        }

        /* Gaya Cetak Tegak */
        header h1 {
            font-family: 'Impact', 'Arial Black', sans-serif;
            font-weight: 900;
            font-size: 2.5rem;
            color: var(--accent);
            margin: 5px 0 10px 0;
            line-height: 1.2;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        header .tahun {
            font-family: 'Arial', sans-serif;
            font-size: 1.3rem;
            color: var(--text-dim);
            letter-spacing: 2px;
            font-weight: bold;
        }

        /* Desain Galeri Foto Landscape */
        .foto-kenangan-container {
            max-width: 600px;
            margin: -10px auto 30px auto;
            padding: 0 20px;
        }

        .grid-foto {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
        }

        .frame-foto {
            width: 100%;
            aspect-ratio: 16 / 12;
            background-color: #222;
            border: 2px solid rgba(214, 175, 55, 0.25);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.6);
            transition: transform 0.4s ease, border-color 0.4s ease, box-shadow 0.4s ease;
        }

        .frame-foto img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .frame-foto:hover {
            transform: scale(1.04) translateY(-3px);
            border-color: var(--accent);
            box-shadow: 0 8px 20px rgba(214, 175, 55, 0.2);
        }

        .frame-foto:hover img {
            transform: scale(1.08);
        }

        /* Menu Navigasi di Bawah (Fixed Bottom) */
        nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(22, 22, 22, 0.95);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            display: flex;
            justify-content: space-around;
            padding: 12px 0;
            border-top: 1px solid var(--accent);
            z-index: 1000;
        }

        nav a {
            text-decoration: none;
            color: var(--text-dim);
            font-size: 0.7rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            flex: 1;
        }

        nav a i { 
            font-size: 1.2rem; 
            margin-bottom: 5px; 
            transition: transform 0.3s ease;
        }

        nav a:hover, nav a.active { 
            color: var(--accent); 
        }

        nav a:hover i, nav a.active i {
            transform: scale(1.2) translateY(-2px);
        }

        /* Wadah Konten Utama */
        .container {
            padding: 20px;
            padding-bottom: 110px; 
            max-width: 600px;
            margin: auto;
        }

        section {
            scroll-margin-top: 30px;
            margin-bottom: 40px;
        }

        /* Card Basik dengan Animasi Muncul */
        .card {
            background: var(--card-bg);
            border: 1px solid rgba(214, 175, 55, 0.25);
            padding: 30px 20px;
            border-radius: 15px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.7);
            text-align: center;
            transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
        }

        section:target .card {
            animation: highlightCard 0.8s ease-out forwards;
        }

        @keyframes highlightCard {
            0% {
                transform: translateY(20px);
                border-color: var(--accent);
                box-shadow: 0 8px 30px rgba(214, 175, 55, 0.2);
            }
            50% {
                transform: translateY(-4px);
                border-color: var(--accent);
                box-shadow: 0 8px 35px rgba(214, 175, 55, 0.4);
            }
            100% {
                transform: translateY(0);
                border-color: rgba(214, 175, 55, 0.25);
                box-shadow: 0 8px 25px rgba(0,0,0,0.7);
            }
        }

        .card h3 {
            font-family: 'Arial', sans-serif;
            color: var(--accent);
            font-size: 1.4rem;
            margin-top: 0;
            margin-bottom: 20px;
            border-bottom: 1px solid rgba(214, 175, 55, 0.2);
            padding-bottom: 10px;
            text-transform: uppercase;
        }

        .card p {
            line-height: 1.6;
            font-size: 0.98rem;
            color: var(--text-light);
            text-align: justify;
        }

        .card .text-center {
            text-align: center;
        }

        /* Tabel Acara / Rundown */
        .rundown-box {
            text-align: left;
        }

        .rundown-item {
            display: flex;
            justify-content: space-between;
            padding: 12px 0;
            border-bottom: 1px solid #262626;
        }

        .rundown-item:last-child {
            border-bottom: none;
        }

        .time {
            color: var(--accent);
            font-weight: bold;
            min-width: 90px;
        }

        .activity {
            flex: 1;
            padding-left: 10px;
            color: var(--text-light);
        }

        /* Google Maps Wrapper */
        .map-wrapper {
            border-radius: 10px;
            overflow: hidden;
            margin-top: 20px;
            border: 1px solid rgba(214, 175, 55, 0.4);
        }

        .map-wrapper iframe {
            width: 100%;
            height: 250px;
            border: 0;
            display: block;
        }

        /* Grid Detail Dress Code */
        .grid-dress {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin-top: 20px;
        }

        .dress-item {
            background: #1e1e1e;
            padding: 12px 8px;
            border-radius: 8px;
            font-size: 0.85rem;
            border: 1px solid #2a2a2a;
            transition: transform 0.3s ease, border-color 0.3s ease;
        }

        .dress-item:hover {
            transform: translateY(-3px);
            border-color: var(--accent);
        }

        .dress-item i {
            color: var(--accent);
            font-size: 1.1rem;
            margin-bottom: 6px;
            display: block;
        }

        /* Box Informasi Kado Tunggal */
        .box-kado {
            background: #1e1e1e;
            padding: 25px 15px;
            border-radius: 12px;
            border: 1px dashed var(--accent);
            margin-top: 15px;
        }

        .box-kado i {
            color: var(--accent);
            font-size: 2.5rem;
            margin-bottom: 15px;
            display: block;
        }

        .box-kado h4 {
            color: var(--text-light);
            font-size: 1.2rem;
            margin: 0 0 10px 0;
            font-weight: bold;
        }

        footer {
            text-align: center;
            padding: 20px 0 40px 0;
            color: var(--text-dim);
            font-size: 0.8rem;
        }
    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="c:\Users\Hype GLK\Downloads\WhatsApp Audio 2026-05-19 at 19.59.09.mpeg" type="audio/mp4">
    </audio>

    <div class="music-control" id="musicBtn" onclick="toggleMusic()">
        <i class="fas fa-music" id="musicIcon"></i>
    </div>

    <header>
        <div class="main-title">Undangan</div>
        <div class="sambung">Perpisahan dan Pelepasan</div>
        <h1>SDN SEPANJANG JAYA VI</h1>
        <div class="tahun">Tahun Pelajaran 2025 / 2026</div>
    </header>

    <div class="foto-kenangan-container">
        <div class="grid-foto">
            <div class="frame-foto"><img src="c:\Users\Hype GLK\Downloads\WhatsApp Image 2026-05-19 at 20.10.00.jpeg" alt="Kenangan 1"></div>
            <div class="frame-foto"><img src="c:\Users\Hype GLK\Downloads\WhatsApp Image 2026-05-17 at 22.38.01 (2).jpeg" alt="Kenangan 2"></div>
            <div class="frame-foto"><img src="c:\Users\Hype GLK\Downloads\WhatsApp Image 2026-05-17 at 22.38.01 (1).jpeg" alt="Kenangan 3"></div>
            <div class="frame-foto"><img src="c:\Users\Hype GLK\Downloads\WhatsApp Image 2026-05-17 at 22.38.01.jpeg" alt="Kenangan 4"></div>

        </div>
    </div>

    <div class="container">

        <section id="acara">
            <div class="card">
                <h3>Info Acara</h3>
                <p class="text-center" style="font-style: italic; color: var(--accent); margin-bottom: 15px;">Halo teman-teman seangkatan!</p>
                <p>Nggak kerasa ya, udah 6 tahun kita bareng-bareng di SDN Sepanjang Jaya VI. Dari yang dulu awal masuk sekolah masih malu-malu dan diantar orang tua, sekarang kita udah mau lulus aja dan bersiap masuk ke jenjang SMP.</p>
                <p>Banyak banget cerita, tawa, canda, dan kenangan gokil yang udah kita lewati di sekolah ini. Nah, buat merayakan kelulusan sekaligus jadi momen seru-seruan terakhir kita sebagai satu angkatan, yuk datang dan kumpul bareng di acara perpisahan kita yang bakal diadakan pada:</p>
                
                <p class="text-center" style="color: var(--accent); font-weight: bold; font-size: 1.2rem; margin: 25px 0 5px 0;">Rabu, 3 Juni 2026</p>
                <p class="text-center" style="margin-top: 0;">Pukul: 08.00 WIB s/d Selesai</p>
                
                <p style="margin-top: 20px;">Jangan sampai nggak datang ya, guys! Kehadiran kalian berharga banget biar momen terakhir kita di SD ini lengkap dan gak terlupakan. Sampai ketemu di tempat acara!</p>
            </div>
        </section>

        <section id="rundown">
            <div class="card">
                <h3>Rundown Seru</h3>
                <div class="rundown-box">
                    <div class="rundown-item"><span class="time">07.30 - 08.00</span><span class="activity">Kumpul & Registrasi Teman-teman</span></div>
                    <div class="rundown-item"><span class="time">08.00 - 08.30</span><span class="activity">Pembukaan Acara & Doa Bersama</span></div>
                    <div class="rundown-item"><span class="time">08.30 - 09.00</span><span class="activity">Sambutan-sambutan</span></div>
                    <div class="rundown-item"><span class="time">09.00 - 11.00</span><span class="activity">Prosesi Kelulusan & Kalungan Medali</span></div>
                    <div class="rundown-item"><span class="time">11.00 - 12.00</span><span class="activity">Pentas Seni & Tukar Kado Angkatan</span></div>
                    <div class="rundown-item"><span class="time">12.00 - Selesai</span><span class="activity">Sesi Foto Bebas, Seru-seruan & Penutup</span></div>
                </div>
            </div>
        </section>

        <section id="dresscode">
            <div class="card">
                <h3>Dress Code Kita</h3>
                <p class="text-center" style="margin-bottom: 15px;">Biar foto angkatan kita kelihatan kompak dan keren, wajib pakai ini ya:</p>
                <div class="grid-dress">
                    <div class="dress-item"><i class="fas fa-tshirt"></i><strong>Atasan</strong><br>Kaos Angkatan</div>
                    <div class="dress-item"><i class="fas fa-socks"></i><strong>Bawahan</strong><br>Bebas Rapi</div>
                    <div class="dress-item"><i class="fas fa-female"></i><strong>Hijab</strong><br>Diserasikan</div>
                </div>
            </div>
        </section>

        <section id="lokasi">
            <div class="card">
                <h3>Lokasi Kumpul</h3>
                <p class="text-center">Tahun ini acara pelepasan angkatan kita diadakan di:</p>
                <p class="text-center"><strong>Omah Joglo Nusantara (Rawalumbu)</strong></p>
                <p style="font-size: 0.9rem; color: var(--text-dim); text-align: center;">Jl. Pramuka, Sepanjang Jaya, Kec. Rawalumbu, Kota Bekasi, Jawa Barat</p>
                
                <div class="map-wrapper">
                    <iframe src="https://maps.google.com/maps?q=Omah%20Joglo%20Nusantara%20Rawalumbu%20Bekasi&t=&z=15&ie=UTF-8&iwloc=&output=embed" allowfullscreen="" loading="lazy"></iframe>
                </div>
            </div>
        </section>

        <section id="barang">
            <div class="card">
                <h3>Barang Bawaan</h3>
                <p class="text-center">Biar acara tukar kado akhir seangkatan makin asyik, jangan sampai lupa bawa barang ini:</p>
                <div class="box-kado">
                    <i class="fas fa-gift"></i>
                    <h4>Kado Perpisahan</h4>
                    <p style="margin: 0; font-size: 0.95rem; color: var(--text-dim); text-align: center;">
                        Masing-masing dari kita wajib bawa <strong style="color: var(--accent);">1 buah kado</strong> ya! Nanti bakal ditukar acak biar semua kebagian kenang-kenangan dari teman.
                    </p>
                </div>
            </div>
        </section>

        <footer>
            <p>© 2026 Panitia Perpisahan SDN Sepanjang Jaya VI</p>
        </footer>

    </div>
 
    <nav id="bottom-nav">
        <a href="#acara" class="nav-link"><i class="fas fa-calendar-alt"></i><span>Acara</span></a>
        <a href="#rundown" class="nav-link"><i class="fas fa-history"></i><span>Rundown</span></a>
        <a href="#dresscode" class="nav-link"><i class="fas fa-user-tie"></i><span>Dresscode</span></a>
        <a href="#lokasi" class="nav-link"><i class="fas fa-map-marked-alt"></i><span>Lokasi</span></a>
        <a href="#barang" class="nav-link"><i class="fas fa-shopping-bag"></i><span>Barang</span></a>
    </nav>

    <script>
        const audio = document.getElementById('bgMusic');
        const musicBtn = document.getElementById('musicBtn');
        const musicIcon = document.getElementById('musicIcon');
        let isPlaying = false;

        function toggleMusic() {
            if (isPlaying) {
                audio.pause();
                musicIcon.className = "fas fa-volume-mute";
                musicBtn.classList.remove('rotating');
                isPlaying = false;
            } else {
                audio.play().catch(err => console.log("Interaksi diperlukan"));
                musicIcon.className = "fas fa-music";
                musicBtn.classList.add('rotating');
                isPlaying = true;
            }
        }

        function startAudioOnInteraction() {
            if (!isPlaying) {
                audio.play().then(() => {
                    isPlaying = true;
                    musicIcon.className = "fas fa-music";
                    musicBtn.classList.add('rotating');
                    window.removeEventListener('click', startAudioOnInteraction);
                    window.removeEventListener('touchstart', startAudioOnInteraction);
                    window.removeEventListener('scroll', startAudioOnInteraction);
                }).catch(e => console.log("Menunggu klik"));
            }
        }

        window.addEventListener('click', startAudioOnInteraction);
        window.addEventListener('touchstart', startAudioOnInteraction);
        window.addEventListener('scroll', startAudioOnInteraction);

        // Script Scroll Navigasi Aktif
        const navLinks = document.querySelectorAll('.nav-link');
        navLinks.forEach(link => {
            link.addEventListener('click', function() {
                navLinks.forEach(item => item.classList.remove('active'));
                this.classList.add('active');
            });
        });

        window.addEventListener('scroll', () => {
            let fromTop = window.scrollY + 60;
            document.querySelectorAll('section').forEach(section => {
                if (section.offsetTop <= fromTop && section.offsetTop + section.offsetHeight > fromTop) {
                    navLinks.forEach(link => {
                        link.classList.remove('active');
                        if (link.getAttribute('href').substring(1) === section.getAttribute('id')) {
                            link.classList.add('active');
                        }
                    });
                }
            });
        });
    </script>
</body>
</html>
