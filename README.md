<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes" />
    <title>🧱 MEDIKOM SMAN 2 JAKARTA · Retro Edition</title>

    <!-- Font & Icons -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Quicksand:wght@400;600;700&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <!-- Bootstrap 5 untuk carousel & grid -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous" />

    <style>
        :root {
            --yellow: #f5cd1f;
            --yellow-bright: #ffe74a;
            --pink: #ff6bcd;
            --cyan: #00f0ff;
            --green: #00a34e;
            --green-bright: #00ff88;
            --purple-dark: #0c0518;
            --purple-mid: #2d1b69;
            --purple-light: #a78bcb;
            --text-soft: #d4c4f0;
            --radius-sm: 16px;
            --radius-md: 24px;
            --radius-lg: 32px;
            --shadow-glow-yellow: 0 0 20px rgba(245, 205, 31, 0.4);
            --shadow-glow-pink: 0 0 30px rgba(255, 107, 205, 0.3);
            --font-pixel: 'Press Start 2P', monospace;
            --font-body: 'Quicksand', sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--font-body);
            background: var(--purple-dark);
            color: #fff;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
            -webkit-tap-highlight-color: transparent;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        /* ===== RETRO BACKGROUND ===== */
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

        /* ===== FLOATING LEGO PARTICLES ===== */
        .lego-particle {
            position: fixed;
            width: 28px;
            height: 14px;
            border-radius: 3px 3px 2px 2px;
            opacity: 0.2;
            pointer-events: none;
            z-index: 1;
            animation: floatBrick linear infinite;
            box-shadow: inset 0 -3px 0 rgba(0, 0, 0, 0.2), 0 0 8px rgba(255, 255, 255, 0.04);
        }
        .lego-particle::before {
            content: '';
            position: absolute;
            top: -5px;
            left: 5px;
            width: 6px;
            height: 5px;
            background: inherit;
            border-radius: 2px 2px 0 0;
            box-shadow: 9px 0 0 0 currentColor;
            opacity: 0.5;
        }
        .lego-particle:nth-child(odd)::before {
            left: 8px;
            box-shadow: 11px 0 0 0 currentColor;
        }

        @keyframes floatBrick {
            0% {
                transform: translateY(110vh) rotate(0deg) scale(0.5);
                opacity: 0.06;
            }
            10% {
                opacity: 0.22;
            }
            90% {
                opacity: 0.22;
            }
            100% {
                transform: translateY(-10vh) rotate(720deg) scale(1.1);
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
            transition: opacity 0.55s ease, transform 0.55s ease;
            padding: 16px 12px;
        }
        .page.active {
            display: flex;
            opacity: 1;
            transform: translateY(0);
        }

        .main-wrapper {
            max-width: 1100px;
            margin: 0 auto;
            width: 100%;
            padding: 0 4px;
        }

        /* ===== HERO ===== */
        .hero {
            text-align: center;
            padding: 36px 8px 22px;
            position: relative;
        }
        .hero .badge {
            display: inline-block;
            background: var(--yellow);
            color: #1a0a2e;
            font-family: var(--font-pixel);
            font-size: 0.55rem;
            padding: 6px 14px;
            border-radius: 30px;
            letter-spacing: 1.5px;
            margin-bottom: 16px;
            box-shadow: var(--shadow-glow-yellow);
            text-transform: uppercase;
            line-height: 1.5;
        }
        .glow-title {
            font-family: var(--font-pixel);
            font-size: clamp(1.6rem, 7vw, 4rem);
            line-height: 1.25;
            background: linear-gradient(135deg, #ffe74a, #ff6bcd, #00f0ff, #ffe74a);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 4s ease-in-out infinite, glowPulse 2s ease-in-out infinite alternate;
            text-shadow: 0 0 40px rgba(255, 107, 205, 0.3);
            filter: drop-shadow(0 0 30px rgba(255, 107, 205, 0.2));
            letter-spacing: 1.5px;
            word-break: break-word;
            margin-bottom: 8px;
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
                filter: drop-shadow(0 0 16px rgba(255, 107, 205, 0.2)) drop-shadow(0 0 30px rgba(0, 240, 255, 0.1));
            }
            100% {
                filter: drop-shadow(0 0 32px rgba(255, 107, 205, 0.45)) drop-shadow(0 0 60px rgba(0, 240, 255, 0.25));
            }
        }
        .sub-glow {
            font-family: var(--font-pixel);
            font-size: clamp(0.5rem, 1.5vw, 0.85rem);
            color: var(--purple-light);
            margin-top: 12px;
            letter-spacing: 2px;
            text-shadow: 0 0 16px rgba(167, 139, 203, 0.25);
            animation: flicker 3s infinite alternate;
            line-height: 1.6;
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

        /* Hero Logo */
        .hero-logo {
            max-width: min(160px, 40vw);
            border-radius: 20px;
            box-shadow: 0 0 30px rgba(245, 205, 31, 0.3), 0 0 50px rgba(255, 107, 205, 0.2);
            margin: 10px 0 16px;
            animation: floatLogo 3s ease-in-out infinite;
            display: inline-block;
        }
        @keyframes floatLogo {
            0%,
            100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        /* ===== TOMBOL "KLIK DI SINI" ===== */
        .btn-wrapper {
            text-align: center;
            margin: 28px 0 36px;
        }
        .btn-klik {
            position: relative;
            display: inline-block;
            padding: 16px 36px;
            font-family: var(--font-pixel);
            font-size: clamp(0.8rem, 2.2vw, 1.4rem);
            font-weight: 700;
            color: #1a0a2e;
            background: linear-gradient(135deg, #ffe74a, #f5cd1f);
            border: none;
            border-radius: 16px;
            cursor: pointer;
            box-shadow: 0 0 0 3px #1a0a2e, 0 0 0 6px #f5cd1f, 0 0 30px rgba(245, 205, 31, 0.45);
            transition: all 0.25s ease;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            z-index: 5;
            text-decoration: none;
            touch-action: manipulation;
            -webkit-user-select: none;
            user-select: none;
            white-space: nowrap;
        }
        .btn-klik:hover {
            transform: scale(1.06) translateY(-3px);
            box-shadow: 0 0 0 3px #1a0a2e, 0 0 0 6px #ffe74a, 0 0 50px rgba(245, 205, 31, 0.7), 0 16px 32px rgba(0, 0, 0, 0.35);
        }
        .btn-klik:active {
            transform: scale(0.95);
            transition: transform 0.1s ease;
        }
        .btn-klik .fa {
            margin-right: 10px;
        }

        /* ===== SECTION TITLE ===== */
        .section-title {
            font-family: var(--font-pixel);
            font-size: clamp(0.85rem, 2.2vw, 1.6rem);
            text-align: center;
            margin: 40px 0 22px;
            color: var(--yellow-bright);
            text-shadow: 0 0 20px rgba(255, 231, 74, 0.15);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
            line-height: 1.5;
        }
        .section-title .fa {
            color: var(--pink);
            font-size: 1.3rem;
        }
        .section-label {
            display: inline-block;
            background: rgba(245, 205, 31, 0.12);
            color: var(--yellow-bright);
            font-family: var(--font-pixel);
            font-size: 0.5rem;
            padding: 5px 12px;
            border-radius: 30px;
            letter-spacing: 1.5px;
            text-transform: uppercase;
            margin-bottom: 8px;
            border: 1px solid rgba(245, 205, 31, 0.25);
            line-height: 1.6;
        }

        /* ===== VISUAL EFFECTS CANVAS ===== */
        .visual-effects {
            background: rgba(45, 27, 105, 0.35);
            border-radius: var(--radius-md);
            padding: 20px 12px;
            border: 2px solid rgba(245, 205, 31, 0.18);
            margin-bottom: 32px;
            backdrop-filter: blur(3px);
            position: relative;
            overflow: hidden;
            min-height: 140px;
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
            border-radius: var(--radius-md);
            pointer-events: none;
        }
        .visual-effects .overlay-text {
            position: relative;
            z-index: 2;
            font-family: var(--font-pixel);
            font-size: clamp(0.7rem, 1.6vw, 1.2rem);
            color: #fff;
            text-shadow: 0 0 20px rgba(255, 107, 205, 0.4), 0 0 40px rgba(0, 240, 255, 0.2);
            animation: pulseText 2s infinite alternate;
            text-align: center;
            padding: 8px;
            line-height: 1.5;
        }
        .visual-effects .overlay-text .fa {
            color: var(--yellow-bright);
            margin: 0 6px;
        }
        @keyframes pulseText {
            0% {
                opacity: 0.7;
                transform: scale(0.98);
            }
            100% {
                opacity: 1;
                transform: scale(1.03);
            }
        }

        /* ===== COLLAGE GRID ===== */
        .collage-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 14px;
            margin-top: 16px;
        }
        .collage-item {
            background: rgba(45, 27, 105, 0.3);
            border-radius: 18px;
            padding: 14px 10px;
            border: 2px solid rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(3px);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            word-break: break-word;
        }
        .collage-item:hover {
            transform: translateY(-6px);
            border-color: var(--yellow);
            box-shadow: 0 10px 30px rgba(245, 205, 31, 0.12);
        }
        .collage-item .media {
            width: 100%;
            aspect-ratio: 1/1;
            border-radius: 12px;
            overflow: hidden;
            background: #1a0a2e;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.2rem;
            color: var(--purple-light);
        }
        .collage-item .media img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .collage-item .caption {
            font-weight: 700;
            font-size: 0.85rem;
            color: var(--text-soft);
            margin-bottom: 3px;
        }
        .collage-item .sub-caption {
            font-size: 0.7rem;
            color: var(--purple-light);
        }
        .collage-item .message {
            font-size: 0.78rem;
            color: var(--yellow-bright);
            margin-top: 8px;
            padding: 8px 10px;
            background: rgba(245, 205, 31, 0.06);
            border-radius: 24px;
            width: 100%;
            border-left: 3px solid var(--yellow);
        }

        /* ===== PROFILE CARD ===== */
        .profile-card {
            display: flex;
            flex-wrap: wrap;
            gap: 16px;
            align-items: center;
            background: rgba(45, 27, 105, 0.3);
            border-radius: 18px;
            padding: 20px 14px;
            border: 2px solid rgba(255, 255, 255, 0.06);
            backdrop-filter: blur(3px);
            margin-bottom: 14px;
            transition: all 0.3s ease;
        }
        .profile-card:hover {
            border-color: var(--yellow);
            box-shadow: 0 10px 30px rgba(245, 205, 31, 0.08);
            transform: translateY(-3px);
        }
        .profile-card img {
            width: 110px;
            height: 130px;
            object-fit: cover;
            border-radius: 14px;
            flex-shrink: 0;
            border: 3px solid rgba(245, 205, 31, 0.25);
        }
        .profile-card .profile-info {
            flex: 1 1 200px;
        }
        .profile-card .profile-info h4 {
            font-family: var(--font-pixel);
            font-size: 0.7rem;
            color: var(--yellow-bright);
            margin-bottom: 4px;
            line-height: 1.4;
        }
        .profile-card .profile-info .role-badge {
            display: inline-block;
            font-size: 0.5rem;
            font-family: var(--font-pixel);
            padding: 4px 10px;
            border-radius: 30px;
            margin-bottom: 6px;
            letter-spacing: 1px;
        }
        .role-badge.pembina {
            background: rgba(0, 240, 255, 0.18);
            color: var(--cyan);
        }
        .role-badge.ketua {
            background: rgba(255, 107, 205, 0.18);
            color: var(--pink);
        }
        .profile-card .profile-info p {
            font-size: 0.82rem;
            color: var(--text-soft);
            line-height: 1.6;
        }

        /* ===== PRESTASI GRID ===== */
        .prestasi-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 18px;
            margin-top: 16px;
            justify-content: center;
        }
        .prestasi-item {
            background: linear-gradient(145deg, rgba(45, 27, 105, 0.45), rgba(26, 10, 46, 0.55));
            border: 2px solid rgba(245, 205, 31, 0.22);
            border-radius: 22px;
            padding: 22px 14px;
            text-align: center;
            backdrop-filter: blur(5px);
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
            top: -16px;
            right: -16px;
            width: 60px;
            height: 60px;
            background: radial-gradient(circle, rgba(245, 205, 31, 0.25) 0%, transparent 70%);
            border-radius: 50%;
            z-index: 0;
            transition: 0.3s;
        }
        .prestasi-item:hover::before {
            width: 100px;
            height: 100px;
            top: -24px;
            right: -24px;
        }
        .prestasi-item:hover {
            transform: translateY(-6px);
            border-color: var(--yellow);
            box-shadow: 0 14px 35px rgba(245, 205, 31, 0.2);
        }
        .prestasi-item .icon-trophy {
            font-size: 2.2rem;
            color: var(--yellow);
            margin-bottom: 8px;
            filter: drop-shadow(0 0 10px rgba(245, 205, 31, 0.4));
            z-index: 1;
            position: relative;
        }
        .prestasi-item h5 {
            font-family: var(--font-pixel);
            font-size: 0.62rem;
            color: var(--yellow-bright);
            margin-bottom: 6px;
            z-index: 1;
            position: relative;
            line-height: 1.4;
            max-width: 100%;
        }
        .prestasi-item .desc {
            font-size: 0.78rem;
            color: var(--text-soft);
            margin-bottom: 14px;
            z-index: 1;
            position: relative;
            line-height: 1.5;
        }
        .prestasi-item .btn-lihat-sertifikat {
            font-family: var(--font-pixel);
            font-size: 0.48rem;
            padding: 7px 14px;
            background: transparent;
            border: 2px solid var(--yellow);
            color: var(--yellow);
            border-radius: 30px;
            cursor: pointer;
            transition: 0.3s;
            z-index: 1;
            position: relative;
            letter-spacing: 1px;
            text-transform: uppercase;
            white-space: nowrap;
            touch-action: manipulation;
        }
        .prestasi-item .btn-lihat-sertifikat:hover {
            background: var(--yellow);
            color: #1a0a2e;
            box-shadow: 0 0 20px rgba(245, 205, 31, 0.6);
        }

        /* ===== CAROUSEL ===== */
        .carousel-retro {
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 0 40px rgba(245, 205, 31, 0.12);
            border: 2px solid rgba(245, 205, 31, 0.18);
        }
        .carousel-retro .carousel-item img {
            height: auto;
            max-height: 320px;
            object-fit: cover;
            width: 100%;
        }
        .carousel-retro .carousel-control-prev-icon,
        .carousel-retro .carousel-control-next-icon {
            background-color: rgba(245, 205, 31, 0.65);
            border-radius: 50%;
            padding: 16px;
            box-shadow: 0 0 16px rgba(245, 205, 31, 0.35);
        }

        /* ===== VIDEO WRAPPER ===== */
        .video-wrapper {
            border: 2px solid rgba(245, 205, 31, 0.18);
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 0 40px rgba(245, 205, 31, 0.08);
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
            aspect-ratio: 16/9;
        }
        .video-wrapper video,
        .video-wrapper iframe {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            border: none;
        }

        /* ===== CONTACT CARD ===== */
        .contact-card {
            background: rgba(45, 27, 105, 0.3);
            border: 2px solid rgba(255, 255, 255, 0.05);
            border-radius: 16px;
            padding: 18px 12px;
            text-align: center;
            transition: all 0.3s;
            backdrop-filter: blur(3px);
            text-decoration: none;
            color: inherit;
            display: block;
            height: 100%;
            touch-action: manipulation;
        }
        .contact-card:hover {
            transform: translateY(-4px);
            border-color: var(--yellow);
            box-shadow: 0 10px 30px rgba(245, 205, 31, 0.12);
        }
        .contact-card .icon-circle {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 10px;
            font-size: 1.1rem;
        }
        .contact-card h5 {
            font-weight: 700;
            font-size: 0.9rem;
            margin-bottom: 3px;
            color: var(--yellow-bright);
        }
        .contact-card p {
            font-size: 0.72rem;
            color: var(--text-soft);
            margin: 0;
            word-break: break-all;
        }

        /* ===== MARQUEE ===== */
        .marquee-wrap {
            background: rgba(245, 205, 31, 0.08);
            border-top: 1px solid rgba(245, 205, 31, 0.18);
            border-bottom: 1px solid rgba(245, 205, 31, 0.18);
            color: var(--yellow-bright);
            padding: 8px 0;
            overflow: hidden;
            white-space: nowrap;
            font-weight: 700;
            letter-spacing: 2px;
            font-size: 0.6rem;
            text-transform: uppercase;
            font-family: var(--font-pixel);
            margin: 16px 0;
        }
        .marquee-wrap .marquee-inner {
            display: inline-block;
            animation: marqueeScroll 22s linear infinite;
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
            gap: 5px;
            margin: 16px 0;
        }
        .nav-retro a {
            font-family: var(--font-pixel);
            font-size: 0.45rem;
            color: var(--text-soft);
            text-decoration: none;
            padding: 7px 10px;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.08);
            transition: all 0.25s;
            letter-spacing: 0.8px;
            background: rgba(45, 27, 105, 0.25);
            white-space: nowrap;
            touch-action: manipulation;
        }
        .nav-retro a:hover {
            color: var(--yellow-bright);
            border-color: var(--yellow);
            box-shadow: 0 0 14px rgba(245, 205, 31, 0.18);
            background: rgba(245, 205, 31, 0.08);
        }
        .nav-retro a.nav-daftar {
            background: rgba(0, 163, 78, 0.25);
            border-color: var(--green);
            color: var(--green-bright);
            animation: pulseDaftar 2s infinite;
        }
        .nav-retro a.nav-daftar:hover {
            background: var(--green);
            color: #fff;
            border-color: var(--green-bright);
            box-shadow: 0 0 20px rgba(0, 255, 136, 0.35);
        }
        @keyframes pulseDaftar {
            0%,
            100% {
                box-shadow: 0 0 6px rgba(0, 163, 78, 0.25);
            }
            50% {
                box-shadow: 0 0 16px rgba(0, 255, 136, 0.5);
            }
        }

        /* ===== FLOATING DAFTAR BUTTON ===== */
        .floating-daftar {
            position: fixed;
            bottom: 20px;
            right: 16px;
            z-index: 100;
            font-family: var(--font-pixel);
            font-size: 0.5rem;
            padding: 12px 16px;
            background: linear-gradient(135deg, #00a34e, #00cc5f);
            color: #fff;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 6px 22px rgba(0, 163, 78, 0.45), 0 0 0 2px #1a0a2e, 0 0 0 5px rgba(0, 255, 136, 0.25);
            transition: all 0.3s ease;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
            letter-spacing: 1px;
            animation: bounceFloat 2s ease-in-out infinite;
            touch-action: manipulation;
            -webkit-tap-highlight-color: transparent;
        }
        .floating-daftar:hover {
            transform: translateY(-5px) scale(1.04);
            box-shadow: 0 12px 35px rgba(0, 255, 136, 0.55), 0 0 0 2px #1a0a2e, 0 0 0 5px #00ff88;
            color: #fff;
            background: linear-gradient(135deg, #00cc5f, #00ff88);
        }
        .floating-daftar .fa {
            font-size: 1rem;
            animation: spinIcon 3s linear infinite;
        }
        @keyframes bounceFloat {
            0%,
            100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-8px);
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
            background: linear-gradient(135deg, rgba(0, 163, 78, 0.18), rgba(0, 255, 136, 0.06));
            border: 2px solid rgba(0, 163, 78, 0.4);
            border-radius: var(--radius-lg);
            padding: 28px 16px;
            text-align: center;
            margin: 32px 0;
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(3px);
            box-shadow: 0 0 40px rgba(0, 163, 78, 0.15);
        }
        .daftar-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(0, 255, 136, 0.08), transparent, rgba(0, 255, 136, 0.08), transparent);
            animation: rotateDaftar 10s linear infinite;
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
            font-family: var(--font-pixel);
            font-size: clamp(1rem, 2.6vw, 1.7rem);
            color: var(--green-bright);
            text-shadow: 0 0 20px rgba(0, 255, 136, 0.3);
            margin-bottom: 12px;
            line-height: 1.4;
        }
        .daftar-section p {
            color: var(--text-soft);
            font-size: 0.88rem;
            margin-bottom: 18px;
            line-height: 1.7;
        }
        .daftar-section .btn-daftar-besar {
            display: inline-block;
            font-family: var(--font-pixel);
            font-size: clamp(0.65rem, 1.6vw, 1rem);
            padding: 15px 32px;
            background: linear-gradient(135deg, #00a34e, #00cc5f);
            color: #fff;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            text-decoration: none;
            letter-spacing: 1.5px;
            box-shadow: 0 0 20px rgba(0, 255, 136, 0.3), 0 0 0 3px #1a0a2e, 0 0 0 6px rgba(0, 255, 136, 0.25);
            transition: all 0.3s ease;
            animation: pulseDaftarBig 2s infinite;
            touch-action: manipulation;
            white-space: nowrap;
        }
        .daftar-section .btn-daftar-besar:hover {
            transform: scale(1.05) translateY(-3px);
            box-shadow: 0 0 40px rgba(0, 255, 136, 0.6), 0 0 0 3px #1a0a2e, 0 0 0 6px #00ff88;
            background: linear-gradient(135deg, #00cc5f, #00ff88);
            color: #1a0a2e;
        }
        @keyframes pulseDaftarBig {
            0%,
            100% {
                box-shadow: 0 0 20px rgba(0, 255, 136, 0.3), 0 0 0 3px #1a0a2e, 0 0 0 6px rgba(0, 255, 136, 0.25);
            }
            50% {
                box-shadow: 0 0 40px rgba(0, 255, 136, 0.6), 0 0 0 3px #1a0a2e, 0 0 0 6px #00ff88;
            }
        }

        /* ===== FOOTER ===== */
        .footer {
            margin-top: 40px;
            text-align: center;
            font-size: 0.55rem;
            color: #6a4f8a;
            font-family: var(--font-pixel);
            letter-spacing: 1px;
            border-top: 1px solid rgba(255, 255, 255, 0.03);
            padding-top: 24px;
            line-height: 1.8;
        }
        .footer .fa {
            color: var(--pink);
        }

        /* ===== HALAMAN 2 : KARTU DIGITAL ===== */
        .digital-card {
            width: 92%;
            max-width: 440px;
            background: linear-gradient(145deg, #2d1b69, #1a0a2e);
            border: 3px solid var(--yellow);
            border-radius: var(--radius-lg);
            padding: 28px 18px;
            text-align: center;
            box-shadow: 0 0 60px rgba(245, 205, 31, 0.2), 0 16px 45px rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(8px);
            animation: popIn 0.55s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            margin: 16px;
        }
        @keyframes popIn {
            0% {
                opacity: 0;
                transform: scale(0.65) rotate(-5deg);
            }
            100% {
                opacity: 1;
                transform: scale(1) rotate(0deg);
            }
        }
        .card-logo {
            width: 65px;
            height: 65px;
            object-fit: contain;
            border-radius: 16px;
            margin: 0 auto 16px;
            display: block;
            border: 2px solid var(--yellow);
            box-shadow: 0 0 20px rgba(245, 205, 31, 0.35);
            animation: floatLogo 3s ease-in-out infinite;
        }
        .card-title {
            font-family: var(--font-pixel);
            font-size: 1rem;
            background: linear-gradient(135deg, #ffe74a, #ff6bcd);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 6px;
            letter-spacing: 1.5px;
        }
        .card-subtitle {
            font-family: var(--font-pixel);
            font-size: 0.5rem;
            color: var(--purple-light);
            margin-bottom: 14px;
            letter-spacing: 1.5px;
        }
        .divider {
            width: 60px;
            height: 2px;
            background: var(--yellow);
            margin: 12px auto;
            border-radius: 2px;
        }
        .info-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin: 16px 0;
            text-align: left;
        }
        .info-item {
            background: rgba(255, 255, 255, 0.04);
            border-radius: 10px;
            padding: 8px;
            border: 1px solid rgba(245, 205, 31, 0.18);
            transition: all 0.3s;
            word-break: break-word;
        }
        .info-item:hover {
            border-color: var(--yellow);
            box-shadow: 0 0 12px rgba(245, 205, 31, 0.15);
            transform: translateY(-2px);
        }
        .info-item i {
            color: var(--pink);
            margin-right: 4px;
            font-size: 0.85rem;
        }
        .info-item .label {
            font-weight: 600;
            font-size: 0.65rem;
            color: var(--yellow-bright);
            display: block;
            margin-bottom: 3px;
        }
        .info-item .value {
            font-size: 0.78rem;
            color: var(--text-soft);
        }
        .contact-row {
            display: flex;
            justify-content: center;
            gap: 14px;
            margin: 20px 0 12px;
            flex-wrap: wrap;
        }
        .contact-row a {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.04);
            border: 2px solid rgba(245, 205, 31, 0.25);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            font-size: 1.2rem;
            text-decoration: none;
            transition: all 0.3s;
            touch-action: manipulation;
        }
        .contact-row a:hover {
            background: var(--yellow);
            color: #1a0a2e;
            border-color: var(--yellow);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(245, 205, 31, 0.35);
        }
        .btn-back {
            display: inline-block;
            margin-top: 10px;
            padding: 10px 22px;
            font-family: var(--font-pixel);
            font-size: 0.55rem;
            background: var(--pink);
            color: #1a0a2e;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s;
            box-shadow: 0 0 16px rgba(255, 107, 205, 0.35);
            touch-action: manipulation;
        }
        .btn-back:hover {
            background: var(--yellow-bright);
            transform: scale(1.04);
            box-shadow: 0 0 30px rgba(255, 231, 74, 0.45);
        }
        .btn-daftar-card {
            display: inline-block;
            margin: 8px 6px;
            padding: 8px 16px;
            font-family: var(--font-pixel);
            font-size: 0.48rem;
            background: linear-gradient(135deg, #00a34e, #00cc5f);
            color: #fff;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s;
            box-shadow: 0 0 12px rgba(0, 255, 136, 0.3);
            letter-spacing: 0.8px;
            touch-action: manipulation;
        }
        .btn-daftar-card:hover {
            background: var(--green-bright);
            color: #1a0a2e;
            transform: scale(1.04);
            box-shadow: 0 0 22px rgba(0, 255, 136, 0.5);
        }
        .quote {
            font-style: italic;
            color: var(--purple-light);
            margin-top: 14px;
            font-size: 0.7rem;
            line-height: 1.5;
        }

        /* ===== MODAL STYLE ===== */
        .modal-content {
            background-color: transparent !important;
            border: none !important;
        }
        .modal-backdrop.show {
            opacity: 0.85;
            background-color: #0c0518;
        }
        .modal-img-only {
            max-width: 92vw;
            max-height: 82vh;
            border-radius: 18px;
            border: 3px solid var(--yellow);
            box-shadow: 0 0 50px rgba(245, 205, 31, 0.35), 0 0 100px rgba(255, 107, 205, 0.18);
            object-fit: contain;
            animation: popIn 0.45s ease;
        }

        /* ===== SCROLLBAR ===== */
        ::-webkit-scrollbar {
            width: 5px;
        }
        ::-webkit-scrollbar-track {
            background: #0c0518;
        }
        ::-webkit-scrollbar-thumb {
            background: #2d1b69;
            border-radius: 10px;
            border: 1px solid var(--yellow);
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #4a2a8a;
        }

        /* ===== RESPONSIVE ENHANCEMENTS ===== */
        @media (max-width: 768px) {
            .page {
                padding: 10px 6px;
            }
            .hero {
                padding: 24px 4px 14px;
            }
            .hero .badge {
                font-size: 0.45rem;
                padding: 5px 10px;
                letter-spacing: 1px;
            }
            .glow-title {
                font-size: clamp(1.4rem, 6vw, 2.6rem);
                letter-spacing: 1px;
            }
            .sub-glow {
                font-size: 0.48rem;
                letter-spacing: 1px;
            }
            .btn-klik {
                padding: 14px 26px;
                font-size: 0.7rem;
                letter-spacing: 1px;
                border-radius: 14px;
                box-shadow: 0 0 0 2px #1a0a2e, 0 0 0 5px #f5cd1f, 0 0 24px rgba(245, 205, 31, 0.4);
            }
            .btn-klik .fa {
                margin-right: 6px;
            }
            .visual-effects {
                min-height: 120px;
                padding: 14px 8px;
                border-radius: 18px;
            }
            .visual-effects .overlay-text {
                font-size: 0.6rem;
            }
            .collage-grid {
                grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
                gap: 10px;
            }
            .collage-item {
                padding: 10px 8px;
                border-radius: 14px;
            }
            .collage-item .media {
                border-radius: 10px;
                font-size: 1.8rem;
            }
            .collage-item .caption {
                font-size: 0.75rem;
            }
            .collage-item .sub-caption {
                font-size: 0.62rem;
            }
            .collage-item .message {
                font-size: 0.68rem;
                padding: 6px 8px;
            }
            .profile-card {
                flex-direction: column;
                text-align: center;
                padding: 16px 10px;
                gap: 10px;
            }
            .profile-card img {
                width: 90px;
                height: 105px;
                margin: 0 auto;
                border-radius: 12px;
            }
            .profile-card .profile-info h4 {
                font-size: 0.6rem;
            }
            .profile-card .profile-info p {
                font-size: 0.74rem;
            }
            .section-title {
                font-size: 0.75rem;
                gap: 8px;
                margin: 28px 0 14px;
            }
            .section-title .fa {
                font-size: 1.1rem;
            }
            .section-label {
                font-size: 0.42rem;
                padding: 4px 10px;
            }
            .nav-retro a {
                font-size: 0.4rem;
                padding: 5px 8px;
                letter-spacing: 0.5px;
            }
            .prestasi-grid {
                grid-template-columns: 1fr;
                gap: 14px;
            }
            .prestasi-item {
                padding: 18px 12px;
                border-radius: 18px;
            }
            .prestasi-item h5 {
                font-size: 0.55rem;
            }
            .prestasi-item .btn-lihat-sertifikat {
                font-size: 0.42rem;
                padding: 6px 10px;
            }
            .carousel-retro .carousel-item img {
                max-height: 220px;
            }
            .carousel-retro .carousel-control-prev-icon,
            .carousel-retro .carousel-control-next-icon {
                padding: 12px;
            }
            .daftar-section {
                padding: 22px 12px;
                border-radius: 22px;
            }
            .daftar-section h2 {
                font-size: 0.85rem;
            }
            .daftar-section p {
                font-size: 0.76rem;
            }
            .daftar-section .btn-daftar-besar {
                padding: 12px 22px;
                font-size: 0.58rem;
            }
            .floating-daftar {
                bottom: 14px;
                right: 10px;
                font-size: 0.42rem;
                padding: 10px 14px;
                gap: 5px;
            }
            .floating-daftar .fa {
                font-size: 0.8rem;
            }
            .contact-card {
                padding: 14px 8px;
                border-radius: 14px;
            }
            .contact-card .icon-circle {
                width: 36px;
                height: 36px;
                font-size: 0.9rem;
            }
            .contact-card h5 {
                font-size: 0.78rem;
            }
            .contact-card p {
                font-size: 0.65rem;
            }
            .digital-card {
                padding: 20px 12px;
                border-radius: 24px;
                width: 95%;
                margin: 10px;
            }
            .card-logo {
                width: 50px;
                height: 50px;
            }
            .card-title {
                font-size: 0.85rem;
            }
            .card-subtitle {
                font-size: 0.42rem;
            }
            .info-grid {
                gap: 7px;
            }
            .info-item .label {
                font-size: 0.55rem;
            }
            .info-item .value {
                font-size: 0.68rem;
            }
            .btn-back {
                font-size: 0.48rem;
                padding: 8px 16px;
            }
            .footer {
                font-size: 0.45rem;
            }
            .marquee-wrap {
                font-size: 0.48rem;
                letter-spacing: 1px;
            }
            .video-wrapper {
                border-radius: 12px;
            }
        }

        @media (max-width: 400px) {
            .glow-title {
                font-size: 1.2rem;
                letter-spacing: 0.5px;
            }
            .btn-klik {
                padding: 12px 18px;
                font-size: 0.6rem;
                border-radius: 12px;
            }
            .collage-grid {
                grid-template-columns: 1fr 1fr;
                gap: 8px;
            }
            .prestasi-item h5 {
                font-size: 0.5rem;
            }
            .nav-retro {
                gap: 3px;
            }
            .nav-retro a {
                font-size: 0.35rem;
                padding: 4px 6px;
            }
            .digital-card {
                padding: 16px 8px;
                border-radius: 20px;
            }
            .info-grid {
                grid-template-columns: 1fr;
                gap: 6px;
            }
            .contact-row {
                gap: 8px;
            }
            .contact-row a {
                width: 36px;
                height: 36px;
                font-size: 1rem;
            }
            .floating-daftar {
                bottom: 10px;
                right: 6px;
                font-size: 0.38rem;
                padding: 8px 10px;
            }
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
                <img src="Logo MEDIKOM (1).png" alt="Logo MEDIKOM" class="hero-logo" loading="eager" />
                <h1 class="glow-title">
                    MEDIKOM<br />
                    <span style="background:linear-gradient(135deg,#ff6bcd,#ffe74a);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">SMAN 2 JAKARTA</span>
                </h1>
                <p class="sub-glow">
                    <i class="fas fa-bolt"></i> SUB-ORGANISASI MEDIA INFORMASI & KOMUNIKASI · 2026 <i class="fas fa-bolt"></i>
                </p>
            </header>

            <!-- ===== NAVIGASI RETRO ===== -->
            <nav class="nav-retro" aria-label="Navigasi utama">
                <a href="#tentang">📖 Tentang</a>
                <a href="#profil">👤 Profil</a>
                <a href="#fasilitas">🛠️ Fasilitas</a>
                <a href="#divisi">📂 Divisi</a>
                <a href="#prestasi">🏆 Prestasi</a>
                <a href="#galeri">📸 Galeri</a>
                <a href="#video">🎬 Video</a>
                <a href="#kontak">📞 Kontak</a>
                <a href="#daftar" class="nav-daftar">📝 Daftar</a>
            </nav>

            <!-- ===== TOMBOL "KLIK DI SINI" ===== -->
            <div class="btn-wrapper">
                <button class="btn-klik" id="btnToPage2" aria-label="Buka kartu digital MEDIKOM">
                    <i class="fas fa-rocket"></i> KLIK DI SINI
                </button>
            </div>

            <!-- ===== VISUAL EFFECTS ===== -->
            <h2 class="section-title">
                <i class=""></i> VISUAL EFFECTS <i class=""></i>
            </h2>
            <div class="visual-effects" id="visualCanvasWrapper">
                <canvas id="effectCanvas" aria-hidden="true"></canvas>
                <div class="overlay-text">
                    <i class="fas fa-bolt"></i> MEDIKOM · RETRO WAVES <i class="fas fa-bolt"></i>
                </div>
            </div>

            <!-- ===== MARQUEE ===== -->
            <div class="marquee-wrap" aria-hidden="true">
                <div class="marquee-inner">
                    ✦ MEDIKOM SMAN 2 JAKARTA ✦ SUB-ORGANISASI MEDIA INFORMASI & KOMUNIKASI ✦ THE SOUND OF SMAN 2 JAKARTA ✦
                    ✦ MEDIKOM SMAN 2 JAKARTA ✦ SUB-ORGANISASI MEDIA INFORMASI & KOMUNIKASI ✦ THE SOUND OF SMAN 2 JAKARTA ✦
                </div>
            </div>

            <!-- ===== TENTANG KAMI ===== -->
            <section id="tentang">
                <div style="text-align:center;margin-bottom:8px;">
                    <span class="section-label">📖 TENTANG KAMI</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-info-circle"></i> Apa itu MEDIKOM? <i class="fas fa-info-circle"></i>
                </h2>
                <div style="max-width:800px;margin:0 auto;text-align:center;">
                    <p style="font-size:clamp(0.88rem,1.6vw,1.05rem);color:#d4c4f0;line-height:1.8;padding:0 8px;">
                        <strong style="color:#ffe74a;">MEDIKOM SMAN 2 JAKARTA</strong> adalah sebuah Sub-Organisasi yang
                        memadukan nilai-nilai organisasi dengan teknologi modern untuk mengembangkan kreativitas, wawasan,
                        serta minat dan bakat siswa/i di bidang media, komunikasi, dan teknologi digital.
                    </p>
                </div>
            </section>

            <!-- ===== PROFIL ===== -->
            <section id="profil">
                <div style="text-align:center;margin-bottom:8px;">
                    <span class="section-label">👤 PROFIL</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-user"></i> Pembina & Ketua <i class="fas fa-user"></i>
                </h2>
                <div class="row g-3" style="margin-top:8px;">
                    <div class="col-md-6">
                        <div class="profile-card">
                            <img src="IMG-20260624-WA0047.jpg" alt="Pembina MEDIKOM" loading="lazy" />
                            <div class="profile-info">
                                <span class="role-badge pembina">PEMBINA</span>
                                <h4>Bpk. Dwi Chandra Kusworo</h4>
                                <p>Dedikasi tinggi dalam membangun pendidikan berkualitas, berkarakter, serta berorientasi pada perkembangan teknologi dan kreativitas siswa.</p>
                            </div>
                        </div>
                    </div>
                    <div class="col-md-6">
                        <div class="profile-card">
                            <img src="KETUA MEDIKOM SMAN 2 JAKARTA.jpg" alt="Ketua MEDIKOM" loading="lazy" />
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
                <div style="text-align:center;margin-bottom:8px;">
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
                <div style="text-align:center;margin-bottom:8px;">
                    <span class="section-label">📂 DIVISI KAMI</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-users"></i> 5 Divisi Unggulan MEDIKOM <i class="fas fa-users"></i>
                </h2>
                <div class="collage-grid">
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(255,231,74,0.2), rgba(255,231,74,0.06));">
                        <div class="media"><img src="POSTER DIVISI FOTOGRAFI (1).png" alt="Divisi Fotografi" loading="lazy" /></div>
                        <div class="caption">Divisi Fotografi</div>
                        <div class="sub-caption" style="color:#ffe74a;">📸 Foto</div>
                        <div class="message" style="border-left-color:#ffe74a;">"Mengabadikan momen terbaik dengan teknik fotografi profesional."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.5rem; padding:5px 10px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI FOTOGRAFI (1).png">LIHAT KARTU</button>
                    </div>
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(227,0,11,0.2), rgba(227,0,11,0.06));">
                        <div class="media"><img src="POSTER DIVISI SINEMATOGRAFI  - Copy.png" alt="Divisi Cinema" loading="lazy" /></div>
                        <div class="caption">Divisi Sinematografi</div>
                        <div class="sub-caption" style="color:#e3000b;">🎬 Cinema</div>
                        <div class="message" style="border-left-color:#e3000b;">"Menghasilkan karya film pendek dan sinematik berkualitas tinggi."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.5rem; padding:5px 10px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI SINEMATOGRAFI  - Copy.png">LIHAT KARTU</button>
                    </div>
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(0,109,183,0.2), rgba(0,109,183,0.06));">
                        <div class="media"><img src="POSTER DIVISI RADIO (1).png" alt="Divisi Radio" loading="lazy" /></div>
                        <div class="caption">Divisi Radio</div>
                        <div class="sub-caption" style="color:#006db7;">📻 Penyiaran</div>
                        <div class="message" style="border-left-color:#006db7;">"Mengelola program siaran radio sekolah yang informatif dan menghibur."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.5rem; padding:5px 10px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI RADIO (1).png">LIHAT KARTU</button>
                    </div>
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(255,107,205,0.2), rgba(255,107,205,0.06));">
                        <div class="media"><img src="POSTER DIVISI MADES (1).png" alt="Divisi Mading & Desain" loading="lazy" /></div>
                        <div class="caption">Divisi Mading & Desain</div>
                        <div class="sub-caption" style="color:#ff6bcd;">📰 Kreativitas Visual</div>
                        <div class="message" style="border-left-color:#ff6bcd;">"Merancang mading sekolah dan materi desain grafis yang menarik."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.5rem; padding:5px 10px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI MADES (1).png">LIHAT KARTU</button>
                    </div>
                    <div class="collage-item" style="background: linear-gradient(135deg, rgba(0,163,78,0.2), rgba(0,163,78,0.06));">
                        <div class="media"><img src="POSTER DIVISI JURNALISTIK.png" alt="Divisi Jurnalistik" loading="lazy" /></div>
                        <div class="caption">Divisi Jurnalistik</div>
                        <div class="sub-caption" style="color:#00a34e;">📰 Liputan & Berita</div>
                        <div class="message" style="border-left-color:#00a34e;">"Menyajikan informasi aktual dan terpercaya seputar kegiatan sekolah."</div>
                        <button class="btn btn-sm btn-klik" style="font-size:0.5rem; padding:5px 10px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="POSTER DIVISI JURNALISTIK.png">LIHAT KARTU</button>
                    </div>
                </div>
            </section>

            <!-- ===== PRESTASI ===== -->
            <section id="prestasi">
                <div style="text-align:center;margin-bottom:8px;">
                    <span class="section-label">🏆 PRESTASI</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-trophy"></i> Prestasi Terbaru <i class="fas fa-trophy"></i>
                </h2>
                <div class="prestasi-grid">
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
                <div style="text-align:center;margin-bottom:8px;">
                    <span class="section-label">📸 GALERI</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-images"></i> Foto Kegiatan Kami <i class="fas fa-images"></i>
                </h2>
                <div class="row justify-content-center">
                    <div class="col-lg-8">
                        <div id="carouselExampleRide" class="carousel slide carousel-retro" data-bs-ride="carousel" data-bs-touch="true">
                            <div class="carousel-inner">
                                <div class="carousel-item active"><img src="Pendidikan Dan Pelatihan.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="3cd558fc-2abd-4b98-8e72-d794b3a34073.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="3d8487d2-1415-470c-8f68-699dcfe08ae6.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="265d417b-8cce-4942-9670-91b9b90fb507.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="1963e56a-f8e5-4e68-a036-b0014c01df08.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="7303bee8-60c6-4034-977f-98dbf780b723.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="222174f4-6f61-47ef-bc8d-7fe0e7c683d4.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="c1229e03-1845-4652-a150-5563862fd3bd.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="IMG_0238.jpeg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="IMG_5086.png" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="IMG-20251002-WA0044.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                                <div class="carousel-item"><img src="IMG-20251213-WA0070.jpg" class="d-block w-100" alt="Kegiatan Seru" loading="lazy" /></div>
                            </div>
                            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleRide" data-bs-slide="prev" aria-label="Sebelumnya">
                                <span class="carousel-control-prev-icon"></span>
                            </button>
                            <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleRide" data-bs-slide="next" aria-label="Berikutnya">
                                <span class="carousel-control-next-icon"></span>
                            </button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ===== VIDEO ===== -->
            <section id="video">
                <div style="text-align:center;margin-bottom:8px;">
                    <span class="section-label">🎬 VIDEO</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-play-circle"></i> Video Kami <i class="fas fa-play-circle"></i>
                </h2>
                <div class="row justify-content-center g-3">
                    <div class="col-md-6">
                        <div class="video-wrapper">
                            <iframe width="100%" height="100%"
                                src="https://www.youtube.com/embed/KC2GR4jNRHQ?si=oe-OVtgLDOhx3_Sz"
                                title="YouTube video player" frameborder="0"
                                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                                referrerpolicy="strict-origin-when-cross-origin" allowfullscreen
                                loading="lazy"></iframe>
                        </div>
                    </div>
                    <div class="col-md-6">
                        <div class="video-wrapper">
                            <video controls playsinline preload="metadata" poster="">
                                <source src="WhatsApp Video 2026-06-30 at 06.29.54.mp4" type="video/mp4">
                                Browser Anda tidak mendukung pemutaran video. Silakan <a href="WhatsApp Video 2026-06-30 at 06.29.54.mp4">unduh video</a>.
                            </video>
                        </div>
                    </div>
                </div>
            </section>

            <!-- ===== PENDAFTARAN ===== -->
            <section id="daftar">
                <div style="text-align:center;margin-bottom:8px;">
                    <span class="section-label" style="background:rgba(0,163,78,0.18);color:#00ff88;border-color:rgba(0,255,136,0.35);">📝 PENDAFTARAN</span>
                </div>
                <div class="daftar-section">
                    <div class="daftar-content">
                        <h2><i class="fas fa-user-plus"></i> AYOO GABUNG MEDIKOM! <i class="fas fa-user-plus"></i></h2>
                        <p>
                            Ingin menjadi bagian dari Sub-Organisasi Media & Teknologi Yang Merupakan Sub-Organisasi terkeren di SMAN 2 Jakarta?<br />
                            <strong style="color:#00ff88;">Daftarkan dirimu sekarang juga!</strong><br />
                            Jika kamu ingin mendapatkan pengalaman, keseruan, pengetahuan dan pertemanan yang luas. "JANGAN LUPA DAFTAR MEDIKOM YAWWW"
                        </p>
                        <p style="margin-top:14px;font-size:0.72rem;color:#a78bcb;">
                            <i class="fas fa-info-circle"></i> Kamu akan diberikan Google Forms · Pastikan data diisi dengan lengkap dan benar.
                        </p>
                        <h2 style="font-size:clamp(0.7rem,1.8vw,1rem);">JANGAN LUPA GABUNG MEDIKOM YAAA!</h2>
                    </div>
                </div>
            </section>

            <!-- ===== KONTAK ===== -->
            <section id="kontak">
                <div style="text-align:center;margin-bottom:8px;">
                    <span class="section-label">📞 KONTAK</span>
                </div>
                <h2 class="section-title">
                    <i class="fas fa-phone"></i> Hubungi Kami <i class="fas fa-phone"></i>
                </h2>
                <p style="text-align:center;max-width:600px;margin:0 auto 16px;color:#d4c4f0;font-size:clamp(0.8rem,1.4vw,0.95rem);padding:0 8px;">
                    Jika ada pertanyaan mengenai informasi tentang MEDIKOM SMAN 2 JAKARTA, silakan hubungi kami melalui kontak berikut.
                </p>
                <div class="collage-grid" style="grid-template-columns:repeat(auto-fit,minmax(130px,1fr));">
                    <a href="https://wa.me/6285694224134" target="_blank" rel="noopener" class="contact-card">
                        <div class="icon-circle" style="background:rgba(37,211,102,0.18);color:#25D366;">💬</div>
                        <h5>WhatsApp</h5>
                        <p>+62 856-9422-4134</p>
                    </a>
                    <a href="https://instagram.com/medikomsmandu" target="_blank" rel="noopener" class="contact-card">
                        <div class="icon-circle" style="background:rgba(225,48,108,0.18);color:#E1306C;">📷</div>
                        <h5>Instagram</h5>
                        <p>@medikomsmandu</p>
                    </a>
                    <a href="https://youtube.com/@medikomsman2jakarta?si=w1OKeB3u0zkZhBNt" target="_blank" rel="noopener" class="contact-card">
                        <div class="icon-circle" style="background:rgba(24,119,242,0.18);color:#1877F2;">📘</div>
                        <h5>Youtube</h5>
                        <p>@medikomsman2jakarta</p>
                    </a>
                    <a href="https://wa.me/6285709309836" target="_blank" rel="noopener" class="contact-card">
                        <div class="icon-circle" style="background:rgba(37,211,102,0.18);color:#25D366;">💬</div>
                        <h5>WhatsApp</h5>
                        <p>+62 857-0930-9836</p>
                    </a>
                </div>
            </section>

            <!-- ===== FOOTER ===== -->
            <footer class="footer">
                <i class="fas fa-crown"></i> MEDIKOM SMAN 2 JAKARTA · RETRO EDITION <i class="fas fa-crown"></i>
                <br />
                <span style="font-size:0.5rem;color:#4a2a6a;">
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
            <img src="Logo MEDIKOM.png" alt="Logo MEDIKOM" class="card-logo" loading="lazy" />
            <div class="card-title">MEDIKOM</div>
            <div class="card-subtitle">SMAN 2 JAKARTA</div>
            <div class="divider"></div>
            <p style="font-size:clamp(0.75rem,1.3vw,0.9rem); color:#d4c4f0; margin-bottom:16px;">
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
                <a href="https://wa.me/6285694224134" target="_blank" rel="noopener" title="WhatsApp" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                <a href="https://instagram.com/medikomsmandu" target="_blank" rel="noopener" title="Instagram" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                <a href="https://youtube.com/@medikomsman2jakarta?si=w1OKeB3u0zkZhBNt" target="_blank" rel="noopener" title="Youtube" aria-label="Youtube"><i class="fab fa-youtube"></i></a>
                <a href="https://wa.me/6285709309836" target="_blank" rel="noopener" title="WhatsApp" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
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
                    <button type="button" class="btn-close btn-close-white" data-bs-dismiss="modal" aria-label="Close" style="position: absolute; top: 8px; right: 12px; z-index: 10; filter: drop-shadow(0 0 4px rgba(255,255,255,0.5));"></button>
                    <img id="modalImageOnly" src="Logo MEDIKOM (1).png" alt="" class="modal-img-only" loading="lazy" />
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
            const particleCount = window.innerWidth < 500 ? 12 : 22;
            for (let i = 0; i < particleCount; i++) {
                const el = document.createElement('div');
                el.className = 'lego-particle';
                const color = colors[Math.floor(Math.random() * colors.length)];
                el.style.background = color;
                el.style.color = color;
                el.style.width = (18 + Math.random() * 26) + 'px';
                el.style.height = (8 + Math.random() * 10) + 'px';
                el.style.left = Math.random() * 100 + '%';
                el.style.animationDuration = (14 + Math.random() * 22) + 's';
                el.style.animationDelay = (Math.random() * 20) + 's';
                document.body.appendChild(el);
            }

            // ===== CANVAS EFFECT =====
            const canvas = document.getElementById('effectCanvas');
            const wrapper = document.getElementById('visualCanvasWrapper');
            function resizeCanvas() {
                if (!canvas || !wrapper) return;
                const rect = wrapper.getBoundingClientRect();
                const dpr = Math.min(window.devicePixelRatio || 1, 2);
                canvas.width = rect.width * dpr;
                canvas.height = rect.height * dpr;
                canvas.style.width = rect.width + 'px';
                canvas.style.height = rect.height + 'px';
            }
            if (canvas) {
                resizeCanvas();
                window.addEventListener('resize', () => {
                    resizeCanvas();
                });
                const ctx = canvas.getContext('2d');
                let time = 0;
                let animId;
                function drawEffect() {
                    const w = canvas.width, h = canvas.height;
                    if (w === 0 || h === 0) {
                        animId = requestAnimationFrame(drawEffect);
                        return;
                    }
                    const dpr = Math.min(window.devicePixelRatio || 1, 2);
                    ctx.setTransform(1, 0, 0, 1, 0, 0);
                    ctx.clearRect(0, 0, w, h);
                    ctx.scale(dpr, dpr);
                    const cw = w / dpr;
                    const ch = h / dpr;

                    const grad = ctx.createRadialGradient(cw * 0.5, ch * 0.5, 0, cw * 0.5, ch * 0.5, cw * 0.7);
                    grad.addColorStop(0, 'rgba(45, 27, 105, 0.2)');
                    grad.addColorStop(1, 'rgba(12, 5, 24, 0.35)');
                    ctx.fillStyle = grad;
                    ctx.fillRect(0, 0, cw, ch);

                    const waveCount = 3;
                    for (let wv = 0; wv < waveCount; wv++) {
                        ctx.beginPath();
                        const baseY = ch * (0.22 + wv * 0.22);
                        const amp = 10 + wv * 5;
                        const freq = 0.025 + wv * 0.006;
                        const phase = time * 0.018 + wv * 1.0;
                        for (let x = 0; x <= cw; x += 3) {
                            const y = baseY + Math.sin(x * freq + phase) * amp +
                                Math.sin(x * freq * 0.5 + phase * 1.2) * amp * 0.4;
                            if (x === 0) ctx.moveTo(x, y);
                            else ctx.lineTo(x, y);
                        }
                        ctx.strokeStyle = `rgba(255, 231, 74, ${0.1 + wv * 0.04})`;
                        ctx.lineWidth = 1.5 + wv * 0.6;
                        ctx.shadowColor = 'rgba(255, 107, 205, 0.25)';
                        ctx.shadowBlur = 14;
                        ctx.stroke();
                    }

                    const dotCount = 20;
                    for (let i = 0; i < dotCount; i++) {
                        const x = (Math.sin(i * 1.6 + time * 0.01) * 0.4 + 0.5) * cw;
                        const y = (Math.cos(i * 2.1 + time * 0.014) * 0.35 + 0.5) * ch;
                        const r = 1.5 + Math.sin(i + time * 0.02) * 1.2;
                        const alpha = 0.18 + Math.sin(i + time * 0.03) * 0.12 + 0.25;
                        ctx.beginPath();
                        ctx.arc(x, y, r, 0, Math.PI * 2);
                        const dotColors = ['#ffe74a', '#ff6bcd', '#00f0ff', '#f5cd1f'];
                        ctx.fillStyle = dotColors[i % dotColors.length] + Math.floor(alpha * 170).toString(16).padStart(2, '0');
                        ctx.shadowBlur = 12;
                        ctx.shadowColor = dotColors[i % dotColors.length] + '55';
                        ctx.fill();
                    }
                    ctx.shadowBlur = 0;
                    time++;
                    animId = requestAnimationFrame(drawEffect);
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
                divisiGrid.innerHTML = '';
                fasilitasData.forEach(d => {
                    divisiGrid.innerHTML += `
                        <div class="collage-item">
                            <div class="media"><img src="${d.image}" alt="${d.name}" loading="lazy" /></div>
                            <div class="caption">${d.name}</div>
                            <div class="sub-caption">${d.date}</div>
                            <div class="message">"${d.desc}"</div>
                            <button class="btn btn-sm btn-klik" style="font-size:0.5rem; padding:5px 10px; margin-top:8px;" data-bs-toggle="modal" data-bs-target="#imageOnlyModal" data-image="${d.image}">LIHAT KARTU</button>
                        </div>`;
                });
            }

            // ===== MODAL HANYA FOTO =====
            const imageModal = document.getElementById('imageOnlyModal');
            if (imageModal) {
                imageModal.addEventListener('show.bs.modal', function(event) {
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

            function switchPage(show, hide) {
                if (hide) hide.classList.remove('active');
                if (show) {
                    show.classList.add('active');
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                }
            }

            if (btnToPage2) {
                btnToPage2.addEventListener('click', () => switchPage(page2, page1));
            }
            if (btnBackToPage1) {
                btnBackToPage1.addEventListener('click', () => switchPage(page1, page2));
            }

            // Smooth scroll untuk anchor link di halaman 1
            document.querySelectorAll('.nav-retro a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    const targetId = this.getAttribute('href').substring(1);
                    const target = document.getElementById(targetId);
                    if (target && page1 && page1.classList.contains('active')) {
                        e.preventDefault();
                        target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                    }
                });
            });

            console.log('🧱 MEDIKOM SMAN 2 JAKARTA · Mobile-optimized Retro Edition siap!');
        })();
    </script>
</body>
</html>
