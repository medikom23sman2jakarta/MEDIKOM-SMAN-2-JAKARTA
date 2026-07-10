<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>🧱 MEDIKOM SMAN 2 JAKARTA · Retro Edition</title>

    <!-- Font & Icons -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
    href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Quicksand:wght@400;600;700&display=swap"
    rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <!-- Bootstrap 5 untuk carousel & grid -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">

    <style>
        /* ===== RESET & BASE ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Quicksand', sans-serif;
            background: #0c0518;
            color: #fff;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* ===== RETRO LEGO BACKGROUND ===== */
        .retro-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            background:
                radial-gradient(ellipse at 20% 50%, #2d1b69 0%, transparent 60%),
                radial-gradient(ellipse at 80% 20%, #1a0a2e 0%, transparent 50%),
                radial-gradient(ellipse at 50% 80%, #3d1f6e 0%, transparent 50%),
                #0c0518;
            opacity: 0.9;
        }

        /* ===== FLOATING LEGO BRICKS (partikel) ===== */
        .lego-particle {
            position: fixed;
            width: 40px;
            height: 18px;
            border-radius: 4px 4px 2px 2px;
            opacity: 0.25;
            pointer-events: none;
            z-index: 1;
            animation: floatBrick linear infinite;
            box-shadow: inset 0 -4px 0 rgba(0, 0, 0, 0.2),
                0 0 12px rgba(255, 255, 255, 0.05);
        }
        .lego-particle::before {
            content: '';
            position: absolute;
            top: -6px;
            left: 6px;
            width: 8px;
            height: 6px;
            background: inherit;
            border-radius: 2px 2px 0 0;
            box-shadow: 12px 0 0 0 currentColor;
            opacity: 0.5;
        }
        .lego-particle:nth-child(odd)::before {
            left: 10px;
            box-shadow: 14px 0 0 0 currentColor;
        }

        @keyframes floatBrick {
            0% {
                transform: translateY(110vh) rotate(0deg) scale(0.6);
                opacity: 0.1;
            }
            10% {
                opacity: 0.3;
            }
            90% {
                opacity: 0.3;
            }
            100% {
                transform: translateY(-10vh) rotate(720deg) scale(1.2);
                opacity: 0;
            }
        }

        /* ===== KONTEN HALAMAN ===== */
        .page {
            position: relative;
            z-index: 2;
            width: 100%;
            min-height: 100vh;
            display: none;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.6s ease, transform 0.6s ease;
            padding: 20px;
        }
        .page.active {
            display: flex;
            opacity: 1;
            transform: translateY(0);
        }

        /* ===== MAIN WRAPPER (untuk page1) ===== */
        .main-wrapper {
            max-width: 1200px;
            margin: 0 auto;
            width: 100%;
        }

        /* ===== HEADER / JUDUL BERNYALA ===== */
        .hero {
            text-align: center;
            padding: 50px 20px 30px;
            position: relative;
        }
        .hero .badge {
            display: inline-block;
            background: #f5cd1f;
            color: #1a0a2e;
            font-family: 'Press Start 2P', monospace;
            font-size: 0.65rem;
            padding: 6px 18px;
            border-radius: 30px;
            letter-spacing: 2px;
            margin-bottom: 20px;
            box-shadow: 0 0 20px rgba(245, 205, 31, 0.4);
            text-transform: uppercase;
        }
        .glow-title {
            font-family: 'Press Start 2P', monospace;
            font-size: clamp(2rem, 8vw, 4.5rem);
            line-height: 1.2;
            background: linear-gradient(135deg, #ffe74a, #ff6bcd, #00f0ff, #ffe74a);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 4s ease-in-out infinite, glowPulse 2s ease-in-out infinite alternate;
            text-shadow: 0 0 40px rgba(255, 107, 205, 0.3);
            filter: drop-shadow(0 0 30px rgba(255, 107, 205, 0.2));
            letter-spacing: 2px;
            word-break: break-word;
        }
        @keyframes gradientShift {
            0%,
            100% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
        }
        @keyframes glowPulse {
            0% {
                filter: drop-shadow(0 0 20px rgba(255, 107, 205, 0.2)) drop-shadow(0 0 40px rgba(0, 240, 255, 0.1));
            }
            100% {
                filter: drop-shadow(0 0 40px rgba(255, 107, 205, 0.5)) drop-shadow(0 0 80px rgba(0, 240, 255, 0.3));
            }
        }
        .sub-glow {
            font-family: 'Press Start 2P', monospace;
            font-size: clamp(0.6rem, 1.8vw, 0.95rem);
            color: #a78bcb;
            margin-top: 16px;
            letter-spacing: 3px;
            text-shadow: 0 0 20px rgba(167, 139, 203, 0.3);
            animation: flicker 3s infinite alternate;
        }
        @keyframes flicker {
            0%,
            90% {
                opacity: 1;
            }
            92% {
                opacity: 0.6;
            }
            94% {
                opacity: 1;
            }
            96% {
                opacity: 0.4;
            }
            100% {
                opacity: 1;
            }
        }

        /* ===== LOGO HERO ===== */
        .hero-logo {
            max-width: 10px;
            border-radius: 20px;
            box-shadow: 0 0 30px rgba(245, 205, 31, 0.3), 0 0 60px rgba(255, 107, 205, 0.2);
            margin: 10px 0 20px;
            animation: floatLogo 3s ease-in-out infinite;
        }
        @keyframes floatLogo {
            0%,
            100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-12px);
            }
        }

        /* ===== TOMBOL "KLIK DI SINI" ===== */
        .btn-wrapper {
            text-align: center;
            margin: 30px 0 40px;
        }
        .btn-klik {
            position: relative;
            display: inline-block;
            padding: 18px 56px;
            font-family: 'Press Start 2P', monospace;
            font-size: clamp(1rem, 2.5vw, 1.6rem);
            font-weight: 700;
            color: #1a0a2e;
            background: linear-gradient(135deg, #ffe74a, #f5cd1f);
            border: none;
            border-radius: 16px;
            cursor: pointer;
            box-shadow:
                0 0 0 4px #1a0a2e,
                0 0 0 8px #f5cd1f,
                0 0 40px rgba(245, 205, 31, 0.5);
            transition: all 0.25s ease;
            text-transform: uppercase;
            letter-spacing: 2px;
            z-index: 5;
            text-decoration: none;
        }
        .btn-klik:hover {
            transform: scale(1.08) translateY(-4px);
            box-shadow:
                0 0 0 4px #1a0a2e,
                0 0 0 8px #ffe74a,
                0 0 60px rgba(245, 205, 31, 0.8),
                0 20px 40px rgba(0, 0, 0, 0.4);
        }
        .btn-klik:active {
            transform: scale(0.94);
        }
        .btn-klik .fa {
            margin-right: 12px;
        }

        /* ===== SECTION TITLE (halaman1) ===== */
        .section-title {
            font-family: 'Press Start 2P', monospace;
            font-size: clamp(1rem, 2.5vw, 1.8rem);
            text-align: center;
            margin: 50px 0 30px;
            color: #ffe74a;
            text-shadow: 0 0 30px rgba(255, 231, 74, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 16px;
            flex-wrap: wrap;
        }
        .section-title .fa {
            color: #ff6bcd;
            font-size: 1.8rem;
        }
        .section-label {
            display: inline-block;
            background: rgba(245, 205, 31, 0.15);
            color: #ffe74a;
            font-family: 'Press Start 2P', monospace;
            font-size: 0.6rem;
            padding: 6px 16px;
            border-radius: 30px;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 10px;
            border: 1px solid rgba(245, 205, 31, 0.3);
        }

        /* ===== VISUAL EFFECTS CANVAS ===== */
        .visual-effects {
            background: rgba(45, 27, 105, 0.4);
            border-radius: 28px;
            padding: 30px 20px;
            border: 2px solid rgba(245, 205, 31, 0.2);
            margin-bottom: 40px;
            backdrop-filter: blur(4px);
            position: relative;
            overflow: hidden;
            min-height: 180px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
        }
        .visual-effects canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 28px;
            pointer-events: none;
        }
        .visual-effects .overlay-text {
            position: relative;
            z-index: 2;
            font-family: 'Press Start 2P', monospace;
            font-size: clamp(0.9rem, 2vw, 1.4rem);
            color: #fff;
            text-shadow: 0 0 30px rgba(255, 107, 205, 0.5), 0 0 60px rgba(0, 240, 255, 0.3);
            animation: pulseText 2s infinite alternate;
            text-align: center;
            padding: 10px;
        }
        .visual-effects .overlay-text .fa {
            color: #ffe74a;
            margin: 0 10px;
        }
        @keyframes pulseText {
            0% {
                opacity: 0.7;
                transform: scale(0.98);
            }
            100% {
                opacity: 1;
                transform: scale(1.04);
            }
        }

        /* ===== KOLASE FOTO / GRID CARD (halaman1) ===== */
        .collage-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        .collage-item {
            background: rgba(45, 27, 105, 0.35);
            border-radius: 20px;
            padding: 16px;
            border: 2px solid rgba(255, 255, 255, 0.06);
            backdrop-filter: blur(4px);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        .collage-item:hover {
            transform: translateY(-8px);
            border-color: #f5cd1f;
            box-shadow: 0 12px 40px rgba(245, 205, 31, 0.15);
        }
        .collage-item .media {
            width: 100%;
            aspect-ratio: 1/1;
            border-radius: 14px;
            overflow: hidden;
            background: #1a0a2e;
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.8rem;
            color: #a78bcb;
        }
        .collage-item .media img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .collage-item .caption {
            font-weight: 600;
            font-size: 0.95rem;
            color: #d4c4f0;
            margin-bottom: 4px;
        }
        .collage-item .sub-caption {
            font-size: 0.8rem;
            color: #a78bcb;
        }
        .collage-item .message {
            font-size: 0.9rem;
            color: #ffe74a;
            margin-top: 8px;
            padding: 8px 12px;
            background: rgba(245, 205, 31, 0.08);
            border-radius: 30px;
            width: 100%;
            border-left: 3px solid #f5cd1f;
        }

        /* ===== PROFILE CARD (halaman1) ===== */
        .profile-card {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            align-items: center;
            background: rgba(45, 27, 105, 0.35);
            border-radius: 20px;
            padding: 24px;
            border: 2px solid rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(4px);
            margin-bottom: 20px;
            transition: all 0.3s ease;
        }
        .profile-card:hover {
            border-color: #f5cd1f;
            box-shadow: 0 12px 40px rgba(245, 205, 31, 0.1);
            transform: translateY(-4px);
        }
        .profile-card img {
            width: 140px;
            height: 160px;
            object-fit: cover;
            border-radius: 16px;
            flex-shrink: 0;
            border: 3px solid rgba(245, 205, 31, 0.3);
        }
        .profile-card .profile-info h4 {
            font-family: 'Press Start 2P', monospace;
            font-size: 0.85rem;
            color: #ffe74a;
            margin-bottom: 6px;
        }
        .profile-card .profile-info .role-badge {
            display: inline-block;
            font-size: 0.6rem;
            font-family: 'Press Start 2P', monospace;
            padding: 4px 12px;
            border-radius: 30px;
            margin-bottom: 8px;
            letter-spacing: 1px;
        }
        .role-badge.pembina {
            background: rgba(0, 240, 255, 0.2);
            color: #00f0ff;
        }
        .role-badge.ketua {
            background: rgba(255, 107, 205, 0.2);
            color: #ff6bcd;
        }
        .profile-card .profile-info p {
            font-size: 0.9rem;
            color: #d4c4f0;
            line-height: 1.7;
        }

        /* ===== PRESTASI GRID CARD ===== */
        .prestasi-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 20px;
            margin-top: 20px;
            justify-content: center;
        }
        .prestasi-item {
            background: linear-gradient(145deg, rgba(45,27,105,0.5), rgba(26,10,46,0.6));
            border: 2px solid rgba(245,205,31,0.25);
            border-radius: 24px;
            padding: 24px 18px;
            text-align: center;
            backdrop-filter: blur(6px);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
            overflow: hidden;
            word-break: break-word;
        }
        .prestasi-item::before {
            content: '';
            position: absolute;
            top: -20px;
            right: -20px;
            width: 80px;
            height: 80px;
            background: radial-gradient(circle, rgba(245,205,31,0.3) 0%, transparent 70%);
            border-radius: 50%;
            z-index: 0;
            transition: 0.3s;
        }
        .prestasi-item:hover::before {
            width: 120px;
            height: 120px;
            top: -30px;
            right: -30px;
        }
        .prestasi-item:hover {
            transform: translateY(-8px);
            border-color: #f5cd1f;
            box-shadow: 0 16px 45px rgba(245,205,31,0.25);
        }
        .prestasi-item .icon-trophy {
            font-size: 2.8rem;
            color: #f5cd1f;
            margin-bottom: 10px;
            filter: drop-shadow(0 0 12px rgba(245,205,31,0.5));
            z-index: 1;
            position: relative;
        }
        .prestasi-item h5 {
            font-family: 'Press Start 2P', monospace;
            font-size: 0.75rem;
            color: #ffe74a;
            margin-bottom: 8px;
            z-index: 1;
            position: relative;
            line-height: 1.4;
            max-width: 100%;
        }
        .prestasi-item .desc {
            font-size: 0.85rem;
            color: #d4c4f0;
            margin-bottom: 16px;
            z-index: 1;
            position: relative;
        }
        .prestasi-item .btn-lihat-sertifikat {
            font-family: 'Press Start 2P', monospace;
            font-size: 0.55rem;
            padding: 8px 18px;
            background: transparent;
            border: 2px solid #f5cd1f;
            color: #f5cd1f;
            border-radius: 30px;
            cursor: pointer;
            transition: 0.3s;
            z-index: 1;
            position: relative;
            letter-spacing: 1px;
            text-transform: uppercase;
            white-space: nowrap;
        }
        .prestasi-item .btn-lihat-sertifikat:hover {
            background: #f5cd1f;
            color: #1a0a2e;
            box-shadow: 0 0 25px rgba(245,205,31,0.7);
        }

        /* ===== CAROUSEL ===== */
        .carousel-retro {
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 0 60px rgba(245, 205, 31, 0.15);
            border: 3px solid rgba(245, 205, 31, 0.2);
        }
        .carousel-retro .carousel-item img {
            height: 420px;
            object-fit: cover;
        }
        .carousel-retro .carousel-control-prev-icon,
        .carousel-retro .carousel-control-next-icon {
            background-color: rgba(245, 205, 31, 0.7);
            border-radius: 50%;
            padding: 20px;
            box-shadow: 0 0 20px rgba(245, 205, 31, 0.4);
        }

        /* ===== VIDEO WRAPPER ===== */
        .video-wrapper {
            border: 3px solid rgba(245, 205, 31, 0.2);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 0 60px rgba(245, 205, 31, 0.1);
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .video-wrapper video {
            width: 100%;
            height: auto;
            aspect-ratio: 16 / 9;
            object-fit: cover;
            display: block;
        }

        /* ===== CONTACT CARD ===== */
        .contact-card {
            background: rgba(45, 27, 105, 0.35);
            border: 2px solid rgba(255, 255, 255, 0.06);
            border-radius: 20px;
            padding: 24px 20px;
            text-align: center;
            transition: all 0.3s;
            backdrop-filter: blur(4px);
            text-decoration: none;
            color: inherit;
            display: block;
            height: 100%;
        }
        .contact-card:hover {
            transform: translateY(-4px);
            border-color: #f5cd1f;
            box-shadow: 0 12px 40px rgba(245, 205, 31, 0.15);
        }
        .contact-card .icon-circle {
            width: 56px;
            height: 56px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 14px;
            font-size: 1.4rem;
        }
        .contact-card h5 {
            font-weight: 700;
            font-size: 1rem;
            margin-bottom: 4px;
            color: #ffe74a;
        }
        .contact-card p {
            font-size: 0.82rem;
            color: #d4c4f0;
            margin: 0;
        }

        /* ===== MARQUEE ===== */
        .marquee-wrap {
            background: rgba(245, 205, 31, 0.1);
            border-top: 1px solid rgba(245, 205, 31, 0.2);
            border-bottom: 1px solid rgba(245, 205, 31, 0.2);
            color: #ffe74a;
            padding: 10px 0;
            overflow: hidden;
            white-space: nowrap;
            font-weight: 700;
            letter-spacing: 3px;
            font-size: 0.75rem;
            text-transform: uppercase;
            font-family: 'Press Start 2P', monospace;
            margin: 20px 0;
        }
        .marquee-wrap .marquee-inner {
            display: inline-block;
            animation: marqueeScroll 20s linear infinite;
        }
        @keyframes marqueeScroll {
            0% {
                transform: translateX(0);
            }
            100% {
                transform: translateX(-50%);
            }
        }

        /* ===== NAV RETRO ===== */
        .nav-retro {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 8px;
            margin: 20px 0;
        }
        .nav-retro a {
            font-family: 'Press Start 2P', monospace;
            font-size: 0.55rem;
            color: #d4c4f0;
            text-decoration: none;
            padding: 8px 14px;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.25s;
            letter-spacing: 1px;
            background: rgba(45, 27, 105, 0.3);
        }
        .nav-retro a:hover {
            color: #ffe74a;
            border-color: #f5cd1f;
            box-shadow: 0 0 20px rgba(245, 205, 31, 0.2);
            background: rgba(245, 205, 31, 0.1);
        }
        .nav-retro a.nav-daftar {
            background: rgba(0, 163, 78, 0.3);
            border-color: #00a34e;
            color: #00ff88;
            animation: pulseDaftar 2s infinite;
        }
        .nav-retro a.nav-daftar:hover {
            background: #00a34e;
            color: #fff;
            border-color: #00ff88;
            box-shadow: 0 0 30px rgba(0, 255, 136, 0.4);
        }
        @keyframes pulseDaftar {
            0%,
            100% {
                box-shadow: 0 0 8px rgba(0, 163, 78, 0.3);
            }
            50% {
                box-shadow: 0 0 20px rgba(0, 255, 136, 0.6);
            }
        }

        /* ===== FLOATING DAFTAR BUTTON ===== */
        .floating-daftar {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 100;
            font-family: 'Press Start 2P', monospace;
            font-size: 0.65rem;
            padding: 16px 24px;
            background: linear-gradient(135deg, #00a34e, #00cc5f);
            color: #fff;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 8px 30px rgba(0, 163, 78, 0.5), 0 0 0 3px #1a0a2e, 0 0 0 6px rgba(0, 255, 136, 0.3);
            transition: all 0.3s ease;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
            letter-spacing: 1px;
            animation: bounceFloat 2s ease-in-out infinite;
        }
        .floating-daftar:hover {
            transform: translateY(-6px) scale(1.05);
            box-shadow: 0 14px 40px rgba(0, 255, 136, 0.6), 0 0 0 3px #1a0a2e, 0 0 0 6px #00ff88;
            color: #fff;
            background: linear-gradient(135deg, #00cc5f, #00ff88);
        }
        .floating-daftar .fa {
            font-size: 1.2rem;
            animation: spinIcon 3s linear infinite;
        }
        @keyframes bounceFloat {
            0%,
            100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }
        @keyframes spinIcon {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }

        /* ===== SECTION PENDAFTARAN ===== */
        .daftar-section {
            background: linear-gradient(135deg, rgba(0, 163, 78, 0.2), rgba(0, 255, 136, 0.08));
            border: 3px solid rgba(0, 163, 78, 0.5);
            border-radius: 32px;
            padding: 40px 30px;
            text-align: center;
            margin: 40px 0;
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(4px);
            box-shadow: 0 0 60px rgba(0, 163, 78, 0.2);
        }
        .daftar-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(0, 255, 136, 0.1), transparent, rgba(0, 255, 136, 0.1), transparent);
            animation: rotateDaftar 8s linear infinite;
            pointer-events: none;
        }
        @keyframes rotateDaftar {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }
        .daftar-section .daftar-content {
            position: relative;
            z-index: 2;
        }
        .daftar-section h2 {
            font-family: 'Press Start 2P', monospace;
            font-size: clamp(1.2rem, 3vw, 2rem);
            color: #00ff88;
            text-shadow: 0 0 30px rgba(0, 255, 136, 0.4);
            margin-bottom: 16px;
        }
        .daftar-section p {
            color: #d4c4f0;
            font-size: 1rem;
            margin-bottom: 24px;
            line-height: 1.8;
        }
        .daftar-section .btn-daftar-besar {
            display: inline-block;
            font-family: 'Press Start 2P', monospace;
            font-size: clamp(0.8rem, 2vw, 1.2rem);
            padding: 18px 48px;
            background: linear-gradient(135deg, #00a34e, #00cc5f);
            color: #fff;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            text-decoration: none;
            letter-spacing: 2px;
            box-shadow: 0 0 30px rgba(0, 255, 136, 0.4), 0 0 0 4px #1a0a2e, 0 0 0 8px rgba(0, 255, 136, 0.3);
            transition: all 0.3s ease;
            animation: pulseDaftarBig 2s infinite;
        }
        .daftar-section .btn-daftar-besar:hover {
            transform: scale(1.06) translateY(-4px);
            box-shadow: 0 0 50px rgba(0, 255, 136, 0.7), 0 0 0 4px #1a0a2e, 0 0 0 8px #00ff88;
            background: linear-gradient(135deg, #00cc5f, #00ff88);
            color: #1a0a2e;
        }
        @keyframes pulseDaftarBig {
            0%,
            100% {
                box-shadow: 0 0 30px rgba(0, 255, 136, 0.4), 0 0 0 4px #1a0a2e, 0 0 0 8px rgba(0, 255, 136, 0.3);
            }
            50% {
                box-shadow: 0 0 50px rgba(0, 255, 136, 0.7), 0 0 0 4px #1a0a2e, 0 0 0 8px #00ff88;
            }
        }

        /* ===== FOOTER ===== */
        .footer {
            margin-top: 50px;
            text-align: center;
            font-size: 0.7rem;
            color: #6a4f8a;
            font-family: 'Press Start 2P', monospace;
            letter-spacing: 1px;
            border-top: 1px solid rgba(255, 255, 255, 0.04);
            padding-top: 30px;
        }
        .footer .fa {
            color: #ff6bcd;
        }

        /* ========== HALAMAN 2 : KARTU DIGITAL ========== */
        .digital-card {
            width: 90%;
            max-width: 500px;
            background: linear-gradient(145deg, #2d1b69, #1a0a2e);
            border: 4px solid #f5cd1f;
            border-radius: 32px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 0 80px rgba(245, 205, 31, 0.25), 0 20px 60px rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            animation: popIn 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            margin: 20px;
        }
        @keyframes popIn {
            0% {
                opacity: 0;
                transform: scale(0.6) rotate(-6deg);
            }
            100% {
                opacity: 1;
                transform: scale(1) rotate(0deg);
            }
        }
        .card-logo {
            width: 80px;
            height: 80px;
            object-fit: contain;
            border-radius: 20px;
            margin: 0 auto 20px;
            display: block;
            border: 3px solid #f5cd1f;
            box-shadow: 0 0 30px rgba(245, 205, 31, 0.4);
            animation: floatLogo 3s ease-in-out infinite;
        }
        .card-title {
            font-family: 'Press Start 2P', monospace;
            font-size: 1.2rem;
            background: linear-gradient(135deg, #ffe74a, #ff6bcd);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            letter-spacing: 2px;
        }
        .card-subtitle {
            font-family: 'Press Start 2P', monospace;
            font-size: 0.65rem;
            color: #a78bcb;
            margin-bottom: 20px;
            letter-spacing: 2px;
        }
        .divider {
            width: 80px;
            height: 3px;
            background: #f5cd1f;
            margin: 15px auto;
            border-radius: 2px;
        }
        .info-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            margin: 20px 0;
            text-align: left;
        }
        .info-item {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            padding: 10px;
            border: 1px solid rgba(245, 205, 31, 0.2);
            transition: all 0.3s;
        }
        .info-item:hover {
            border-color: #f5cd1f;
            box-shadow: 0 0 15px rgba(245, 205, 31, 0.2);
            transform: translateY(-2px);
        }
        .info-item i {
            color: #ff6bcd;
            margin-right: 6px;
            font-size: 1rem;
        }
        .info-item .label {
            font-weight: 600;
            font-size: 0.75rem;
            color: #ffe74a;
            display: block;
            margin-bottom: 4px;
        }
        .info-item .value {
            font-size: 0.9rem;
            color: #d4c4f0;
        }
        .contact-row {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 25px 0 15px;
        }
        .contact-row a {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
            border: 2px solid rgba(245, 205, 31, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            font-size: 1.4rem;
            text-decoration: none;
            transition: all 0.3s;
        }
        .contact-row a:hover {
            background: #f5cd1f;
            color: #1a0a2e;
            border-color: #f5cd1f;
            transform: translateY(-4px);
            box-shadow: 0 10px 25px rgba(245, 205, 31, 0.4);
        }
        .btn-back {
            display: inline-block;
            margin-top: 15px;
            padding: 12px 30px;
            font-family: 'Press Start 2P', monospace;
            font-size: 0.7rem;
            background: #ff6bcd;
            color: #1a0a2e;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s;
            box-shadow: 0 0 20px rgba(255, 107, 205, 0.4);
        }
        .btn-back:hover {
            background: #ffe74a;
            transform: scale(1.05);
            box-shadow: 0 0 40px rgba(255, 231, 74, 0.5);
        }
        .btn-daftar-card {
            display: inline-block;
            margin: 10px 8px;
            padding: 10px 22px;
            font-family: 'Press Start 2P', monospace;
            font-size: 0.6rem;
            background: linear-gradient(135deg, #00a34e, #00cc5f);
            color: #fff;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s;
            box-shadow: 0 0 16px rgba(0, 255, 136, 0.35);
            letter-spacing: 1px;
        }
        .btn-daftar-card:hover {
            background: #00ff88;
            color: #1a0a2e;
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(0, 255, 136, 0.6);
        }
        .quote {
            font-style: italic;
            color: #a78bcb;
            margin-top: 20px;
            font-size: 0.8rem;
        }

        /* ===== MODAL STYLE ===== */
        .modal-content {
            background-color: transparent !important;
            border: none !important;
        }
        .modal-backdrop.show {
            opacity: 0.8;
            background-color: #0c0518;
        }
        .modal-img-only {
            max-width: 90vw;
            max-height: 85vh;
            border-radius: 20px;
            border: 4px solid #f5cd1f;
            box-shadow: 0 0 60px rgba(245, 205, 31, 0.4), 0 0 120px rgba(255, 107, 205, 0.2);
            object-fit: contain;
            animation: popIn 0.5s ease;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            .hero {
                padding: 30px 10px 20px;
            }
            .btn-klik {
                padding: 14px 32px;
                font-size: 0.9rem;
            }
            .visual-effects {
                min-height: 140px;
                padding: 20px 14px;
            }
            .profile-card {
                flex-direction: column;
                text-align: center;
            }
            .profile-card img {
                width: 120px;
                height: 140px;
                margin: 0 auto;
            }
            .daftar-section {
                padding: 24px 16px;
                border-radius: 20px;
            }
            .daftar-section .btn-daftar-besar {
                padding: 14px 28px;
                font-size: 0.7rem;
            }
            .prestasi-grid {
                grid-template-columns: 1fr;
                gap: 16px;
            }
            .prestasi-item {
                padding: 20px 16px;
            }
            .prestasi-item h5 {
                font-size: 0.65rem;
            }
            .carousel-retro .carousel-item img {
                height: 260px;
            }
            .floating-daftar {
                bottom: 20px;
                right: 15px;
                font-size: 0.5rem;
                padding: 12px 18px;
                gap: 6px;
            }
            .floating-daftar .fa {
                font-size: 0.9rem;
            }
            .hide-on-mobile {
                display: none;
            }
            .section-title {
                font-size: 0.9rem;
                gap: 10px;
            }
            .section-title .fa {
                font-size: 1.4rem;
            }
            .nav-retro a {
                font-size: 0.5rem;
                padding: 6px 10px;
            }
        }

        @media (max-width: 480px) {
            .glow-title {
                font-size: 2rem;
            }
            .btn-klik {
                padding: 12px 24px;
                font-size: 0.8rem;
            }
            .prestasi-item h5 {
                font-size: 0.6rem;
            }
            .prestasi-item .btn-lihat-sertifikat {
                font-size: 0.5rem;
                padding: 6px 14px;
            }
        }

        /* ===== SCROLLBAR ===== */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0c0518;
        }
        ::-webkit-scrollbar-thumb {
            background: #2d1b69;
            border-radius: 10px;
            border: 1px solid #f5cd1f;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #4a2a8a;
        }
    </style>
</head>
<body>

    <!-- ===== BACKGROUND ===== -->
    <div class="retro-bg"></div>

    <!-- ==================== HALAMAN 1 ==================== -->
    <div id="page1" class="page active">
        <div class="main-wrapper">
            <!-- ===== HERO ===== -->
            <header class="hero">
                <div class="badge">
                    <i class="fas fa-crown"></i> MEDIKOM · SMAN 2 JAKARTA
                </div>
                <img src="Logo MEDIKOM (1).png" alt="Logo MEDIKOM" class="hero-logo" />
                <h1 class="glow-title">
                    MEDIKOM<br class="hide-on-mobile" />
                    <span style="background:linear-gradient(135deg,#ff6bcd,#ffe74a);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">SMAN 2 JAKARTA</span>
                </h1>
                <p class="sub-glow">
                    <i class="fas fa-bolt"></i> SUB-ORGANISASI MEDIA INFORMASI & KOMUNIKASI · 2026 <i class="fas fa-bolt"></i>
                </p>
            </header>

            <!-- ===== NAVIGASI RETRO ===== -->
            <div class="nav-retro">
                <a href="#tentang">📖 Tentang</a>
                <a href="#profil">👤 Profil</a>
                <a href="#fasilitas">🛠️ Fasilitas</a>
                <a href="#divisi">📂 Divisi</a>
                <a href="#prestasi">🏆 Prestasi</a>
                <a href="#galeri">📸 Galeri</a>
                <a href="#video">🎬 Video</a>
                <a href="#kontak">📞 Kontak</a>
                <a href="#daftar" class="nav-daftar">📝 Daftar</a>
            </div>

            <!-- ===== TOMBOL "KLIK DI SINI" => pindah ke halaman2 ===== -->
            <div class="btn-wrapper">
                <button class="btn-klik" id="btnToPage2">
                    <i class="fas fa-rocket"></i> KLIK DI SINI
                </button>
            </div>

            <!-- ===== VISUAL EFFECTS ===== -->
            <h2 class="section-title">
                <i class="fas fa-eye"></i> VISUAL EFFECTS <i class="fas fa-star"></i>
            </h2>

            <div class="visual-effects" id="visualCanvasWrapper">
                <canvas id="effectCanvas"></canvas>
                <div class="overlay-text">
                    <i class="fas fa-bolt"></i>
                    MEDIKOM · RETRO WAVES
                    <i class="fas fa-bolt"></i>
                </div>
            </div>

            <!-- ===== MARQUEE ===== -->
            <div class="marquee-wrap">
                <div class="marquee-inner">
                    ✦ MEDIKOM SMAN 2 JAKARTA ✦ SUB-ORGANISASI MEDIA INFORMASI & KOMUNIKASI ✦ THE SOUND OF SMAN 2 JAKARTA ✦
                    ✦ MEDIKOM SMAN 2 JAKARTA ✦ SUB-ORGANISASI MEDIA INFORMASI & KOMUNIKASI ✦ THE SOUND OF SMAN 2 JAKARTA ✦
                </div>
            </div>

            <!-- ===== TENTANG KAMI ===== -->
            <section id="tentang">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label">📖 TENTANG KAMI</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-info-circle"></i> Apa itu MEDIKOM? <i class="fas fa-info-circle"></i>
                </h2>
                <div style="max-width:800px;margin:0 auto;text-align:center;">
                    <p style="font-size:1.05rem;color:#d4c4f0;line-height:1.9;">
                        <strong style="color:#ffe74a;">MEDIKOM SMAN 2 JAKARTA</strong> adalah sebuah Sub-Organisasi yang
                        memadukan nilai-nilai organisasi dengan teknologi modern untuk mengembangkan kreativitas, wawasan,
                        serta minat dan bakat siswa/i di bidang media, komunikasi, dan teknologi digital.
                    </p>
                </div>
            </section>

            <!-- ===== PROFIL ===== -->
            <section id="profil">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label">👤 PROFIL</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-user"></i> Pembina & Ketua <i class="fas fa-user"></i>
                </h2>
                <div class="row g-4" style="margin-top:10px;">
                    <div class="col-md-6">
                        <div class="profile-card">
                            <img src="IMG-20260624-WA0047.jpg" alt="Pembina MEDIKOM" />
                            <div class="profile-info">
                                <span class="role-badge pembina">PEMBINA</span>
                                <h4>Bpk. Dwi Chandra Kusworo</h4>
                                <p>Dedikasi tinggi dalam membangun pendidikan berkualitas, berkarakter, serta berorientasi pada perkembangan teknologi dan kreativitas siswa.</p>
                            </div>
                        </div>
                    </div>
                    <div class="col-md-6">
                        <div class="profile-card">
                            <img src="KETUA MEDIKOM SMAN 2 JAKARTA.jpg" alt="Ketua MEDIKOM" />
                            <div class="profile-info">
                                <span class="role-badge ketua">KETUA</span>
                                <h4>Calysta Aurellia</h4>
                                <p>Berperan aktif dalam mendukung pengelolaan Sub-Organisasi, meningkatkan kualitas program, serta mendorong prestasi dan karakter siswa.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ===== FASILITAS ===== -->
            <section id="fasilitas">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label">🛠️ FASILITAS</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-tools"></i> Fasilitas Dan Merchandise <i class="fas fa-tools"></i>
                </h2>
                <div class="collage-grid" id="divisiGrid">
                    <!-- Diisi oleh JS -->
                </div>
            </section>

            <!-- ===== DIVISI MEDIKOM ===== -->
            <section id="divisi">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label">📂 DIVISI KAMI</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-users"></i> 5 Divisi Unggulan MEDIKOM <i class="fas fa-users"></i>
                </h2>
                <div class="collage-grid">
                    <!-- Divisi 1: Fotografi -->
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(255,231,74,0.25), rgba(255,231,74,0.08));">
                        <div class="media"><img src="POSTER DIVISI FOTOGRAFI (1).png" alt="Divisi Fotografi" loading="lazy" /></div>
                        <div class="caption">Divisi Fotografi</div>
                        <div class="sub-caption" style="color:#ffe74a;">📸 Foto</div>
                        <div class="message" style="border-left-color:#ffe74a;">"Mengabadikan momen terbaik dengan teknik fotografi profesional."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.6rem; padding:4px 12px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI FOTOGRAFI (1).png">LIHAT KARTU</button>
                    </div>
                    <!-- Divisi 2: Sinematografi -->
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(227,0,11,0.25), rgba(227,0,11,0.08));">
                        <div class="media"><img src="POSTER DIVISI SINEMATOGRAFI  - Copy.png" alt="Divisi Cinema" loading="lazy" /></div>
                        <div class="caption">Divisi Sinematografi</div>
                        <div class="sub-caption" style="color:#e3000b;">🎬 Cinema</div>
                        <div class="message" style="border-left-color:#e3000b;">"Menghasilkan karya film pendek dan sinematik berkualitas tinggi."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.6rem; padding:4px 12px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI SINEMATOGRAFI  - Copy.png">LIHAT KARTU</button>
                    </div>
                    <!-- Divisi 3: Radio -->
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(0,109,183,0.25), rgba(0,109,183,0.08));">
                        <div class="media"><img src="POSTER DIVISI RADIO (1).png" alt="Divisi Radio" loading="lazy" /></div>
                        <div class="caption">Divisi Radio</div>
                        <div class="sub-caption" style="color:#006db7;">📻 Penyiaran</div>
                        <div class="message" style="border-left-color:#006db7;">"Mengelola program siaran radio sekolah yang informatif dan menghibur."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.6rem; padding:4px 12px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI RADIO (1).png">LIHAT KARTU</button>
                    </div>
                    <!-- Divisi 4: Mading & Desain -->
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(255,107,205,0.25), rgba(255,107,205,0.08));">
                        <div class="media"><img src="POSTER DIVISI MADES (1).png" alt="Divisi Mading & Desain" loading="lazy" /></div>
                        <div class="caption">Divisi Mading & Desain</div>
                        <div class="sub-caption" style="color:#ff6bcd;">📰 Kreativitas Visual</div>
                        <div class="message" style="border-left-color:#ff6bcd;">"Merancang mading sekolah dan materi desain grafis yang menarik."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.6rem; padding:4px 12px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI MADES (1).png">LIHAT KARTU</button>
                    </div>
                    <!-- Divisi 5: Jurnalistik -->
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(0,163,78,0.25), rgba(0,163,78,0.08));">
                        <div class="media"><img src="POSTER DIVISI JURNALISTIK.png" alt="Divisi Jurnalistik" loading="lazy" /></div>
                        <div class="caption">Divisi Jurnalistik</div>
                        <div class="sub-caption" style="color:#00a34e;">📰 Liputan & Berita</div>
                        <div class="message" style="border-left-color:#00a34e;">"Menyajikan informasi aktual dan terpercaya seputar kegiatan sekolah."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.6rem; padding:4px 12px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI JURNALISTIK.png">LIHAT KARTU</button>
                    </div>
                </div>
            </section>

            <!-- ===== PRESTASI (HANYA SATU) ===== -->
            <section id="prestasi">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label">🏆 PRESTASI</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-trophy"></i> Prestasi Terbaru <i class="fas fa-trophy"></i>
                </h2>
                <div class="prestasi-grid">
                    <!-- Hanya satu prestasi tersisa -->
                    <div class="prestasi-item">
                        <div class="icon-trophy"><i class="fas fa-medal"></i></div>
                        <h5>Pemenang Ide Cerita Film Pendek – Jakarta Youth Film Fund For Student 2026</h5>
                        <div class="desc">Penghargaan tingkat nasional dalam bidang ide cerita pembuatan film pendek yang akan dibuat film pendek dan akan didanai oleh Jakarta Youth Film Fund For Student 2026</div>
                        <button class="btn-lihat-sertifikat" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="WhatsApp Image 2026-07-06 at 09.24.27.jpeg">📜 Lihat lebih lanjut</button>
                    </div>
                    <div class="prestasi-item">
                        <div class="icon-trophy"><i class="fas fa-medal"></i></div>
                        <h5>Juara 1 – LENSA KOMPETISI PELAJAR JAKARTA YOUTH FILM FESTIVAL 2026</h5>
                        <div class="desc">Penghargaan tingkat nasional dalam bidang pembuatan film pendek yang diselenggarakan oleh LENSA KOMPETISI PELAJAR JAKARTA YOUTH FILM FESTIVAL 2026</div>
                        <button class="btn-lihat-sertifikat" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="WhatsApp Image 2026-07-06 .jpeg">📜 Lihat lebih lanjut</button>
                    </div>
                </div>
            </section>

            <!-- ===== GALERI (CAROUSEL) ===== -->
            <section id="galeri">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label">📸 GALERI</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-images"></i> Foto Kegiatan Kami <i class="fas fa-images"></i>
                </h2>
                <div class="row justify-content-center">
                    <div class="col-lg-8">
                        <div id="carouselExampleRide" class="carousel slide carousel-retro" data-bs-ride="carousel">
                            <div class="carousel-inner">
                                <div class="carousel-item active">
                                    <img src="Pendidikan Dan Pelatihan.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="3cd558fc-2abd-4b98-8e72-d794b3a34073.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="3d8487d2-1415-470c-8f68-699dcfe08ae6.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="265d417b-8cce-4942-9670-91b9b90fb507.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="1963e56a-f8e5-4e68-a036-b0014c01df08.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="7303bee8-60c6-4034-977f-98dbf780b723.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="222174f4-6f61-47ef-bc8d-7fe0e7c683d4.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="c1229e03-1845-4652-a150-5563862fd3bd.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="IMG_0238.jpeg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="IMG_5086.png" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="IMG-20251002-WA0044.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                                <div class="carousel-item">
                                    <img src="IMG-20251213-WA0070.jpg" class="d-block w-100" alt="Kegiatan Seru">
                                </div>
                            </div>
                            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleRide" data-bs-slide="prev">
                                <span class="carousel-control-prev-icon"></span>
                            </button>
                            <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleRide" data-bs-slide="next">
                                <span class="carousel-control-next-icon"></span>
                            </button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ===== VIDEO (DUA VIDEO: YOUTUBE & LOKAL) ===== -->
            <section id="video">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label">🎬 VIDEO</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-play-circle"></i> Video Kami <i class="fas fa-play-circle"></i>
                </h2>
                <div class="row justify-content-center g-4">
                    <!-- Video dari YouTube -->
                    <div class="col-md-6">
                        <div class="video-wrapper">
                            <div style="position:relative;width:100%;aspect-ratio:16/9;">
                                <iframe width="100%" height="100%"
                                src="https://www.youtube.com/embed/KC2GR4jNRHQ?si=oe-OVtgLDOhx3_Sz"
                                title="YouTube video player" frameborder="0"
                                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                                referrerpolicy="strict-origin-when-cross-origin" allowfullscreen
                                style="position:absolute;top:0;left:0;width:100%;height:100%;"></iframe>
                            </div>
                        </div>
                    </div>
                    <!-- Video dari penyimpanan lokal -->
                    <div class="col-md-6">
                        <div class="video-wrapper">
                            <video controls playsinline>
                                <source src="WhatsApp Video 2026-06-30 at 06.29.54.mp4" type="video/mp4">
                                Browser Anda tidak mendukung pemutaran video. Silakan <a href="WhatsApp Video 2026-06-30 at 06.29.54.mp4">unduh video</a>.
                            </video>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ===== PENDAFTARAN ===== -->
            <section id="daftar">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label" style="background:rgba(0,163,78,0.2);color:#00ff88;border-color:rgba(0,255,136,0.4);">📝 PENDAFTARAN</span>
                </div>
                <div class="daftar-section">
                    <div class="daftar-content">
                        <h2><i class="fas fa-user-plus"></i> AYOO GABUNG MEDIKOM! <i class="fas fa-user-plus"></i></h2>
                        <p>
                            Ingin menjadi bagian dari Sub-Organisasi Media & Teknologi Yang Merupakan Sub-Organisasi terkeren di SMAN 2 Jakarta?<br />
                            <strong style="color:#00ff88;">Daftarkan dirimu sekarang juga!</strong><br />
                           Jika kamu ingin mendapatkan pengalaman, keseruan, pengetahuan dan pertemanan yang luas. "JANGAN LUPA DAFTAR MEDIKOM YAWWW"
                        </p>
                        <p style="margin-top:18px;font-size:0.8rem;color:#a78bcb;">
                            <i class="fas fa-info-circle"></i> Kamu akan diberikan Google Forms · Pastikan data diisi dengan lengkap dan benar.
                        </p>
                         <h2>JANGAN LUPA GABUNG MEDIKOM YAAA!</i></h2>
                    </div>
                </div>
            </section>

            <!-- ===== KONTAK ===== -->
            <section id="kontak">
                <div style="text-align:center;margin-bottom:10px;">
                    <span class="section-label">📞 KONTAK</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-phone"></i> Hubungi Kami <i class="fas fa-phone"></i>
                </h2>
                <p style="text-align:center;max-width:600px;margin:0 auto 20px;color:#d4c4f0;">
                    Jika ada pertanyaan mengenai informasi tentang MEDIKOM SMAN 2 JAKARTA, silakan hubungi kami melalui kontak berikut.
                </p>
                <div class="collage-grid" style="grid-template-columns:repeat(auto-fit,minmax(150px,1fr));">
                    <a href="https://wa.me/6285694224134" target="_blank" class="contact-card">
                        <div class="icon-circle" style="background:rgba(37,211,102,0.2);color:#25D366;">💬</div>
                        <h5>WhatsApp</h5>
                        <p>+62 856-9422-4134</p>
                    </a>
                    <a href="https://instagram.com/medikomsmandu" target="_blank" class="contact-card">
                        <div class="icon-circle" style="background:rgba(225,48,108,0.2);color:#E1306C;">📷</div>
                        <h5>Instagram</h5>
                        <p>@medikomsmandu</p>
                    </a>
                    <a href="https://youtube.com/@medikomsman2jakarta?si=w1OKeB3u0zkZhBNt" target="_blank" class="contact-card">
                        <div class="icon-circle" style="background:rgba(24,119,242,0.2);color:#1877F2;">📘</div>
                        <h5>Youtube</h5>
                        <p>@medikomsman2jakarta</p>
                    </a>
                    <a href="https://wa.me/6285709309836" target="_blank" class="contact-card">
                        <div class="icon-circle" style="background:rgba(37,211,102,0.2);color:#25D366;">💬</div>
                        <h5>WhatsApp</h5>
                        <p>+62 857-0930-9836</p>
                    </a>
                </div>
            </section>

            <!-- ===== FOOTER ===== -->
            <footer class="footer">
                <i class="fas fa-crown"></i>
                MEDIKOM SMAN 2 JAKARTA · RETRO EDITION
                <i class="fas fa-crown"></i>
                <br />
                <span style="font-size:0.6rem;color:#4a2a6a;">
                    © 2026 <strong>MEDIKOM SMAN 2 JAKARTA</strong>. All Rights Reserved.
                    <br />Designed with Tim MEDIKOM SMAN 2 JAKARTA by Tim Website
                    (Frendy M., Kayzan N. A., Leonardo J. H., Cindy C., dan Raisa W.)
                </span>
            </footer>
        </div>
    </div>

    <!-- ==================== HALAMAN 2 : KARTU DIGITAL ==================== -->
    <div id="page2" class="page">
        <div class="digital-card">
            <img src="Logo MEDIKOM.png" alt="Logo MEDIKOM" class="card-logo" />
            <div class="card-title">MEDIKOM</div>
            <div class="card-subtitle">SMAN 2 JAKARTA</div>
            <div class="divider"></div>
            <p style="font-size:0.9rem; color:#d4c4f0; margin-bottom:20px;">
                Kartu Identitas Digital Resmi<br>Sub‑Organisasi Media & Teknologi
            </p>
            <div class="info-grid">
                <div class="info-item">
                    <i class="fas fa-user"></i>
                    <span class="label">Pembina</span>
                    <span class="value">Bpk. Dwi Chandra K.</span>
                </div>
                <div class="info-item">
                    <i class="fas fa-crown"></i>
                    <span class="label">Ketua</span>
                    <span class="value">Calysta Aurellia</span>
                </div>
                <div class="info-item">
                    <i class="fas fa-map-marker-alt"></i>
                    <span class="label">Lokasi</span>
                    <span class="value">SMAN 2 Jakarta</span>
                </div>
                <div class="info-item">
                    <i class="fas fa-calendar-alt"></i>
                    <span class="label">Tahun Aktif</span>
                    <span class="value">2004 / 2005</span>
                </div>
            </div>
            <div class="contact-row">
                <a href="https://wa.me/6285694224134" target="_blank" title="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                <a href="https://instagram.com/medikomsmandu" target="_blank" title="Instagram"><i class="fab fa-instagram"></i></a>
                <a href="https://youtube.com/@medikomsman2jakarta?si=w1OKeB3u0zkZhBNt" target="_blank" title="Youtube"><i class="fab fa-youtube"></i></a>
                <a href="https://wa.me/6285709309836" target="_blank" title="WhatsApp"><i class="fab fa-whatsapp"></i></a>
            </div>
            <button class="btn-back" id="btnBackToPage1"><i class="fas fa-arrow-left"></i> KEMBALI KE HALAMAN UTAMA</button>
            <div class="quote">
                <i class="fas fa-quote-left" style="opacity:0.5;"></i>
                Kreativitas Tanpa Batas — Setiap pengalaman adalah cerita.
                <i class="fas fa-quote-right" style="opacity:0.5;"></i>
            </div>
        </div>
    </div>

    <!-- ===== MODAL HANYA FOTO ===== -->
    <div class="modal fade" id="imageOnlyModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered">
            <div class="modal-content" style="background: transparent; border: none;">
                <div class="modal-body text-center p-0" style="position: relative;">
                    <button type="button" class="btn-close btn-close-white" data-bs-dismiss="modal" aria-label="Close" style="position: absolute; top: 10px; right: 15px; z-index: 10; filter: drop-shadow(0 0 5px rgba(255,255,255,0.5));"></button>
                    <img id="modalImageOnly" src="Logo MEDIKOM (1).png" alt="" class="modal-img-only">
                </div>
            </div>
        </div>
    </div>

    <!-- ===== SCRIPT ===== -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"
    integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI"
    crossorigin="anonymous">
    </script>

    <script>
        (function() {
            // ===== PARTIKEL LEGO =====
            const colors = ['#e3000b', '#f5cd1f', '#006db7', '#00a34e', '#ff6bcd', '#00f0ff', '#ffe74a'];
            for (let i = 0; i < 22; i++) {
                const el = document.createElement('div');
                el.className = 'lego-particle';
                const color = colors[Math.floor(Math.random() * colors.length)];
                el.style.background = color;
                el.style.color = color;
                el.style.width = (24 + Math.random() * 32) + 'px';
                el.style.height = (10 + Math.random() * 14) + 'px';
                el.style.left = Math.random() * 100 + '%';
                el.style.animationDuration = (12 + Math.random() * 20) + 's';
                el.style.animationDelay = (Math.random() * 18) + 's';
                document.body.appendChild(el);
            }

            // ===== CANVAS EFFECT =====
            const canvas = document.getElementById('effectCanvas');
            const wrapper = document.getElementById('visualCanvasWrapper');
            function resizeCanvas() {
                if (!canvas || !wrapper) return;
                const rect = wrapper.getBoundingClientRect();
                canvas.width = rect.width;
                canvas.height = rect.height;
            }
            if (canvas) {
                resizeCanvas();
                window.addEventListener('resize', resizeCanvas);
                const ctx = canvas.getContext('2d');
                let time = 0;
                function drawEffect() {
                    const w = canvas.width, h = canvas.height;
                    if (w === 0 || h === 0) {
                        requestAnimationFrame(drawEffect);
                        return;
                    }
                    ctx.clearRect(0, 0, w, h);
                    const grad = ctx.createRadialGradient(w * 0.5, h * 0.5, 0, w * 0.5, h * 0.5, w * 0.7);
                    grad.addColorStop(0, 'rgba(45, 27, 105, 0.25)');
                    grad.addColorStop(1, 'rgba(12, 5, 24, 0.4)');
                    ctx.fillStyle = grad;
                    ctx.fillRect(0, 0, w, h);
                    for (let wv = 0; wv < 4; wv++) {
                        ctx.beginPath();
                        const baseY = h * (0.2 + wv * 0.2);
                        const amp = 12 + wv * 6;
                        const freq = 0.02 + wv * 0.005;
                        const phase = time * 0.02 + wv * 1.2;
                        for (let x = 0; x <= w; x += 2) {
                            const y = baseY + Math.sin(x * freq + phase) * amp +
                                Math.sin(x * freq * 0.6 + phase * 1.3) * amp * 0.5;
                            if (x === 0) ctx.moveTo(x, y);
                            else ctx.lineTo(x, y);
                        }
                        ctx.strokeStyle = `rgba(255, 231, 74, ${0.12 + wv * 0.04})`;
                        ctx.lineWidth = 2 + wv * 0.8;
                        ctx.shadowColor = 'rgba(255, 107, 205, 0.3)';
                        ctx.shadowBlur = 20;
                        ctx.stroke();
                    }
                    for (let i = 0; i < 30; i++) {
                        const x = (Math.sin(i * 1.7 + time * 0.01) * 0.4 + 0.5) * w;
                        const y = (Math.cos(i * 2.3 + time * 0.015) * 0.35 + 0.5) * h;
                        const r = 2 + Math.sin(i + time * 0.02) * 1.5;
                        const alpha = 0.2 + Math.sin(i + time * 0.03) * 0.15 + 0.3;
                        ctx.beginPath();
                        ctx.arc(x, y, r, 0, Math.PI * 2);
                        const dotColors = ['#ffe74a', '#ff6bcd', '#00f0ff', '#f5cd1f'];
                        ctx.fillStyle = dotColors[i % dotColors.length] + Math.floor(alpha * 180).toString(16).padStart(2, '0');
                        ctx.shadowBlur = 15;
                        ctx.shadowColor = dotColors[i % dotColors.length] + '66';
                        ctx.fill();
                    }
                    time++;
                    requestAnimationFrame(drawEffect);
                }
                drawEffect();
            }

            // ===== DATA FASILITAS =====
            const fasilitasData = [
                { image: "RUANG MEDIKOM SMAN 2 JAKARTA.jpeg", name: "Ruangan Modern", date: "Fasilitas Utama", desc: "Ruang MEDIKOM yang nyaman dan modern." },
                { image: "Kamera.png", name: "Alat-Alat Digital", date: "Peralatan Profesional", desc: "peralatan digital profesional." },
                { image: "MEDIKOM GIBRAN.jpg", name: "ID Card Anggota", date: "Identitas Resmi", desc: "Kartu identitas resmi anggota MEDIKOM." },
                { image: "Beige Simplicity Mood Photo Collage.png", name: "Merchandise MEDIKOM", date: "Merchandise Eksklusif", desc: "Barang eksklusif sebagai merchandise khas." }
            ];
            const divisiGrid = document.getElementById("divisiGrid");
            if (divisiGrid) {
                fasilitasData.forEach(d => {
                    divisiGrid.innerHTML += `
                        <div class="collage-item">
                            <div class="media"><img src="${d.image}" alt="${d.name}" loading="lazy" /></div>
                            <div class="caption">${d.name}</div>
                            <div class="sub-caption">${d.date}</div>
                            <div class="message">"${d.desc}"</div>
                            <button class="btn btn-sm btn-klik" style="font-size:0.6rem; padding:4px 12px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="${d.image}">LIHAT KARTU</button>
                        </div>`;
                });
            }

            // ===== MODAL HANYA FOTO =====
            const imageModal = document.getElementById('imageOnlyModal');
            if (imageModal) {
                imageModal.addEventListener('show.bs.modal', function (event) {
                    const button = event.relatedTarget;
                    const imageSrc = button ? button.getAttribute('data-image') : null;
                    const imgElement = document.getElementById('modalImageOnly');
                    if (imgElement) {
                        imgElement.src = (imageSrc && imageSrc.trim() !== '') ? imageSrc : 'Logo MEDIKOM.png';
                    }
                });
            }

            // ===== TRANSISI HALAMAN =====
            const page1 = document.getElementById('page1');
            const page2 = document.getElementById('page2');
            const btnToPage2 = document.getElementById('btnToPage2');
            const btnBackToPage1 = document.getElementById('btnBackToPage1');

            if (btnToPage2) {
                btnToPage2.addEventListener('click', () => {
                    if (page1) page1.classList.remove('active');
                    if (page2) page2.classList.add('active');
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                });
            }
            if (btnBackToPage1) {
                btnBackToPage1.addEventListener('click', () => {
                    if (page2) page2.classList.remove('active');
                    if (page1) page1.classList.add('active');
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                });
            }

            console.log('🧱 MEDIKOM SMAN 2 JAKARTA · Siap dengan satu prestasi unggulan dan layout mobile yang lebih baik!');
        })();
    </script>
</body>
</html>
