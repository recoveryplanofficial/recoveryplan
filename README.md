<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Investasi Cerdas - RecoveryPLAN</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');

        :root {
            --gradient-start: #0f0c29;
            --gradient-mid: #302b63;
            --gradient-end: #24243e;
            --accent-primary: #8A2BE2; /* Biru Violet/Ungu cerah */
            --accent-secondary: #4A90E2; /* Biru cerah */
            --accent-greenish: #28a745; /* Hijau untuk nuansa trading */
            --accent-pinkish: #C71585; /* Magenta/Pink untuk aksen gradien tambahan jika diperlukan */
            --text-primary: #F0F0F5;       /* Putih keabu-abuan muda */
            --text-secondary: #A0A0CC;     /* Abu-abu kebiruan muda */
            --surface-color: rgba(20, 20, 50, 0.5); /* Permukaan semi-transparan dengan hint biru/ungu */
            --surface-alt: rgba(30, 30, 60, 0.7);
            --border-color: rgba(138, 43, 226, 0.3); /* Border dengan warna ungu transparan */
            --shadow-color: rgba(138, 43, 226, 0.2); /* Bayangan dengan hint ungu */
            --scrollbar-track-color: rgba(40, 40, 70, 0.5);
            --scrollbar-thumb-color: var(--accent-primary);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background: linear-gradient(135deg, var(--gradient-start), var(--gradient-mid), var(--gradient-end));
            background-attachment: fixed;
            color: var(--text-primary);
            line-height: 1.7;
            overflow-x: hidden;
        }

        .container {
            max-width: 1150px;
            margin: auto;
            padding: 0 1.5rem;
        }

        /* Header & Navigation */
        .main-header {
            background: rgba(10, 10, 30, 0.6);
            backdrop-filter: blur(12px);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 15px rgba(0,0,0,0.3);
        }
        .main-header .container { display: flex; justify-content: space-between; align-items: center; }
        .logo { font-size: 1.75rem; font-weight: 800; color: var(--text-primary); text-decoration: none; letter-spacing: -0.5px; }
        .logo span { color: var(--accent-secondary); }
        .main-nav ul { list-style: none; display: flex; }
        .main-nav ul li { margin-left: 2.2rem; }
        .main-nav ul li a { color: var(--text-secondary); text-decoration: none; font-weight: 600; font-size: 0.95rem; transition: color 0.3s ease; position: relative; padding-bottom: 0.5rem; }
        .main-nav ul li a::after { content: ''; position: absolute; bottom: 0; left: 50%; transform: translateX(-50%); width: 0; height: 2.5px; background: var(--accent-primary); border-radius: 2px; transition: width 0.3s ease; }
        .main-nav ul li a:hover, .main-nav ul li a.active { color: var(--text-primary); }
        .main-nav ul li a:hover::after, .main-nav ul li a.active::after { width: 60%; }

        /* Hero Section */
        .hero { min-height: 90vh; display: flex; align-items: center; text-align: left; padding: 5rem 0; position: relative; }
        .hero-content { max-width: 700px; }
        .hero h1 {
            font-size: 3.8rem; font-weight: 800; margin-bottom: 1.5rem; line-height: 1.25;
            color: transparent; -webkit-background-clip: text; background-clip: text;
            background-image: linear-gradient(90deg, var(--accent-secondary), var(--accent-greenish), var(--accent-primary), var(--text-primary), var(--accent-secondary), var(--accent-greenish), var(--accent-primary));
            background-size: 400% 100%;
            animation: tradingTitleAnimation 5s linear infinite;
            display: inline-block; text-shadow: none;
        }
        .hero p { font-size: 1.15rem; margin-bottom: 2.5rem; color: var(--text-secondary); font-weight: 400; }

        /* Tombol Hero Section */
        .hero-buttons-container {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2.5rem;
            align-items: center;
            justify-content: flex-start;
        }
        .cta-button-main {
            display: inline-block;
            background: linear-gradient(90deg, var(--accent-primary), var(--accent-secondary));
            color: #FFFFFF;
            padding: 0.9rem 2.5rem;
            text-decoration: none;
            border-radius: 8px;
            font-weight: 700;
            font-size: 1.05rem;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 5px 20px var(--shadow-color);
        }
        .cta-button-main:hover {
            transform: translateY(-4px) scale(1.03);
            box-shadow: 0 8px 25px var(--shadow-color);
        }
        .cta-button-secondary {
            display: inline-flex;
            align-items: center;
            background: transparent;
            color: var(--accent-secondary);
            border: 2px solid var(--accent-secondary);
            padding: calc(0.9rem - 2px) calc(2.5rem - 2px);
            text-decoration: none;
            border-radius: 8px;
            font-weight: 700;
            font-size: 1.05rem;
            transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;
        }
        .cta-button-secondary:hover {
            background-color: var(--accent-secondary);
            color: var(--text-primary);
            transform: translateY(-4px) scale(1.03);
        }

        /* Section Styling */
        .section { padding: 5rem 0; }
        .section-title {
            text-align: center; font-size: 2.6rem; font-weight: 700; margin-bottom: 1rem;
            color: var(--text-primary); position: relative;
        }
        .section-title-decorator {
            display: block; width: 70px; height: 4px; background: var(--accent-primary);
            border-radius: 2px; margin: 0.5rem auto 3.5rem;
        }

        /* Video Section */
        .video-wrapper {
            position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;
            border-radius: 12px; border: 1px solid var(--border-color); box-shadow: 0 10px 30px rgba(0,0,0,0.4);
        }
        .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; }

        /* Products Section */
        .product-section-header {
            text-align: center;
            margin-bottom: 2rem;
        }
        .product-section-header p {
            font-size: 1.1rem;
            color: var(--text-secondary);
            max-width: 700px;
            margin: 0.5rem auto 0;
        }
        .product-row-title {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 1.5rem;
            padding-left: 5px;
        }
        .product-grid-container {
            overflow-x: auto;
            padding: 10px 5px 20px 5px;
            padding-right: 35px; /* Ruang untuk animasi petunjuk scroll */
            position: relative; 
            scrollbar-width: thin;
            scrollbar-color: var(--scrollbar-thumb-color) var(--scrollbar-track-color);
        }
        .product-grid-container::-webkit-scrollbar { height: 10px; }
        .product-grid-container::-webkit-scrollbar-track { background: var(--scrollbar-track-color); border-radius: 10px; }
        .product-grid-container::-webkit-scrollbar-thumb { background-color: var(--scrollbar-thumb-color); border-radius: 10px; border: 2px solid var(--scrollbar-track-color); }
        .product-grid-container::-webkit-scrollbar-thumb:hover { background-color: var(--accent-secondary); }

        /* Animasi Petunjuk Scroll Kanan-Kiri */
        .product-grid-container::after {
            content: '›'; 
            position: absolute;
            right: 8px; 
            top: 50%;
            transform: translateY(-50%);
            font-size: 2.8rem; 
            font-weight: bold;
            color: var(--accent-primary);
            opacity: 0; 
            pointer-events: none; 
            z-index: 5; 
            animation: peekScrollHint 2.2s ease-in-out 4 1.5s; /* Jalan 4x, delay 1.5s */
        }
        .product-grid-container:hover::after {
            animation: peekScrollHint 2.2s ease-in-out infinite 0s; /* Loop saat hover */
        }
        @keyframes peekScrollHint { /* Animasi panah "mengintip" */
            0%, 100% {
                opacity: 0;
                transform: translateY(-50%) translateX(0px);
            }
            30%, 70% {
                opacity: 0.9;
                transform: translateY(-50%) translateX(5px);
            }
            50% {
                opacity: 0.9;
                transform: translateY(-50%) translateX(-2px);
            }
        }


        .product-grid {
            display: flex;
            flex-wrap: nowrap;
            gap: 1.5rem;
            padding-bottom: 10px;
        }
        .product-card {
            flex: 0 0 310px;
            width: 310px;
            background: var(--surface-color);
            backdrop-filter: blur(5px);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            box-shadow: 0 8px 25px rgba(0,0,0,0.3);
            transition: transform 0.35s cubic-bezier(0.25, 0.8, 0.25, 1), box-shadow 0.35s cubic-bezier(0.25, 0.8, 0.25, 1);
            display: flex;
            flex-direction: column;
        }
        .product-card:hover { transform: translateY(-8px); box-shadow: 0 12px 30px var(--shadow-color); }
        .product-card-image-wrapper { width: 100%; height: 200px; overflow: hidden; flex-shrink: 0; }
        .product-card img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.4s ease; }
        .product-card:hover img { transform: scale(1.08); }
        .product-card-content {
            padding: 1.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .product-card h3 {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: var(--text-primary);
        }
        .product-card p {
            font-size: 0.9rem;
            color: var(--text-secondary);
            min-height: 40px;
            line-height: 1.5;
            margin-bottom: 0.75rem;
        }
        .product-action-area {
            margin-top: auto;
            padding-top: 0.5rem;
        }
        .price-container {
            margin-bottom: 1rem;
            display: flex;
            flex-wrap: wrap;
            align-items: baseline;
            gap: 0.5rem;
        }
        .original-price {
            text-decoration: line-through;
            color: var(--text-secondary);
            font-size: 0.9em;
            opacity: 0.8;
        }
        .current-price {
            font-size: 1.4em;
            font-weight: 700;
            color: var(--accent-secondary);
        }
        .product-cta {
            display: block;
            text-align: center;
            background: var(--accent-primary);
            color: var(--text-primary);
            padding: 0.8rem 1.5rem;
            text-decoration: none;
            border-radius: 6px;
            font-weight: 600;
            font-size: 0.95rem;
            border: none;
            transition: background-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 2px 8px rgba(0,0,0,0.2);
        }
        .product-cta:hover {
            background-color: var(--accent-secondary);
            color: var(--text-primary);
            transform: scale(1.03) translateY(-2px);
            box-shadow: 0 4px 12px var(--shadow-color);
        }

        /* WhatsApp CTA Section */
        .whatsapp-cta-section { background: var(--surface-alt); border-top: 1px solid var(--border-color); border-bottom: 1px solid var(--border-color); }
        .whatsapp-cta-section .container {
            text-align: center;
        }
        .whatsapp-cta-section p { font-size: 1.1rem; color: var(--text-secondary); margin-bottom: 2rem; max-width: 650px; margin-left: auto; margin-right: auto; }
        .whatsapp-button { display: inline-flex; align-items: center; background: #25D366; color: white; padding: 0.9rem 2.2rem; text-decoration: none; border-radius: 8px; font-weight: 700; font-size: 1.05rem; transition: background-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease; box-shadow: 0 4px 15px rgba(37, 211, 102, 0.25); }
        .whatsapp-button svg { width: 22px; height: 22px; margin-right: 10px; fill: white; }
        .whatsapp-button:hover { background-color: #1DAE50; transform: translateY(-3px) scale(1.03); box-shadow: 0 6px 20px rgba(37, 211, 102, 0.4); }

        /* Footer */
        .main-footer { text-align: center; padding: 2.5rem 0; background: #0A0A1A; color: var(--text-secondary); font-size: 0.85rem; }
        .main-footer p a { color: var(--accent-secondary); text-decoration: none; font-weight: 500; }
        .main-footer p a:hover { text-decoration: underline; }

        /* -- ANIMASI SCROLL -- */
        .scroll-animate {
            opacity: 0;
            transition: opacity 0.7s ease-out, transform 0.7s ease-out;
        }
        .scroll-animate.sa-fade-in { transform: translateY(0); }
        .scroll-animate.sa-slide-in-bottom { transform: translateY(40px); }
        .scroll-animate.sa-slide-in-left { transform: translateX(-40px); }
        .scroll-animate.sa-slide-in-right { transform: translateX(40px); }
        .scroll-animate.sa-scale-up { transform: scale(0.9); }

        .scroll-animate.is-visible {
            opacity: 1;
            transform: translateY(0) translateX(0) scale(1);
        }

        /* Animasi judul hero */
        @keyframes tradingTitleAnimation {
            0% { background-position: 0% 50%; }
            100% { background-position: 100% 50%; }
        }

        /* Responsive adjustments */
        @media (max-width: 992px) {
            .hero h1 { font-size: 3rem; }
            .hero p { font-size: 1.05rem; }
            .product-card { flex: 0 0 290px; width: 290px; }
        }
        @media (max-width: 768px) {
            .main-header .container { flex-direction: column; gap: 1rem; }
            .main-nav ul { padding-top: 0.5rem; justify-content: center; flex-wrap: wrap; }
            .main-nav ul li { margin: 0 0.8rem; }
            .hero { text-align: center; }
            .hero-content { max-width: 100%; text-align: center; }
            .hero h1 { font-size: 2.5rem; display: block; }
            .hero-buttons-container { justify-content: center; }
            .section-title { font-size: 2.2rem; }
            .product-card { flex: 0 0 270px; width: 270px; }
        }
        @media (max-width: 480px) {
            .hero-buttons-container {
                flex-direction: column;
                align-items: stretch;
            }
            .cta-button-main, .cta-button-secondary {
                width: 100%;
                text-align: center;
                justify-content: center;
            }
        }
    </style>
</head>
<body>

    <header class="main-header">
        <div class="container">
            <a href="#" class="logo">Recovery<span>PLAN</span></a>
            <nav class="main-nav">
                <ul>
                    <li><a href="#hero" class="active">Home</a></li>
                    <li><a href="#video">Intro</a></li>
                    <li><a href="#produk">Produk</a></li>
                    <li><a href="#kontak">Kontak</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section id="hero" class="hero">
        <div class="container">
            <div class="hero-content scroll-animate sa-slide-in-bottom">
                <h1>Platform Edukasi <span class="highlight-no-bg">Aset Digital</span> Terdepan</h1>
                <p>Bergabunglah dengan ribuan member lainnya dan mulailah perjalanan Anda di dunia aset digital dengan panduan dari para ahli.</p>
                <div class="hero-buttons-container">
                    <a href="#produk" class="cta-button-main">Lihat Program Kami</a>
                    <a href="https://t.me/NamaChannelTelegramAnda" target="_blank" class="cta-button-secondary telegram-button">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="20" height="20" fill="currentColor" style="margin-right: 8px;">
                            <path d="M9.78 18.65l.28-4.23a.5.5 0 0 0-.15-.48l-4.06-3.52 5.56-1.02H12l5.56 1.02-4.06 3.52a.5.5 0 0 0-.15.48l.28 4.23 4.18-9.05L22 2 2 8.57l5.42 2.1 2.1 5.42 4.44-7.34-4.18 9.92zM22 2L2 8.57l5.42 2.1 2.1 5.42 4.44-7.34-4.18 9.92L12 22l2.27-6.82L22 2z"/>
                        </svg>
                        Gabung Telegram
                    </a>
                </div>
            </div>
        </div>
    </section>

    <section id="video" class="section">
        <div class="container">
            <h2 class="section-title scroll-animate sa-fade-in">Kenali Kami Lebih Dekat</h2>
            <div class="section-title-decorator scroll-animate sa-fade-in" style="animation-delay: 0.1s;"></div>
            <div class="video-wrapper scroll-animate sa-scale-up" style="animation-delay: 0.2s;">
                 <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> </div>
        </div>
    </section>

    <section id="produk" class="section">
        <div class="container">
            <div class="product-section-header scroll-animate sa-fade-in">
                <h2 class="section-title">Pilihan Program Eksklusif</h2>
                <div class="section-title-decorator"></div>
                <p>Temukan program yang dirancang khusus untuk membantu Anda mencapai tujuan investasi aset digital Anda.</p>
            </div>

            <h3 class="product-row-title scroll-animate sa-fade-in">Kelas Populer</h3>
            <div class="product-grid-container scroll-animate sa-slide-in-bottom" style="animation-delay: 0.2s;">
                <div class="product-grid">
                    <div class="product-card">
                        <div class="product-card-image-wrapper"><img src="https://images.unsplash.com/photo-1640340434855-6084b1f4901c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTV8fGNyeXB0b3xlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=500&q=60" alt="Program Crypto Fundamental"></div>
                        <div class="product-card-content">
                            <div>
                                <h3>Crypto Fundamental</h3>
                                <p>Pahami dasar-dasar teknologi blockchain dan aset kripto dari nol hingga mahir.</p>
                            </div>
                            <div class="product-action-area">
                                <div class="price-container">
                                    <span class="original-price">Rp 1.500.000</span>
                                    <span class="current-price">Rp 999.000</span>
                                </div>
                                <a href="https://api.whatsapp.com/send?phone=6281234567890&text=Halo%2C%20saya%20tertarik%20dengan%20paket%20Crypto%20Fundamental." target="_blank" class="product-cta">Pilih Paket</a>
                            </div>
                        </div>
                    </div>
                    <div class="product-card">
                        <div class="product-card-image-wrapper"><img src="https://images.unsplash.com/photo-1639754390422-aad3562aa279?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTJ8fGNyeXB0b3xlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=500&q=60" alt="Program Analisa Teknikal"></div>
                        <div class="product-card-content">
                            <div>
                                <h3>Analisa Teknikal Pro</h3>
                                <p>Kuasai strategi trading dan analisa grafik untuk profit maksimal di pasar kripto.</p>
                            </div>
                            <div class="product-action-area">
                                <div class="price-container">
                                    <span class="original-price">Rp 2.000.000</span>
                                    <span class="current-price">Rp 1.499.000</span>
                                </div>
                                <a href="https://api.whatsapp.com/send?phone=6281234567890&text=Halo%2C%20saya%20tertarik%20dengan%20paket%20Analisa%20Teknikal%20Pro." target="_blank" class="product-cta">Pilih Paket</a>
                            </div>
                        </div>
                    </div>
                    <div class="product-card">
                        <div class="product-card-image-wrapper"><img src="https://images.unsplash.com/photo-1641838208069-aa0739f70bdb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjB8fGNyeXB0b3xlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=500&q=60" alt="Program DeFi & Staking"></div>
                        <div class="product-card-content">
                            <div>
                                <h3>DeFi & Staking Mastery</h3>
                                <p>Jelajahi dunia Decentralized Finance dan maksimalkan passive income Anda.</p>
                            </div>
                            <div class="product-action-area">
                                 <div class="price-container">
                                    <span class="original-price">Rp 1.800.000</span>
                                    <span class="current-price">Rp 1.250.000</span>
                                </div>
                                <a href="https://api.whatsapp.com/send?phone=6281234567890&text=Halo%2C%20saya%20tertarik%20dengan%20paket%20DeFi%20%26%20Staking%20Mastery." target="_blank" class="product-cta">Pilih Paket</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <h3 class="product-row-title scroll-animate sa-fade-in" style="margin-top: 3rem;">Workshop & Spesialisasi</h3>
            <div class="product-grid-container scroll-animate sa-slide-in-bottom" style="animation-delay: 0.3s;">
                <div class="product-grid">
                    <div class="product-card">
                        <div class="product-card-image-wrapper"><img src="https://images.unsplash.com/photo-1639151153981-6599bdd37d75?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8OHx8Y3J5cHRvJTIwbmV3c3xlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=500&q=60" alt="Program NFT & Metaverse"></div>
                        <div class="product-card-content">
                           <div>
                                <h3>NFT & Metaverse Explorer</h3>
                                <p>Selami potensi NFT dan tren Metaverse yang sedang berkembang pesat.</p>
                           </div>
                            <div class="product-action-area">
                                <div class="price-container">
                                    <span class="original-price">Rp 2.500.000</span>
                                    <span class="current-price">Rp 1.750.000</span>
                                </div>
                                <a href="https://api.whatsapp.com/send?phone=6281234567890&text=Halo%2C%20saya%20tertarik%20dengan%20paket%20NFT%20%26%20Metaverse%20Explorer." target="_blank" class="product-cta">Pilih Paket</a>
                            </div>
                        </div>
                    </div>
                     <div class="product-card">
                        <div class="product-card-image-wrapper"><img src="https://images.unsplash.com/photo-1621452709007-683690500694?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Nnx8Y3J5cHRvJTIwc2VjdXJpdHl8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=500&q=60" alt="Program Keamanan Aset Kripto"></div>
                        <div class="product-card-content">
                           <div>
                                <h3>Keamanan Aset Kripto</h3>
                                <p>Lindungi aset digital Anda dari berbagai ancaman siber dengan praktik terbaik.</p>
                           </div>
                            <div class="product-action-area">
                                <div class="price-container">
                                    <span class="original-price">Rp 1.200.000</span>
                                    <span class="current-price">Rp 850.000</span>
                                </div>
                                <a href="https://api.whatsapp.com/send?phone=6281234567890&text=Halo%2C%20saya%20tertarik%20dengan%20paket%20Keamanan%20Aset%20Kripto." target="_blank" class="product-cta">Pilih Paket</a>
                            </div>
                        </div>
                    </div>
                    <div class="product-card">
                        <div class="product-card-image-wrapper"><img src="https://images.unsplash.com/photo-1634704744977-0a06a950e7f7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTB8fGNyeXB0byUyMGZ1dHVyZXN8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=500&q=60" alt="Program Trading Futures"></div>
                        <div class="product-card-content">
                           <div>
                                <h3>Workshop Trading Futures</h3>
                                <p>Pelajari strategi lanjutan untuk trading derivatif di pasar aset digital.</p>
                           </div>
                            <div class="product-action-area">
                                <div class="price-container">
                                    <span class="original-price">Rp 3.000.000</span>
                                    <span class="current-price">Rp 2.250.000</span>
                                </div>
                                <a href="https://api.whatsapp.com/send?phone=6281234567890&text=Halo%2C%20saya%20tertarik%20dengan%20paket%20Workshop%20Trading%20Futures." target="_blank" class="product-cta">Pilih Paket</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="kontak" class="section whatsapp-cta-section">
        <div class="container scroll-animate sa-fade-in">
            <h2 class="section-title">Masih Ada Pertanyaan?</h2>
            <div class="section-title-decorator"></div>
            <p>Tim kami siap membantu Anda memilih program terbaik atau menjawab pertanyaan seputar investasi aset digital.</p>
            <a href="https://api.whatsapp.com/send?phone=6281234567890&text=Halo%2C%20saya%20tertarik%20untuk%20mengetahui%20lebih%20lanjut%20tentang%20program%20di%20RecoveryPLAN%2C%20bisakah%20Anda%20membantu%3F" class="whatsapp-button" target="_blank">
                <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12.04 2C6.58 2 2.13 6.45 2.13 11.91C2.13 13.66 2.59 15.36 3.45 16.86L2.05 22L7.31 20.5C8.76 21.31 10.36 21.76 12.04 21.76C17.5 21.76 21.95 17.31 21.95 11.85C21.95 6.39 17.5 2 12.04 2ZM12.04 20.13C10.56 20.13 9.13 19.72 7.92 19L7.52 18.77L4.32 19.68L5.27 16.57L5.03 16.17C4.32 14.91 3.91 13.45 3.91 11.91C3.91 7.41 7.58 3.74 12.04 3.74C16.5 3.74 20.17 7.41 20.17 11.85C20.17 16.3 16.5 20.13 12.04 20.13ZM17.29 14.45C17.09 14.35 16.08 13.85 15.88 13.78C15.68 13.7 15.55 13.65 15.41 13.89C15.28 14.14 14.81 14.71 14.64 14.88C14.48 15.04 14.31 15.06 14.04 14.96C13.77 14.86 12.95 14.59 11.99 13.73C11.23 13.05 10.71 12.21 10.58 11.96C10.45 11.71 10.57 11.59 10.69 11.47C10.8 11.35 10.94 11.17 11.07 11C11.21 10.84 11.26 10.71 11.39 10.47C11.53 10.22 11.48 10.03 11.41 9.86C11.35 9.7 10.89 8.51 10.72 8.04C10.56 7.58 10.39 7.63 10.26 7.62C10.15 7.61 9.98 7.61 9.81 7.61C9.65 7.61 9.41 7.66 9.21 7.91C9.01 8.15 8.51 8.61 8.51 9.72C8.51 10.82 9.24 11.88 9.37 12.05C9.5 12.21 10.83 14.33 12.87 15.16C14.59 15.85 14.91 15.73 15.31 15.68C15.79 15.62 16.76 15.08 16.96 14.88C17.16 14.68 17.16 14.53 17.29 14.45Z"/></svg>
                Chat via WhatsApp
            </a>
        </div>
    </section>

    <footer class="main-footer">
         <div class="container">
            <p>© <span id="currentYear"></span> <a href="#">RecoveryPLAN</a>. Dirancang untuk Edukasi Kripto Masa Depan.</p>
        </div>
    </footer>

    <script>
        document.getElementById('currentYear').textContent = new Date().getFullYear();

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetElement = document.querySelector(this.getAttribute('href'));
                if (targetElement) {
                    targetElement.scrollIntoView({ behavior: 'smooth' });
                }
                document.querySelectorAll('.main-nav ul li a').forEach(navLink => navLink.classList.remove('active'));
                this.classList.add('active');
            });
        });

        const scrollAnimatedElements = document.querySelectorAll('.scroll-animate');
        const scrollObserver = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('is-visible');
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.1 });

        scrollAnimatedElements.forEach(el => {
            scrollObserver.observe(el);
        });

        window.addEventListener('scroll', () => {
            let current = '';
            const sections = document.querySelectorAll('section[id]');
            const headerHeight = document.querySelector('.main-header')?.offsetHeight || 70;

            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (pageYOffset >= sectionTop - headerHeight) {
                    current = section.getAttribute('id');
                }
            });

            const navLinks = document.querySelectorAll('.main-nav ul li a');
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === current) {
                    link.classList.add('active');
                }
            });
            
            if (!current && pageYOffset < (sections[0]?.offsetTop - headerHeight || 0)) {
                 const homeLink = document.querySelector('.main-nav ul li a[href="#hero"]');
                 if(homeLink) homeLink.classList.add('active');
            }
        });
    </script>

</body>
</html>
