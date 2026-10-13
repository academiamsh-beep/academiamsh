[index.html](https://github.com/user-attachments/files/33399830/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Academia María Soledad Herrera</title>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Alex+Brush&family=Montserrat:wght@300;400;500;600&family=Playfair+Display:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">

    <style>
        /* --- VARIABLES DE COLOR & PALETA PINAMAR --- */
        :root {
            --color-arena-soft: #fcf9f5;
            --color-arena: #f4eee0;
            --color-arena-dark: #e8ded0;
            --color-mar: #2b4c59;
            --color-mar-dark: #1a333d;
            --color-madera: #8c6d58;
            --color-salvia: #8ba88e;
            --color-salvia-light: #eaf1eb;
            --color-dorado: #d4af37;
            --color-dorado-hover: #b89628;
            --color-blanco: #ffffff;
            --color-texto: #333333;
            --color-texto-suave: #666666;
            
            --font-serif: 'Playfair Display', Georgia, serif;
            --font-sans: 'Montserrat', sans-serif;
            --font-artistic: 'Alex Brush', cursive;
            
            --transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
            --shadow-soft: 0 10px 30px rgba(0,0,0,0.05);
            --shadow-medium: 0 15px 35px rgba(43, 76, 89, 0.08);
            --radius-main: 16px;
        }

        /* --- RESET Y BASE --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-sans);
            background-color: var(--color-arena-soft);
            color: var(--color-texto);
            line-height: 1.7;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: var(--font-serif);
            color: var(--color-mar);
            font-weight: 600;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        ul {
            list-style: none;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 25px;
        }

        .section-padding {
            padding: 100px 0;
        }

        .text-center {
            text-align: center;
        }

        .section-subtitle {
            font-family: var(--font-artistic);
            font-size: 2.2rem;
            color: var(--color-madera);
            margin-bottom: 5px;
            display: block;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 20px;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 50px;
            height: 2px;
            background-color: var(--color-dorado);
            margin: 15px auto 0;
        }

        /* --- BOTONES --- */
        .btn {
            display: inline-block;
            padding: 16px 36px;
            border-radius: 50px;
            font-family: var(--font-sans);
            font-weight: 500;
            font-size: 0.95rem;
            letter-spacing: 1px;
            text-transform: uppercase;
            transition: var(--transition);
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background-color: var(--color-mar);
            color: var(--color-blanco);
            box-shadow: 0 8px 20px rgba(43, 76, 89, 0.2);
        }

        .btn-primary:hover {
            background-color: var(--color-mar-dark);
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(43, 76, 89, 0.3);
        }

        .btn-gold {
            background-color: var(--color-dorado);
            color: var(--color-blanco);
        }

        .btn-gold:hover {
            background-color: var(--color-dorado-hover);
            transform: translateY(-3px);
        }

        /* --- NAVBAR --- */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            transition: var(--transition);
            padding: 25px 0;
        }

        .navbar.scrolled {
            background-color: rgba(252, 249, 245, 0.95);
            backdrop-filter: blur(10px);
            padding: 15px 0;
            box-shadow: 0 5px 20px rgba(0,0,0,0.05);
        }

        .navbar-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .brand-logo {
            font-family: var(--font-serif);
            font-size: 1.4rem;
            color: var(--color-mar);
            font-weight: 600;
            letter-spacing: 1px;
        }

        .brand-logo span {
            color: var(--color-madera);
            font-family: var(--font-artistic);
            font-size: 1.8rem;
            font-weight: normal;
        }

        .nav-menu {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-link {
            font-size: 0.9rem;
            font-weight: 500;
            color: var(--color-texto);
            transition: var(--transition);
        }

        .nav-link:hover {
            color: var(--color-madera);
        }

        .menu-toggle {
            display: none;
            font-size: 1.5rem;
            color: var(--color-mar);
            cursor: pointer;
        }

        /* --- 1. HERO --- */
        .hero {
            height: 100vh;
            min-height: 650px;
            background: linear-gradient(135deg, rgba(244, 238, 224, 0.7) 0%, rgba(234, 241, 235, 0.6) 100%), 
                        url('https://images.unsplash.com/photo-1520523839897-bd0b52f945a0?q=80&w=1920&auto=format&fit=crop') center/cover no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            padding: 0 20px;
        }

        .hero-title {
            font-size: 3.5rem;
            color: var(--color-mar);
            margin-bottom: 15px;
            line-height: 1.2;
        }

        .hero-subtitle {
            font-size: 1.4rem;
            font-family: var(--font-serif);
            font-style: italic;
            color: var(--color-madera);
            margin-bottom: 35px;
        }

        /* --- 2. SOBRE MARÍA SOLEDAD --- */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-image {
            position: relative;
            border-radius: var(--radius-main);
            overflow: hidden;
            box-shadow: var(--shadow-medium);
        }

        .about-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: var(--transition);
        }

        .about-image:hover img {
            transform: scale(1.03);
        }

        .about-list {
            margin: 25px 0;
        }

        .about-list li {
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 0.95rem;
            color: var(--color-texto-suave);
        }

        .about-list i {
            color: var(--color-salvia);
        }

        /* --- 3. CURSO PRINCIPAL --- */
        .main-course {
            background-color: var(--color-arena);
            border-radius: 24px;
            padding: 60px;
            position: relative;
            box-shadow: var(--shadow-medium);
            border: 1px solid rgba(212, 175, 55, 0.2);
        }

        .course-badge {
            background-color: var(--color-salvia);
            color: var(--color-blanco);
            padding: 6px 16px;
            border-radius: 20px;
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            display: inline-block;
            margin-bottom: 15px;
        }

        .course-details {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
            padding: 20px 0;
            border-top: 1px solid var(--color-arena-dark);
            border-bottom: 1px solid var(--color-arena-dark);
        }

        .detail-item {
            text-align: center;
        }

        .detail-item i {
            font-size: 1.5rem;
            color: var(--color-madera);
            margin-bottom: 8px;
        }

        /* --- 4. BENEFICIOS --- */
        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .benefit-card {
            background: var(--color-blanco);
            padding: 35px 25px;
            border-radius: var(--radius-main);
            text-align: center;
            transition: var(--transition);
            box-shadow: var(--shadow-soft);
        }

        .benefit-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-medium);
        }

        .benefit-icon {
            width: 65px;
            height: 65px;
            background-color: var(--color-salvia-light);
            color: var(--color-mar);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            margin: 0 auto 20px;
        }

        /* --- 5. PRÓXIMOS CURSOS --- */
        .upcoming-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .upcoming-card {
            background: var(--color-blanco);
            border-radius: var(--radius-main);
            padding: 30px;
            border-left: 4px solid var(--color-salvia);
            transition: var(--transition);
            box-shadow: var(--shadow-soft);
        }

        .upcoming-card:hover {
            border-left-color: var(--color-dorado);
            transform: translateX(5px);
        }

        /* --- 6. TESTIMONIOS --- */
        .testimonials {
            background-color: var(--color-salvia-light);
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .testimonial-card {
            background-color: var(--color-blanco);
            padding: 35px;
            border-radius: var(--radius-main);
            box-shadow: var(--shadow-soft);
            position: relative;
        }

        .testimonial-text {
            font-style: italic;
            color: var(--color-texto-suave);
            margin-bottom: 20px;
            font-size: 0.95rem;
        }

        .author-name {
            font-family: var(--font-serif);
            font-weight: 600;
            color: var(--color-mar);
        }

        /* --- 7. FAQ --- */
        .faq-accordion {
            max-width: 800px;
            margin: 40px auto 0;
        }

        .faq-item {
            background-color: var(--color-blanco);
            border-radius: 10px;
            margin-bottom: 15px;
            box-shadow: var(--shadow-soft);
            overflow: hidden;
        }

        .faq-question {
            padding: 20px 25px;
            width: 100%;
            text-align: left;
            background: none;
            border: none;
            font-family: var(--font-serif);
            font-size: 1.1rem;
            color: var(--color-mar);
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
        }

        .faq-answer {
            padding: 0 25px;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out, padding 0.3s ease;
            color: var(--color-texto-suave);
            font-size: 0.95rem;
        }

        .faq-item.active .faq-answer {
            padding: 0 25px 20px;
            max-height: 200px;
        }

        .faq-item.active i {
            transform: rotate(180deg);
        }

        /* --- 8. CONTACTO --- */
        .contact-form {
            max-width: 650px;
            margin: 40px auto 0;
            background: var(--color-blanco);
            padding: 40px;
            border-radius: var(--radius-main);
            box-shadow: var(--shadow-medium);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-size: 0.9rem;
            color: var(--color-mar);
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 14px;
            border: 1px solid var(--color-arena-dark);
            border-radius: 8px;
            font-family: var(--font-sans);
            background-color: var(--color-arena-soft);
            transition: var(--transition);
        }

        .form-control:focus {
            outline: none;
            border-color: var(--color-salvia);
            background-color: var(--color-blanco);
        }

        /* --- 9. FOOTER --- */
        footer {
            background-color: var(--color-mar-dark);
            color: var(--color-arena);
            padding: 60px 0 30px;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 25px;
        }

        .social-links {
            display: flex;
            gap: 20px;
        }

        .social-icon {
            width: 45px;
            height: 45px;
            background-color: rgba(255,255,255,0.08);
            color: var(--color-arena);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .social-icon:hover {
            background-color: var(--color-dorado);
            color: var(--color-blanco);
            transform: translateY(-3px);
        }

        /* --- ANIMACIONES FADE-IN --- */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            .hero-title { font-size: 2.5rem; }
            .about-grid { grid-template-columns: 1fr; }
            .main-course { padding: 30px; }
            
            .nav-menu {
                position: fixed;
                top: 0;
                right: -100%;
                width: 75%;
                height: 100vh;
                background-color: var(--color-arena-soft);
                flex-direction: column;
                justify-content: center;
                transition: var(--transition);
                box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            }

            .nav-menu.active {
                right: 0;
            }

            .menu-toggle {
                display: block;
            }
        }
    </style>
</head>
<body>

    <!-- NAVBAR -->
    <nav class="navbar" id="navbar">
        <div class="container navbar-container">
            <a href="#" class="brand-logo">Academia <span>MSH</span></a>
            <div class="menu-toggle" id="menuToggle"><i class="fas fa-bars"></i></div>
            <ul class="nav-menu" id="navMenu">
                <li><a href="#about" class="nav-link">Sobre MSH</a></li>
                <li><a href="#curso" class="nav-link">Curso Principal</a></li>
                <li><a href="#beneficios" class="nav-link">Beneficios</a></li>
                <li><a href="#proximos" class="nav-link">Próximos Cursos</a></li>
                <li><a href="#contacto" class="nav-link">Contacto</a></li>
            </ul>
        </div>
    </nav>

    <!-- 1. HERO -->
    <section class="hero">
        <div class="hero-content fade-in">
            <h1 class="hero-title">Academia María Soledad Herrera</h1>
            <p class="hero-subtitle">"Volvé a conectar con vos a través de la música."</p>
            <a href="#curso" class="btn btn-primary">Comenzar hoy</a>
        </div>
    </section>

    <!-- 2. SOBRE MARÍA SOLEDAD HERRERA -->
    <section class="section-padding" id="about">
        <div class="container">
            <div class="about-grid">
                <div class="about-image fade-in">
                    <img src="https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?q=80&w=800&auto=format&fit=crop" alt="María Soledad Herrera">
                </div>
                <div class="about-text fade-in">
                    <span class="section-subtitle">Trayectoria & Vocación</span>
                    <h2 class="section-title" style="text-align: left;">Sobre María Soledad Herrera</h2>
                    <p>La música no es solo un conjunto de notas, es un camino de regreso a uno mismo. Mi misión es guiarte en ese descubrimiento con paciencia, técnica y sensibilidad.</p>
                    <ul class="about-list">
                        <li><i class="fas fa-music"></i> Pianista e Instrumentista en Música Popular.</li>
                        <li><i class="fas fa-microphone-alt"></i> Cantante y preparadora vocal.</li>
                        <li><i class="fas fa-graduation-cap"></i> Docente de Música con experiencia desde 2016.</li>
                        <li><i class="fas fa-book-reader"></i> Sólida Formación Pedagógica adaptada a cada alumno.</li>
                    </ul>
                    <p style="font-style: italic; color: var(--color-madera);">
                        "Tras años de trayectoria en aulas y escenarios, creé esta academia para ofrecer un espacio cálido e inspirador, libre de frustraciones, donde la música sea un refugio."
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- 3. CURSO PRINCIPAL -->
    <section class="section-padding" id="curso" style="background-color: var(--color-arena-soft);">
        <div class="container">
            <div class="main-course fade-in">
                <span class="course-badge">Programa Destacado</span>
                <h2>"Volver a vos con la música"</h2>
                <p style="font-size: 1.1rem; margin-top: 10px;">
                    Un recorrido transformador de ocho semanas diseñado para aprender piano, canto y expresión musical desde cero, a tu propio ritmo.
                </p>
                
                <div class="course-details">
                    <div class="detail-item">
                        <i class="far fa-calendar-alt"></i>
                        <h4>Duración</h4>
                        <p>8 Semanas</p>
                    </div>
                    <div class="detail-item">
                        <i class="fas fa-heart"></i>
                        <h4>Enfoque</h4>
                        <p>Integral y Emocional</p>
                    </div>
                    <div class="detail-item">
                        <i class="fas fa-user-graduate"></i>
                        <h4>Nivel</h4>
                        <p>Desde Cero</p>
                    </div>
                </div>

                <div class="text-center">
                    <a href="#contacto" class="btn btn-gold">Inscribirme al Programa</a>
                </div>
            </div>
        </div>
    </section>

    <!-- 4. BENEFICIOS -->
    <section class="section-padding" id="beneficios">
        <div class="container">
            <div class="text-center fade-in">
                <span class="section-subtitle">Transformación</span>
                <h2 class="section-title">Lo que lograrás en la Academia</h2>
            </div>
            <div class="benefits-grid">
                <div class="benefit-card fade-in">
                    <div class="benefit-icon"><i class="fas fa-drum"></i></div>
                    <h3>Aprender Piano</h3>
                    <p>Domina las bases del instrumento de manera fluida y amigable.</p>
                </div>
                <div class="benefit-card fade-in">
                    <div class="benefit-icon"><i class="fas fa-smile"></i></div>
                    <h3>Cantar con Confianza</h3>
                    <p>Libera tu voz natural perdiendo el miedo y la inhibición.</p>
                </div>
                <div class="benefit-card fade-in">
                    <div class="benefit-icon"><i class="fas fa-spa"></i></div>
                    <h3>Reducir el Estrés</h3>
                    <p>Encuentra en la práctica musical un momento diario de paz y foco.</p>
                </div>
                <div class="benefit-card fade-in">
                    <div class="benefit-icon"><i class="fas fa-paint-brush"></i></div>
                    <h3>Conectar con Emociones</h3>
                    <p>Usa la interpretación musical como canal de expresión personal.</p>
                </div>
                <div class="benefit-card fade-in">
                    <div class="benefit-icon"><i class="fas fa-compact-disc"></i></div>
                    <h3>Disfrutar la Música</h3>
                    <p>Goza del proceso de aprendizaje desde la primera nota.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 5. PRÓXIMOS CURSOS -->
    <section class="section-padding" id="proximos" style="background-color: var(--color-arena);">
        <div class="container">
            <div class="text-center fade-in">
                <span class="section-subtitle">Formación Continua</span>
                <h2 class="section-title">Próximos Cursos y Talleres</h2>
            </div>
            <div class="upcoming-grid">
                <div class="upcoming-card fade-in">
                    <h3>Piano para Cantar</h3>
                    <p style="margin-top: 10px; font-size: 0.9rem;">Aprende a acompañar tu voz de forma armónica y dinámica.</p>
                </div>
                <div class="upcoming-card fade-in">
                    <h3>Música para Docentes</h3>
                    <p style="margin-top: 10px; font-size: 0.9rem;">Herramientas pedagógico-musicales para aplicar en el aula.</p>
                </div>
                <div class="upcoming-card fade-in">
                    <h3>Folklore Argentino en Piano</h3>
                    <p style="margin-top: 10px; font-size: 0.9rem;">Ritmos, arreglos y sutilezas de nuestra música autóctona.</p>
                </div>
                <div class="upcoming-card fade-in">
                    <h3>Tango para Pianistas</h3>
                    <p style="margin-top: 10px; font-size: 0.9rem;">Técnicas de marcación, articulación y estilo tanguero.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 6. TESTIMONIOS -->
    <section class="section-padding testimonials">
        <div class="container">
            <div class="text-center fade-in">
                <span class="section-subtitle">Experiencias</span>
                <h2 class="section-title">Lo que dicen mis alumnos</h2>
            </div>
            <div class="testimonials-grid">
                <div class="testimonial-card fade-in">
                    <p class="testimonial-text">"Empecé desde cero a los 42 años creyendo que no era para mí. La paciencia de María Soledad e pedagogía hicieron que hoy tocar el piano sea mi momento favorito del día."</p>
                    <p class="author-name">— Laura M.</p>
                </div>
                <div class="testimonial-card fade-in">
                    <p class="testimonial-text">"El curso 'Volver a vos' me ayudó a soltar el miedo a cantar en público. La calidez del enfoque pedagógico te hace sentir en un ambiente seguro."</p>
                    <p class="author-name">— Carlos G.</p>
                </div>
                <div class="testimonial-card fade-in">
                    <p class="testimonial-text">"Como docente de aula, el taller de música me dio herramientas prácticas que aplico todas las semanas. Absolutamente recomendable."</p>
                    <p class="author-name">— Mariana R.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 7. PREGUNTAS FRECUENTES -->
    <section class="section-padding">
        <div class="container">
            <div class="text-center fade-in">
                <span class="section-subtitle">Dudas Frecuentes</span>
                <h2 class="section-title">Preguntas Frecuentes</h2>
            </div>
            <div class="faq-accordion fade-in">
                <div class="faq-item">
                    <button class="faq-question">¿Necesito tener conocimientos previos? <i class="fas fa-chevron-down"></i></button>
                    <div class="faq-answer">No, para nada. El curso principal está estructurado para acompañarte paso a paso partiendo desde cero absoluto.</div>
                </div>
                <div class="faq-item">
                    <button class="faq-question">¿Qué necesito para empezar las clases? <i class="fas fa-chevron-down"></i></button>
                    <div class="faq-answer">Un teclado o piano (de cualquier tipo para comenzar), ganas de aprender y una conexión a internet estable.</div>
                </div>
                <div class="faq-item">
                    <button class="faq-question">¿Las clases son en vivo o grabadas? <i class="fas fa-chevron-down"></i></button>
                    <div class="faq-answer">Contamos con una modalidad mixta: contenido grabado de alta calidad con seguimiento y mentoría en vivo para corregir técnicas.</div>
                </div>
                <div class="faq-item">
                    <button class="faq-question">¿Hay límite de edad para inscribirse? <i class="fas fa-chevron-down"></i></button>
                    <div class="faq-answer">No hay límites. La propuesta pedagógica está diseñada especialmente para jóvenes y adultos de cualquier edad.</div>
                </div>
                <div class="faq-item">
                    <button class="faq-question">¿Cuánto tiempo diario debo dedicarle? <i class="fas fa-chevron-down"></i></button>
                    <div class="faq-answer">Con dedicarle entre 15 y 20 minutos diarios notarás un avance constante y muy gratificante.</div>
                </div>
                <div class="faq-item">
                    <button class="faq-question">¿Cómo realizo el pago de la inscripción? <i class="fas fa-chevron-down"></i></button>
                    <div class="faq-answer">Aceptamos transferencias bancarias, tarjetas de crédito y plataformas digitales de pago internacionales.</div>
                </div>
            </div>
        </div>
    </section>

    <!-- 8. FORMULARIO DE CONTACTO -->
    <section class="section-padding" id="contacto" style="background-color: var(--color-arena-soft);">
        <div class="container">
            <div class="text-center fade-in">
                <span class="section-subtitle">Sigamos conectados</span>
                <h2 class="section-title">Formulario de Contacto</h2>
            </div>
            <form class="contact-form fade-in" id="contactForm">
                <div class="form-group">
                    <label for="name">Nombre Completo</label>
                    <input type="text" id="name" class="form-control" placeholder="Tu nombre" required>
                </div>
                <div class="form-group">
                    <label for="email">Correo Electrónico</label>
                    <input type="email" id="email" class="form-control" placeholder="tu@email.com" required>
                </div>
                <div class="form-group">
                    <label for="message">Mensaje</label>
                    <textarea id="message" rows="5" class="form-control" placeholder="Escribe tu consulta aquí..." required></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Enviar Mensaje</button>
            </form>
        </div>
    </section>

    <!-- 9. FOOTER -->
    <footer>
        <div class="container footer-content">
            <a href="#" class="brand-logo" style="color: var(--color-arena);">Academia <span style="color: var(--color-dorado);">MSH</span></a>
            <p style="font-size: 0.9rem; color: #a0b0b8;">María Soledad Herrera — Formación Musical Consciente</p>
            <div class="social-links">
                <a href="#" class="social-icon" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                <a href="#" class="social-icon" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                <a href="mailto:info@mariasoledadherrera.com" class="social-icon" aria-label="Email"><i class="far fa-envelope"></i></a>
            </div>
            <p style="font-size: 0.8rem; margin-top: 20px; opacity: 0.6;">&copy; 2026 Academia María Soledad Herrera. Todos los derechos reservados.</p>
        </div>
    </footer>

    <!-- JAVASCRIPT -->
    <script>
        // Transición del Navbar al hacer scroll
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Menú responsive toggle
        const menuToggle = document.getElementById('menuToggle');
        const navMenu = document.getElementById('navMenu');

        menuToggle.addEventListener('click', () => {
            navMenu.classList.toggle('active');
        });

        // Cierre de menú responsive al clickear un enlace
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                navMenu.classList.remove('active');
            });
        });

        // Acordeón FAQ
        const faqItems = document.querySelectorAll('.faq-item');
        faqItems.forEach(item => {
            const question = item.querySelector('.faq-question');
            question.addEventListener('click', () => {
                const isActive = item.classList.contains('active');
                faqItems.forEach(i => i.classList.remove('active'));
                if (!isActive) {
                    item.classList.add('active');
                }
            });
        });

        // Intersección / Animaciones Fade-In al Scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -50px 0px"
        };

        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(element => {
            observer.observe(element);
        });

        // Formulario Feedback Simulación
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('¡Gracias por tu mensaje! Nos pondremos en contacto contigo a la brevedad.');
            this.reset();
        });
    </script>
</body>
</html>
