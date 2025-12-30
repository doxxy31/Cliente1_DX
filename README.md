<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ChronoBot - Revoluciona Tu Productividad con IA</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;700;900&family=Exo+2:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #00f3ff;
            --secondary-color: #9d4edd;
            --accent-color: #00ff9d;
            --dark-bg: #0a0e17;
            --card-bg: rgba(16, 20, 31, 0.8);
            --text-color: #e0e0ff;
            --text-secondary: #a0a0c0;
            --neon-shadow: 0 0 10px var(--primary-color),
                            0 0 20px var(--primary-color),
                            0 0 30px var(--primary-color);
            --neon-shadow-secondary: 0 0 10px var(--secondary-color),
                                    0 0 20px var(--secondary-color);
            --neon-shadow-accent: 0 0 10px var(--accent-color),
                                  0 0 20px var(--accent-color);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Exo 2', sans-serif;
            background-color: var(--dark-bg);
            color: var(--text-color);
            overflow-x: hidden;
            line-height: 1.6;
        }

        h1, h2, h3, h4 {
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Fondo animado */
        #bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(45deg, #0a0e17, #0f1525, #1a1f35);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Banner de oferta */
        .offer-banner {
            background: linear-gradient(90deg, #ff0080, #9d4edd);
            color: white;
            text-align: center;
            padding: 12px 0;
            font-weight: 600;
            font-size: 1.1rem;
            position: relative;
            overflow: hidden;
            animation: pulseBanner 2s infinite;
            box-shadow: 0 0 20px rgba(255, 0, 128, 0.5);
        }

        @keyframes pulseBanner {
            0%, 100% { box-shadow: 0 0 20px rgba(255, 0, 128, 0.5); }
            50% { box-shadow: 0 0 30px rgba(255, 0, 128, 0.8); }
        }

        .offer-banner .close-offer {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: white;
            font-size: 1.2rem;
            cursor: pointer;
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            padding: 20px 0;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            background-color: rgba(10, 14, 23, 0.8);
            border-bottom: 1px solid rgba(0, 243, 255, 0.1);
        }

        header.scrolled {
            padding: 15px 0;
            box-shadow: 0 5px 20px rgba(0, 243, 255, 0.1);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-family: 'Orbitron', sans-serif;
            font-size: 1.8rem;
            font-weight: 900;
            color: var(--primary-color);
            text-shadow: var(--neon-shadow-secondary);
        }

        .logo i {
            font-size: 2rem;
        }

        .nav-menu {
            display: flex;
            gap: 30px;
        }

        .nav-menu a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            padding: 5px 10px;
            border-radius: 4px;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-menu a:hover {
            color: var(--primary-color);
            text-shadow: var(--neon-shadow-secondary);
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: width 0.3s ease;
        }

        .nav-menu a:hover::after {
            width: 80%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--primary-color);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Sección Hero */
        .hero {
            padding: 180px 0 120px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 20px rgba(0, 243, 255, 0.5);
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.3rem;
            max-width: 700px;
            margin: 0 auto 40px;
            color: var(--text-secondary);
        }

        .hero-stats {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-top: 60px;
            flex-wrap: wrap;
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            font-family: 'Orbitron', sans-serif;
            font-size: 2.5rem;
            font-weight: 900;
            color: var(--accent-color);
            text-shadow: var(--neon-shadow-accent);
            margin-bottom: 5px;
        }

        .stat-label {
            color: var(--text-secondary);
            font-size: 1rem;
        }

        /* Botones con borde animado MEJORADO (más rápido) */
        .cta-button {
            display: inline-block;
            padding: 18px 40px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            color: var(--dark-bg);
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            font-size: 1.2rem;
            text-decoration: none;
            border-radius: 8px;
            box-shadow: var(--neon-shadow);
            transition: all 0.2s ease; /* Cambiado de 0.3s a 0.2s para ser más rápido */
            position: relative;
            overflow: hidden;
            z-index: 1;
            border: none;
            cursor: pointer;
            margin-top: 20px;
        }

        .cta-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 0 25px var(--primary-color);
        }

        .cta-button::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, var(--secondary-color), var(--accent-color));
            z-index: -1;
            opacity: 0;
            transition: opacity 0.2s ease; /* Más rápido */
        }

        .cta-button:hover::after {
            opacity: 1;
        }

        /* Efecto de borde animado en hover MEJORADO */
        .border-hover-effect {
            position: relative;
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            transition: all 0.3s ease;
            border: 1px solid transparent;
        }

        .border-hover-effect::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color), var(--accent-color), var(--primary-color));
            background-size: 400% 400%;
            border-radius: 17px;
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s ease;
            animation: borderFlow 3s linear infinite;
        }

        .border-hover-effect:hover::before {
            opacity: 1;
        }

        .border-hover-effect:hover {
            transform: translateY(-10px);
            box-shadow: var(--neon-shadow-secondary);
        }

        @keyframes borderFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Sección Funciones */
        .features {
            padding: 100px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            color: var(--primary-color);
            text-shadow: var(--neon-shadow-secondary);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background-color: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            transition: all 0.4s ease;
            border: 1px solid rgba(0, 243, 255, 0.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
            z-index: 1;
            height: 100%;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0, 243, 255, 0.05), rgba(157, 78, 221, 0.05));
            z-index: -1;
        }

        .feature-card:hover {
            transform: translateY(-15px) rotateX(5deg);
            box-shadow: var(--neon-shadow-secondary);
            border-color: var(--secondary-color);
        }

        .feature-icon {
            font-size: 3rem;
            color: var(--accent-color);
            margin-bottom: 20px;
            text-shadow: var(--neon-shadow-accent);
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--text-color);
        }

        .feature-card p {
            color: var(--text-secondary);
        }

        /* Sección Capturas */
        .screenshots {
            padding: 100px 0;
        }

        .screenshots-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .screenshot-item {
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            transition: all 0.4s ease;
            position: relative;
            height: 250px;
            background: linear-gradient(45deg, #1a1f35, #2a2f45);
            display: flex;
            align-items: center;
            justify-content: center;
            border: 1px solid rgba(0, 243, 255, 0.2);
        }

        .screenshot-item:hover {
            transform: scale(1.05);
            box-shadow: var(--neon-shadow);
        }

        .screenshot-content {
            text-align: center;
            padding: 20px;
        }

        .screenshot-icon {
            font-size: 4rem;
            color: var(--primary-color);
            margin-bottom: 20px;
            text-shadow: var(--neon-shadow);
        }

        .screenshot-item h3 {
            color: var(--primary-color);
            font-size: 1.5rem;
        }

        /* Sección Testimonios */
        .testimonials {
            padding: 100px 0;
            background: linear-gradient(180deg, rgba(10, 14, 23, 0.9), rgba(26, 31, 53, 0.9));
        }

        .testimonials-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background-color: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            border-left: 5px solid var(--accent-color);
            transition: all 0.3s ease;
        }

        .testimonial-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--neon-shadow-accent);
        }

        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
            color: var(--text-color);
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--accent-color);
        }

        .author-info h4 {
            color: var(--primary-color);
            margin-bottom: 5px;
            font-size: 1.1rem;
        }

        .author-info p {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* Sección Precios */
        .pricing {
            padding: 100px 0;
        }

        .pricing-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .pricing-card {
            background-color: var(--card-bg);
            border-radius: 15px;
            padding: 40px 30px;
            text-align: center;
            transition: all 0.4s ease;
            position: relative;
            border: 1px solid rgba(0, 243, 255, 0.1);
        }

        .pricing-card.popular {
            border: 2px solid var(--accent-color);
            transform: scale(1.05);
            box-shadow: var(--neon-shadow-accent);
        }

        .pricing-card.popular::before {
            content: 'MÁS POPULAR';
            position: absolute;
            top: -12px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--accent-color);
            color: var(--dark-bg);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 700;
            font-family: 'Orbitron', sans-serif;
        }

        .pricing-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--neon-shadow-secondary);
        }

        .pricing-card.popular:hover {
            transform: translateY(-10px) scale(1.05);
        }

        .pricing-header {
            margin-bottom: 30px;
        }

        .pricing-name {
            font-size: 1.5rem;
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        .pricing-price {
            font-family: 'Orbitron', sans-serif;
            font-size: 3rem;
            color: var(--accent-color);
            margin-bottom: 5px;
        }

        .pricing-period {
            color: var(--text-secondary);
            font-size: 1rem;
        }

        .pricing-features {
            list-style: none;
            margin-bottom: 30px;
        }

        .pricing-features li {
            padding: 10px 0;
            color: var(--text-secondary);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .pricing-features li i {
            color: var(--accent-color);
            margin-right: 10px;
        }

        .pricing-button {
            width: 100%;
            padding: 15px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            color: var(--dark-bg);
            border: none;
            border-radius: 8px;
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.2s ease; /* Más rápido */
        }

        .pricing-button:hover {
            transform: translateY(-3px);
            box-shadow: var(--neon-shadow);
        }

        /* Sección Comparativa */
        .comparison {
            padding: 80px 0;
            background: linear-gradient(180deg, rgba(10, 14, 23, 0.9), rgba(16, 20, 31, 0.9));
        }

        .comparison-table {
            width: 100%;
            border-collapse: collapse;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .comparison-table th, .comparison-table td {
            padding: 20px;
            text-align: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .comparison-table th {
            background-color: rgba(0, 243, 255, 0.1);
            color: var(--primary-color);
            font-family: 'Orbitron', sans-serif;
            font-size: 1.2rem;
        }

        .comparison-table td:first-child {
            text-align: left;
            font-weight: 600;
            color: var(--text-color);
        }

        .comparison-table tr:nth-child(even) {
            background-color: rgba(255, 255, 255, 0.03);
        }

        .checkmark {
            color: var(--accent-color);
            font-size: 1.5rem;
        }

        .crossmark {
            color: #ff4d4d;
            font-size: 1.5rem;
        }

        /* NUEVA: Sección de Contacto */
        .contact {
            padding: 100px 0;
            background: linear-gradient(180deg, rgba(10, 14, 23, 0.9), rgba(16, 20, 31, 0.9));
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 20px;
        }

        .contact-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--dark-bg);
            flex-shrink: 0;
        }

        .contact-details h3 {
            color: var(--primary-color);
            margin-bottom: 10px;
            font-size: 1.3rem;
        }

        .contact-details p {
            color: var(--text-secondary);
        }

        .contact-form-container {
            background-color: var(--card-bg);
            border-radius: 15px;
            padding: 40px;
            border: 1px solid rgba(0, 243, 255, 0.1);
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .form-group label {
            color: var(--primary-color);
            font-weight: 500;
        }

        .form-control {
            padding: 15px;
            background-color: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(0, 243, 255, 0.2);
            border-radius: 8px;
            color: var(--text-color);
            font-family: 'Exo 2', sans-serif;
            font-size: 1rem;
            transition: all 0.2s ease;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 10px rgba(0, 243, 255, 0.3);
        }

        .form-control::placeholder {
            color: rgba(160, 160, 192, 0.5);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        .form-button {
            padding: 18px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            color: var(--dark-bg);
            border: none;
            border-radius: 8px;
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.2s ease;
            margin-top: 10px;
        }

        .form-button:hover {
            transform: translateY(-3px);
            box-shadow: var(--neon-shadow);
        }

        .map-container {
            margin-top: 40px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(0, 243, 255, 0.2);
        }

        .map-placeholder {
            height: 300px;
            background: linear-gradient(45deg, #1a1f35, #2a2f45);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--primary-color);
        }

        .map-placeholder i {
            font-size: 4rem;
            margin-bottom: 20px;
        }

        /* Garantía y Seguridad */
        .guarantee {
            background: linear-gradient(90deg, rgba(0, 243, 255, 0.1), rgba(157, 78, 221, 0.1));
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            margin: 50px 0;
            border: 1px solid rgba(0, 243, 255, 0.2);
        }

        .guarantee h3 {
            color: var(--accent-color);
            margin-bottom: 15px;
        }

        .guarantee p {
            color: var(--text-color);
            max-width: 800px;
            margin: 0 auto;
        }

        /* Efectos de partículas */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background-color: var(--primary-color);
            border-radius: 50%;
            opacity: 0.3;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translateY(0) translateX(0); }
            25% { transform: translateY(-100vh) translateX(100px); }
            50% { transform: translateY(-50vh) translateX(-100px); }
            75% { transform: translateY(-150vh) translateX(50px); }
            100% { transform: translateY(0) translateX(0); }
        }

        /* Animaciones al hacer scroll */
        .hidden {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
        }

        .show {
            opacity: 1;
            transform: translateY(0);
        }

        /* Footer */
        footer {
            background-color: rgba(5, 9, 15, 0.9);
            padding: 70px 0 30px;
            border-top: 1px solid rgba(0, 243, 255, 0.1);
            margin-top: 50px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 50px;
        }

        .footer-column h3 {
            color: var(--primary-color);
            font-size: 1.5rem;
            margin-bottom: 25px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background-color: var(--primary-color);
        }

        .footer-column p {
            color: var(--text-secondary);
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--card-bg);
            color: var(--primary-color);
            font-size: 1.2rem;
            transition: all 0.2s ease; /* Más rápido */
        }

        .social-link:hover {
            background-color: var(--primary-color);
            color: var(--dark-bg);
            transform: translateY(-5px);
            box-shadow: var(--neon-shadow);
        }

        .contact-info-list {
            list-style: none;
        }

        .contact-info-list li {
            margin-bottom: 15px;
            color: var(--text-secondary);
        }

        .contact-info-list i {
            color: var(--primary-color);
            margin-right: 10px;
            width: 20px;
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* Responsive */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .section-title {
                font-size: 2.2rem;
            }
            
            .pricing-card.popular {
                transform: none;
            }
        }

        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }

            .nav-menu {
                position: fixed;
                top: 80px;
                left: 0;
                width: 100%;
                background-color: rgba(10, 14, 23, 0.95);
                flex-direction: column;
                align-items: center;
                padding: 20px 0;
                gap: 0;
                transform: translateY(-100%);
                opacity: 0;
                transition: all 0.3s ease;
                backdrop-filter: blur(10px);
                z-index: 999;
            }

            .nav-menu.active {
                transform: translateY(0);
                opacity: 1;
            }

            .nav-menu a {
                padding: 15px;
                width: 100%;
                text-align: center;
            }

            .hero h1 {
                font-size: 2.3rem;
            }

            .hero p {
                font-size: 1.1rem;
            }
            
            .hero-stats {
                gap: 20px;
            }
            
            .comparison-table {
                display: block;
                overflow-x: auto;
            }
            
            .contact-container {
                gap: 30px;
            }
            
            .contact-form-container {
                padding: 30px;
            }
        }

        @media (max-width: 576px) {
            .hero {
                padding: 150px 0 80px;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .cta-button {
                padding: 15px 30px;
                font-size: 1rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .feature-card, .screenshot-item, .testimonial-card, .pricing-card {
                padding: 20px;
            }
            
            .stat-number {
                font-size: 2rem;
            }
            
            .contact-icon {
                width: 50px;
                height: 50px;
                font-size: 1.3rem;
            }
        }

        /* Modal de demostración */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background: linear-gradient(135deg, var(--dark-bg), #1a1f35);
            width: 90%;
            max-width: 600px;
            border-radius: 15px;
            padding: 40px;
            text-align: center;
            border: 1px solid var(--primary-color);
            box-shadow: var(--neon-shadow);
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 20px;
            right: 20px;
            color: var(--primary-color);
            font-size: 2rem;
            cursor: pointer;
            transition: all 0.2s ease; /* Más rápido */
        }

        .close-modal:hover {
            color: var(--accent-color);
            transform: rotate(90deg);
        }

        .modal h2 {
            color: var(--primary-color);
            margin-bottom: 20px;
            font-size: 2rem;
        }

        .modal p {
            margin-bottom: 30px;
            color: var(--text-secondary);
        }

        .demo-placeholder {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, #1a1f35, #2a2f45);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 20px 0;
            border: 1px solid var(--primary-color);
        }

        .demo-placeholder i {
            font-size: 4rem;
            color: var(--primary-color);
        }
        
        /* Contador regresivo */
        .countdown {
            background: rgba(0, 0, 0, 0.3);
            padding: 20px;
            border-radius: 10px;
            margin: 30px 0;
            border: 1px solid var(--primary-color);
        }
        
        .countdown h4 {
            color: var(--accent-color);
            margin-bottom: 15px;
        }
        
        .countdown-timer {
            display: flex;
            justify-content: center;
            gap: 15px;
        }
        
        .countdown-item {
            text-align: center;
            background: rgba(0, 0, 0, 0.5);
            padding: 10px;
            border-radius: 8px;
            min-width: 70px;
        }
        
        .countdown-number {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.8rem;
            color: var(--primary-color);
        }
        
        .countdown-label {
            font-size: 0.8rem;
            color: var(--text-secondary);
            margin-top: 5px;
        }
    </style>
</head>
<body>
    <!-- Fondo animado -->
    <div id="bg-animation"></div>
    
    <!-- Partículas flotantes -->
    <div class="particles" id="particles"></div>
    
    <!-- Banner de oferta especial -->
    <div class="offer-banner" id="offer-banner">
        <span>🔥 OFERTA POR LANZAMIENTO: 50% DE DESCUENTO EN EL PRIMER MES | CÓDIGO: CHRONO50</span>
        <button class="close-offer" id="close-offer">×</button>
    </div>
    
    <!-- Header -->
    <header id="header">
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-robot"></i>
                <span>ChronoBot</span>
            </div>
            
            <button class="mobile-menu-btn" id="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
            
            <nav class="nav-menu" id="nav-menu">
                <a href="#home">Inicio</a>
                <a href="#features">Funciones</a>
                <a href="#testimonials">Testimonios</a>
                <a href="#pricing">Precios</a>
                <a href="#contact">Contacto</a>
            </nav>
        </div>
    </header>
    
    <!-- Sección Hero -->
    <section class="hero" id="home">
        <div class="container">
            <h1 class="hidden">Aumenta tu productividad 3x con IA</h1>
            <p class="hidden">ChronoBot automatiza la gestión de tu agenda con inteligencia artificial. Ahorra 10 horas a la semana en tareas administrativas y enfócate en lo que realmente importa.</p>
            
            <div class="countdown hidden">
                <h4>¡Oferta especial por tiempo limitado!</h4>
                <div class="countdown-timer" id="countdown-timer">
                    <div class="countdown-item">
                        <div class="countdown-number" id="days">00</div>
                        <div class="countdown-label">DÍAS</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="hours">00</div>
                        <div class="countdown-label">HORAS</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="minutes">00</div>
                        <div class="countdown-label">MINUTOS</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="seconds">00</div>
                        <div class="countdown-label">SEGUNDOS</div>
                    </div>
                </div>
            </div>
            
            <button class="cta-button" id="demo-btn">Probar Demo Gratis</button>
            
            <div class="hero-stats hidden">
                <div class="stat-item">
                    <div class="stat-number">10,000+</div>
                    <div class="stat-label">Usuarios Activos</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">97%</div>
                    <div class="stat-label">Satisfacción</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">500k+</div>
                    <div class="stat-label">Eventos Gestionados</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">10h</div>
                    <div class="stat-label">Ahorro Semanal</div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Sección Funciones -->
    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title hidden">Funciones que Revolucionan tu Productividad</h2>
            <div class="features-grid">
                <div class="feature-card hidden">
                    <div class="feature-icon">
                        <i class="fas fa-calendar-plus"></i>
                    </div>
                    <h3>Crear Eventos con IA</h3>
                    <p>Añade eventos a tu calendario con comandos de voz o texto. ChronoBot detecta automáticamente fechas y horas.</p>
                </div>
                
                <div class="feature-card hidden">
                    <div class="feature-icon">
                        <i class="fas fa-calendar-times"></i>
                    </div>
                    <h3>Eliminar Eventos</h3>
                    <p>Elimina o cancela eventos con un simple comando. ChronoBot se encarga de notificar a todos los participantes.</p>
                </div>
                
                <div class="feature-card hidden">
                    <div class="feature-icon">
                        <i class="fas fa-edit"></i>
                    </div>
                    <h3>Modificar Eventos</h3>
                    <p>Cambia fecha, hora, lugar o detalles de cualquier evento. ChronoBot actualiza automáticamente todos los calendarios vinculados.</p>
                </div>
                
                <div class="feature-card hidden">
                    <div class="feature-icon">
                        <i class="fas fa-search"></i>
                    </div>
                    <h3>Consultar Disponibilidad</h3>
                    <p>Comprueba los horarios disponibles de tu equipo para encontrar el mejor momento para una reunión.</p>
                </div>
                
                <div class="feature-card hidden">
                    <div class="feature-icon">
                        <i class="fas fa-bell"></i>
                    </div>
                    <h3>Recordatorios Inteligentes</h3>
                    <p>Recibe notificaciones antes de cada evento, con tiempo suficiente para prepararte.</p>
                </div>
                
                <div class="feature-card hidden">
                    <div class="feature-icon">
                        <i class="fas fa-sync-alt"></i>
                    </div>
                    <h3>Sincronización Multiplataforma</h3>
                    <p>Conecta con Google Calendar, Outlook, Apple Calendar y más. ChronoBot sincroniza todos tus calendarios.</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Sección Testimonios -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <h2 class="section-title hidden">Lo que dicen nuestros clientes</h2>
            <div class="testimonials-container">
                <div class="testimonial-card hidden">
                    <div class="testimonial-text">
                        "ChronoBot ha cambiado completamente la forma en que gestiono mi tiempo. Antes perdía horas organizando mi agenda, ahora solo le digo lo que necesito y listo."
                    </div>
                    <div class="testimonial-author">
                        <img src="https://images.unsplash.com/photo-1494790108755-2616b612b786?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=200&q=80" alt="Ana García" class="author-avatar">
                        <div class="author-info">
                            <h4>Ana García</h4>
                            <p>CEO, TechSolutions</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card hidden">
                    <div class="testimonial-text">
                        "Implementamos ChronoBot en toda la empresa y la productividad aumentó un 40%. Los equipos ahora se enfocan en su trabajo, no en organizar reuniones."
                    </div>
                    <div class="testimonial-author">
                        <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=200&q=80" alt="Carlos Ruiz" class="author-avatar">
                        <div class="author-info">
                            <h4>Carlos Ruiz</h4>
                            <p>Director de Operaciones</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card hidden">
                    <div class="testimonial-text">
                        "Como freelancer, ChronoBot me ha ayudado a organizar mis proyectos con clientes de todo el mundo. La integración con diferentes zonas horarias es increíble."
                    </div>
                    <div class="testimonial-author">
                        <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=200&q=80" alt="Laura Méndez" class="author-avatar">
                        <div class="author-info">
                            <h4>Laura Méndez</h4>
                            <p>Diseñadora UX Freelance</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Sección de Garantía -->
    <section class="container">
        <div class="guarantee hidden">
            <h3>Garantía de Satisfacción 100%</h3>
            <p>Si ChronoBot no aumenta tu productividad en al menos un 30% durante el primer mes, te devolvemos tu dinero. Sin preguntas, sin complicaciones.</p>
            <p><i class="fas fa-shield-alt" style="color: var(--accent-color); margin-right: 10px;"></i>Tu información está 100% protegida con encriptación de grado militar</p>
        </div>
    </section>
    
    <!-- Sección Precios -->
    <section class="pricing" id="pricing">
        <div class="container">
            <h2 class="section-title hidden">Planes para Cada Necesidad</h2>
            <div class="pricing-container">
                <div class="pricing-card hidden">
                    <div class="pricing-header">
                        <h3 class="pricing-name">Básico</h3>
                        <div class="pricing-price">$9<span style="font-size: 1.5rem;">/mes</span></div>
                        <div class="pricing-period">Ideal para individuos</div>
                    </div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Hasta 5 calendarios</li>
                        <li><i class="fas fa-check"></i> 100 eventos/mes</li>
                        <li><i class="fas fa-check"></i> Recordatorios básicos</li>
                        <li><i class="fas fa-check"></i> Soporte por email</li>
                        <li><i class="fas fa-times"></i> Integración con CRM</li>
                        <li><i class="fas fa-times"></i> Análisis de productividad</li>
                    </ul>
                    <button class="pricing-button" data-plan="basico">Comenzar Ahora</button>
                </div>
                
                <div class="pricing-card popular hidden">
                    <div class="pricing-header">
                        <h3 class="pricing-name">Profesional</h3>
                        <div class="pricing-price">$19<span style="font-size: 1.5rem;">/mes</span></div>
                        <div class="pricing-period">Ideal para equipos</div>
                    </div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Calendarios ilimitados</li>
                        <li><i class="fas fa-check"></i> Eventos ilimitados</li>
                        <li><i class="fas fa-check"></i> Recordatorios inteligentes</li>
                        <li><i class="fas fa-check"></i> Soporte prioritario</li>
                        <li><i class="fas fa-check"></i> Integración con CRM</li>
                        <li><i class="fas fa-check"></i> Análisis de productividad</li>
                    </ul>
                    <button class="pricing-button" data-plan="profesional">Oferta Especial - 50% OFF</button>
                </div>
                
                <div class="pricing-card hidden">
                    <div class="pricing-header">
                        <h3 class="pricing-name">Empresa</h3>
                        <div class="pricing-price">$49<span style="font-size: 1.5rem;">/mes</span></div>
                        <div class="pricing-period">Ideal para organizaciones</div>
                    </div>
                    <ul class="pricing-features">
                        <li><i class="fas fa-check"></i> Todo en Profesional</li>
                        <li><i class="fas fa-check"></i> Hasta 50 usuarios</li>
                        <li><i class="fas fa-check"></i> API personalizada</li>
                        <li><i class="fas fa-check"></i> Soporte 24/7</li>
                        <li><i class="fas fa-check"></i> Entrenamiento personalizado</li>
                        <li><i class="fas fa-check"></i> SLA 99.9%</li>
                    </ul>
                    <button class="pricing-button" data-plan="empresa">Contactar Ventas</button>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Sección Comparativa -->
    <section class="comparison">
        <div class="container">
            <h2 class="section-title hidden">Compara con Otras Soluciones</h2>
            <div class="hidden">
                <table class="comparison-table">
                    <thead>
                        <tr>
                            <th>Característica</th>
                            <th>ChronoBot</th>
                            <th>Google Calendar</th>
                            <th>Calendly</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Inteligencia Artificial</td>
                            <td><i class="fas fa-check checkmark"></i></td>
                            <td><i class="fas fa-times crossmark"></i></td>
                            <td><i class="fas fa-times crossmark"></i></td>
                        </tr>
                        <tr>
                            <td>Comandos de Voz</td>
                            <td><i class="fas fa-check checkmark"></i></td>
                            <td><i class="fas fa-times crossmark"></i></td>
                            <td><i class="fas fa-times crossmark"></i></td>
                        </tr>
                        <tr>
                            <td>Automatización Completa</td>
                            <td><i class="fas fa-check checkmark"></i></td>
                            <td><i class="fas fa-times crossmark"></i></td>
                            <td><i class="fas fa-check checkmark"></i></td>
                        </tr>
                        <tr>
                            <td>Integración Multiplataforma</td>
                            <td><i class="fas fa-check checkmark"></i></td>
                            <td><i class="fas fa-check checkmark"></i></td>
                            <td><i class="fas fa-check checkmark"></i></td>
                        </tr>
                        <tr>
                            <td>Análisis de Productividad</td>
                            <td><i class="fas fa-check checkmark"></i></td>
                            <td><i class="fas fa-times crossmark"></i></td>
                            <td><i class="fas fa-times crossmark"></i></td>
                        </tr>
                        <tr>
                            <td>Precio Mensual</td>
                            <td><strong>$19</strong></td>
                            <td><strong>$0</strong></td>
                            <td><strong>$12</strong></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </section>
    
    <!-- NUEVA SECCIÓN: Contacto -->
    <section class="contact" id="contact">
        <div class="container">
            <h2 class="section-title hidden">Contáctanos</h2>
            <p class="hidden" style="text-align: center; max-width: 700px; margin: 0 auto 60px; color: var(--text-secondary);">¿Tienes preguntas? ¿Necesitas una solución personalizada? Nuestro equipo está listo para ayudarte a transformar tu productividad.</p>
            
            <div class="contact-container">
                <!-- Información de contacto -->
                <div class="contact-info hidden">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div class="contact-details">
                            <h3>Nuestra Ubicación</h3>
                            <p>Av. Tecnológica 1234<br>Silicon Valley, CA 94000<br>Estados Unidos</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div class="contact-details">
                            <h3>Teléfono</h3>
                            <p>+1 (555) 123-4567<br>Lunes a Viernes: 9:00 AM - 6:00 PM</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-details">
                            <h3>Correo Electrónico</h3>
                            <p>info@chronobot.com<br>soporte@chronobot.com<br>ventas@chronobot.com</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-clock"></i>
                        </div>
                        <div class="contact-details">
                            <h3>Horario de Atención</h3>
                            <p>Lunes a Viernes: 9:00 AM - 6:00 PM<br>Sábados: 10:00 AM - 2:00 PM<br>Timezone: PST (GMT-8)</p>
                        </div>
                    </div>
                </div>
                
                <!-- Formulario de contacto -->
                <div class="hidden">
                    <div class="contact-form-container border-hover-effect">
                        <h3 style="color: var(--primary-color); margin-bottom: 25px; text-align: center;">Envíanos un Mensaje</h3>
                        <form class="contact-form" id="contact-form">
                            <div class="form-group">
                                <label for="name">Nombre Completo</label>
                                <input type="text" id="name" class="form-control" placeholder="Tu nombre" required>
                            </div>
                            
                            <div class="form-group">
                                <label for="email">Correo Electrónico</label>
                                <input type="email" id="email" class="form-control" placeholder="tu@email.com" required>
                            </div>
                            
                            <div class="form-group">
                                <label for="subject">Asunto</label>
                                <input type="text" id="subject" class="form-control" placeholder="¿Cómo podemos ayudarte?" required>
                            </div>
                            
                            <div class="form-group">
                                <label for="message">Mensaje</label>
                                <textarea id="message" class="form-control" placeholder="Describe tu consulta o proyecto..." required></textarea>
                            </div>
                            
                            <div class="form-group">
                                <label for="plan">Plan de Interés (Opcional)</label>
                                <select id="plan" class="form-control">
                                    <option value="">Selecciona un plan</option>
                                    <option value="basico">Básico</option>
                                    <option value="profesional">Profesional</option>
                                    <option value="empresa">Empresa</option>
                                    <option value="personalizado">Solución Personalizada</option>
                                </select>
                            </div>
                            
                            <button type="submit" class="form-button">Enviar Mensaje</button>
                        </form>
                    </div>
                </div>
            </div>
            
            <!-- Mapa -->
            <div class="map-container hidden">
                <div class="map-placeholder">
                    <i class="fas fa-map-marked-alt"></i>
                    <h3>Ubicación de Nuestras Oficinas</h3>
                    <p>Silicon Valley, California</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer id="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>ChronoBot</h3>
                    <p>El asistente de calendario inteligente que revoluciona la gestión del tiempo. Automatiza tu agenda y enfócate en lo que realmente importa.</p>
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-linkedin"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-discord"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Contacto</h3>
                    <ul class="contact-info-list">
                        <li><i class="fas fa-envelope"></i> info@chronobot.com</li>
                        <li><i class="fas fa-phone"></i> +1 (555) 123-4567</li>
                        <li><i class="fas fa-map-marker-alt"></i> Silicon Valley, CA</li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Suscríbete</h3>
                    <p>Recibe las últimas actualizaciones y ofertas especiales directamente en tu correo.</p>
                    <button class="cta-button" id="subscribe-btn" style="padding: 12px 25px; font-size: 1rem;">Obtener Ofertas</button>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 ChronoBot. Todos los derechos reservados. | Diseño futurista con efectos 3D</p>
            </div>
        </div>
    </footer>
    
    <!-- Modal de demostración -->
    <div class="modal" id="demo-modal">
        <div class="modal-content">
            <span class="close-modal" id="close-modal">&times;</span>
            <h2>Demo de ChronoBot</h2>
            <p>Interactúa con el asistente virtual para gestionar tu calendario. Escribe un comando como "Programar reunión el lunes a las 3 PM" y observa cómo ChronoBot responde.</p>
            
            <div class="demo-placeholder">
                <i class="fas fa-robot"></i>
            </div>
            
            <div class="demo-interface">
                <input type="text" id="demo-input" placeholder="Escribe un comando para ChronoBot..." style="width: 100%; padding: 15px; background-color: rgba(255,255,255,0.1); border: 1px solid var(--primary-color); border-radius: 8px; color: white; font-size: 1rem; margin-bottom: 20px;">
                <button id="demo-send" class="cta-button" style="padding: 12px 30px;">Enviar</button>
            </div>
            
            <div id="demo-response" style="margin-top: 20px; padding: 15px; background-color: rgba(0, 243, 255, 0.1); border-radius: 8px; border-left: 3px solid var(--primary-color); display: none;">
                <p><strong>ChronoBot:</strong> <span id="response-text">He programado una reunión para el lunes a las 3 PM en tu calendario.</span></p>
            </div>
        </div>
    </div>

    <script>
        // Elementos del DOM
        const header = document.getElementById('header');
        const mobileMenuBtn = document.getElementById('mobile-menu-btn');
        const navMenu = document.getElementById('nav-menu');
        const demoBtn = document.getElementById('demo-btn');
        const demoModal = document.getElementById('demo-modal');
        const closeModal = document.getElementById('close-modal');
        const demoInput = document.getElementById('demo-input');
        const demoSend = document.getElementById('demo-send');
        const demoResponse = document.getElementById('demo-response');
        const responseText = document.getElementById('response-text');
        const subscribeBtn = document.getElementById('subscribe-btn');
        const offerBanner = document.getElementById('offer-banner');
        const closeOffer = document.getElementById('close-offer');
        const pricingButtons = document.querySelectorAll('.pricing-button');
        const contactForm = document.getElementById('contact-form');
        
        // Contador regresivo
        const daysElement = document.getElementById('days');
        const hoursElement = document.getElementById('hours');
        const minutesElement = document.getElementById('minutes');
        const secondsElement = document.getElementById('seconds');
        
        // Fecha objetivo (3 días desde ahora)
        const countdownDate = new Date();
        countdownDate.setDate(countdownDate.getDate() + 3);
        countdownDate.setHours(23, 59, 59, 0);
        
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = countdownDate - now;
            
            if (distance < 0) {
                // Si el tiempo ha expirado, reiniciar
                countdownDate.setDate(countdownDate.getDate() + 3);
                return;
            }
            
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);
            
            daysElement.textContent = days.toString().padStart(2, '0');
            hoursElement.textContent = hours.toString().padStart(2, '0');
            minutesElement.textContent = minutes.toString().padStart(2, '0');
            secondsElement.textContent = seconds.toString().padStart(2, '0');
        }
        
        // Crear partículas flotantes
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Tamaño aleatorio entre 2 y 6px
                const size = Math.random() * 4 + 2;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                
                // Posición aleatoria
                particle.style.left = `${Math.random() * 100}vw`;
                particle.style.top = `${Math.random() * 100}vh`;
                
                // Color aleatorio
                const colors = ['#00f3ff', '#9d4edd', '#00ff9d'];
                const color = colors[Math.floor(Math.random() * colors.length)];
                particle.style.backgroundColor = color;
                
                // Animación con retardo aleatorio
                particle.style.animationDelay = `${Math.random() * 20}s`;
                
                particlesContainer.appendChild(particle);
            }
        }
        
        // Efecto de scroll en header
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
        
        // Menú móvil
        mobileMenuBtn.addEventListener('click', () => {
            navMenu.classList.toggle('active');
            mobileMenuBtn.innerHTML = navMenu.classList.contains('active') 
                ? '<i class="fas fa-times"></i>' 
                : '<i class="fas fa-bars"></i>';
        });
        
        // Cerrar menú al hacer clic en un enlace
        document.querySelectorAll('.nav-menu a').forEach(link => {
            link.addEventListener('click', () => {
                navMenu.classList.remove('active');
                mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
            });
        });
        
        // Animaciones al hacer scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('show');
                }
            });
        }, observerOptions);
        
        // Observar elementos con clase 'hidden'
        document.querySelectorAll('.hidden').forEach(el => {
            observer.observe(el);
        });
        
        // Modal de demostración
        demoBtn.addEventListener('click', () => {
            demoModal.style.display = 'flex';
            demoInput.focus();
        });
        
        closeModal.addEventListener('click', () => {
            demoModal.style.display = 'none';
            demoResponse.style.display = 'none';
        });
        
        // Cerrar modal al hacer clic fuera
        window.addEventListener('click', (e) => {
            if (e.target === demoModal) {
                demoModal.style.display = 'none';
                demoResponse.style.display = 'none';
            }
        });
        
        // Cerrar banner de oferta
        closeOffer.addEventListener('click', () => {
            offerBanner.style.display = 'none';
        });
        
        // Botones de precios
        pricingButtons.forEach(button => {
            button.addEventListener('click', () => {
                const plan = button.getAttribute('data-plan');
                let message = '';
                
                switch(plan) {
                    case 'basico':
                        message = "¡Excelente elección! Estás a punto de comenzar con el plan Básico de ChronoBot. Te redirigiremos a la página de pago seguro.";
                        break;
                    case 'profesional':
                        message = "¡Fantástico! Has seleccionado el plan Profesional con 50% de descuento. Esta oferta es por tiempo limitado. Te redirigiremos a la página de pago seguro.";
                        break;
                    case 'empresa':
                        message = "¡Perfecto para tu organización! Un representante de ventas se contactará contigo en menos de 24 horas para personalizar la solución para tu empresa.";
                        break;
                    default:
                        message = "Te redirigiremos a nuestra página de suscripción.";
                }
                
                alert(message);
                
                // Simulación de redirección a página de pago
                if (plan !== 'empresa') {
                    setTimeout(() => {
                        alert("(Simulación) Redirigiendo a página de pago seguro... En una implementación real, aquí se procesaría el pago.");
                    }, 500);
                }
            });
        });
        
        // Formulario de contacto
        if (contactForm) {
            contactForm.addEventListener('submit', (e) => {
                e.preventDefault();
                
                // Obtener valores del formulario
                const name = document.getElementById('name').value;
                const email = document.getElementById('email').value;
                const subject = document.getElementById('subject').value;
                const message = document.getElementById('message').value;
                const plan = document.getElementById('plan').value;
                
                // Validación simple
                if (!name || !email || !subject || !message) {
                    alert("Por favor, completa todos los campos requeridos.");
                    return;
                }
                
                // Simular envío del formulario
                alert(`¡Gracias ${name}! Hemos recibido tu mensaje sobre "${subject}". Te contactaremos en ${email} en menos de 24 horas.`);
                
                // Limpiar formulario
                contactForm.reset();
                
                // Mostrar confirmación visual
                const submitButton = contactForm.querySelector('.form-button');
                const originalText = submitButton.textContent;
                submitButton.textContent = "¡Mensaje Enviado!";
                submitButton.style.background = "linear-gradient(45deg, var(--accent-color), var(--primary-color))";
                
                setTimeout(() => {
                    submitButton.textContent = originalText;
                    submitButton.style.background = "linear-gradient(45deg, var(--primary-color), var(--secondary-color))";
                }, 3000);
            });
        }
        
        // Simular respuesta del bot
        demoSend.addEventListener('click', simulateBotResponse);
        demoInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                simulateBotResponse();
            }
        });
        
        function simulateBotResponse() {
            const command = demoInput.value.toLowerCase().trim();
            let response = "";
            
            if (command.includes('reunión') || command.includes('evento') || command.includes('cita')) {
                if (command.includes('añadir') || command.includes('programar') || command.includes('crear')) {
                    response = "He programado una nueva reunión en tu calendario para mañana a las 10:00 AM. ¿Quieres que envíe invitaciones a los participantes?";
                } else if (command.includes('eliminar') || command.includes('cancelar') || command.includes('borrar')) {
                    response = "He eliminado la reunión de mañana a las 10:00 AM de tu calendario. También he notificado a los participantes sobre la cancelación.";
                } else if (command.includes('modificar') || command.includes('cambiar') || command.includes('mover')) {
                    response = "He cambiado la reunión de mañana a las 2:00 PM. Todos los participantes han sido notificados del cambio.";
                }
            } else if (command.includes('disponibilidad') || command.includes('horario') || command.includes('tiempo libre')) {
                response = "Tienes horario disponible el jueves de 2:00 PM a 4:00 PM y el viernes por la mañana. ¿Quieres programar algo en alguno de esos espacios?";
            } else if (command.includes('recordatorio') || command.includes('recordar') || command.includes('notificación')) {
                response = "He configurado un recordatorio para 15 minutos antes de cada reunión. También te enviaré una notificación por correo electrónico.";
            } else if (command.includes('hola') || command.includes('hi') || command.includes('hello')) {
                response = "¡Hola! Soy ChronoBot, tu asistente de calendario. Puedo ayudarte a programar reuniones, consultar tu disponibilidad o configurar recordatorios. ¿En qué puedo ayudarte?";
            } else if (command.includes('precio') || command.includes('costo') || command.includes('plan')) {
                response = "Tenemos planes desde $9/mes. El plan Profesional (con 50% de descuento) incluye todas las funciones avanzadas por solo $19/mes. ¿Te gustaría conocer más detalles?";
            } else if (command.includes('contacto') || command.includes('soporte') || command.includes('ayuda')) {
                response = "Puedes contactar a nuestro equipo de soporte en soporte@chronobot.com o llamar al +1 (555) 123-4567. También puedes completar el formulario de contacto en nuestra página.";
            } else {
                response = "He procesado tu solicitud. Como ejemplo, he añadido un evento de demostración a tu calendario para mostrarte cómo funciona ChronoBot.";
            }
            
            responseText.textContent = response;
            demoResponse.style.display = 'block';
            demoInput.value = '';
            
            // Desplazar hacia la respuesta
            demoResponse.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
        }
        
        // Botón de suscripción
        subscribeBtn.addEventListener('click', () => {
            const email = prompt("¡Obtén ofertas exclusivas! Introduce tu email para recibir un 20% adicional de descuento:");
            if (email && email.includes('@')) {
                alert(`¡Gracias! Hemos enviado un código de descuento al 20% a: ${email}. Revisa tu bandeja de entrada.`);
            } else if (email) {
                alert("Por favor, introduce un email válido para recibir ofertas especiales.");
            }
        });
        
        // Efecto de parallax sutil en elementos
        window.addEventListener('mousemove', (e) => {
            const x = (window.innerWidth - e.pageX * 2) / 100;
            const y = (window.innerHeight - e.pageY * 2) / 100;
            
            const floatingElements = document.querySelectorAll('.feature-card, .screenshot-item, .testimonial-card, .pricing-card');
            floatingElements.forEach(el => {
                el.style.transform = `translateY(${y/10}px) translateX(${x/10}px)`;
            });
        });
        
        // Inicializar partículas al cargar la página
        window.addEventListener('DOMContentLoaded', () => {
            createParticles();
            
            // Iniciar contador regresivo
            updateCountdown();
            setInterval(updateCountdown, 1000);
            
            // Asegurar que las animaciones se activen después de un breve retraso
            setTimeout(() => {
                document.querySelectorAll('.hidden').forEach(el => {
                    el.style.transitionDelay = `${Math.random() * 0.5}s`;
                });
            }, 300);
            
            // Mostrar testimonio destacado automáticamente
            setTimeout(() => {
                const popularPlan = document.querySelector('.pricing-card.popular');
                if (popularPlan) {
                    popularPlan.style.animation = 'pulse 2s infinite';
                }
            }, 2000);
        });
        
        // Efecto de pulso para el plan popular
        const style = document.createElement('style');
        style.textContent = `
            @keyframes pulse {
                0% { box-shadow: 0 0 0 0 rgba(0, 255, 157, 0.7); }
                70% { box-shadow: 0 0 0 10px rgba(0, 255, 157, 0); }
                100% { box-shadow: 0 0 0 0 rgba(0, 255, 157, 0); }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
