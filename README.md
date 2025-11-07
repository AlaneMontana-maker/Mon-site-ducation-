
<!DOCTYPE html>

<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Génie du Futur - Plateforme de Révision Interactive</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

```
    body {
        font-family: 'Inter', 'Segoe UI', sans-serif;
        background: #1a1a2e;
        color: #ffffff;
        overflow-x: hidden;
        position: relative;
    }

    /* Fond animé avec particules */
    .background-animation {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: -1;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
        opacity: 0.15;
    }

    .particles {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        z-index: -1;
    }

    .particle {
        position: absolute;
        width: 4px;
        height: 4px;
        background: rgba(255, 255, 255, 0.5);
        border-radius: 50%;
        animation: float 15s infinite ease-in-out;
    }

    @keyframes float {
        0%, 100% { transform: translateY(0) translateX(0); }
        50% { transform: translateY(-100px) translateX(100px); }
    }

    /* Header moderne */
    header {
        background: rgba(26, 26, 46, 0.98);
        backdrop-filter: blur(20px);
        padding: 1rem 0;
        box-shadow: 0 4px 30px rgba(102, 126, 234, 0.5);
        position: sticky;
        top: 0;
        z-index: 1000;
        border-bottom: 2px solid rgba(102, 126, 234, 0.5);
    }

    nav {
        max-width: 1400px;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 2rem;
    }

    .logo {
        font-size: 2rem;
        font-weight: 800;
        background: linear-gradient(135deg, #667eea 0%, #f093fb 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        display: flex;
        align-items: center;
        gap: 0.5rem;
        cursor: pointer;
        transition: transform 0.3s ease;
    }

    .logo:hover {
        transform: scale(1.05);
    }

    .nav-links {
        display: flex;
        gap: 2rem;
        list-style: none;
        align-items: center;
    }

    .nav-links a {
        text-decoration: none;
        color: #ffffff;
        font-weight: 600;
        transition: all 0.3s ease;
        padding: 0.5rem 1rem;
        border-radius: 8px;
        position: relative;
    }

    .nav-links a:hover {
        background: rgba(102, 126, 234, 0.3);
        transform: translateY(-2px);
        color: #f093fb;
    }

    /* Barre de recherche avancée */
    .search-container {
        max-width: 1400px;
        margin: 3rem auto;
        padding: 0 2rem;
    }

    .search-box {
        position: relative;
        width: 100%;
        max-width: 800px;
        margin: 0 auto;
    }

    .search-input {
        width: 100%;
        padding: 1.5rem 4rem 1.5rem 4rem;
        background: rgba(255, 255, 255, 0.15);
        border: 2px solid rgba(102, 126, 234, 0.5);
        border-radius: 50px;
        color: #ffffff;
        font-size: 1.1rem;
        backdrop-filter: blur(10px);
        transition: all 0.3s ease;
        outline: none;
    }

    .search-input::placeholder {
        color: rgba(255, 255, 255, 0.7);
    }

    .search-input:focus {
        border-color: #f093fb;
        box-shadow: 0 0 30px rgba(240, 147, 251, 0.6);
        background: rgba(255, 255, 255, 0.2);
    }

    .search-icon {
        position: absolute;
        left: 1.5rem;
        top: 50%;
        transform: translateY(-50%);
        font-size: 1.5rem;
        color: #f093fb;
    }

    .filter-icon {
        position: absolute;
        right: 1.5rem;
        top: 50%;
        transform: translateY(-50%);
        font-size: 1.5rem;
        color: #f093fb;
        cursor: pointer;
        transition: all 0.3s ease;
    }

    .filter-icon:hover {
        transform: translateY(-50%) scale(1.2);
    }

    /* Filtres rapides */
    .quick-filters {
        display: flex;
        gap: 1rem;
        justify-content: center;
        margin-top: 1.5rem;
        flex-wrap: wrap;
    }

    .filter-chip {
        padding: 0.7rem 1.5rem;
        background: rgba(102, 126, 234, 0.25);
        border: 2px solid rgba(102, 126, 234, 0.5);
        border-radius: 25px;
        color: #ffffff;
        cursor: pointer;
        transition: all 0.3s ease;
        font-weight: 600;
    }

    .filter-chip:hover {
        background: rgba(240, 147, 251, 0.3);
        border-color: #f093fb;
        transform: translateY(-3px);
        box-shadow: 0 5px 20px rgba(240, 147, 251, 0.5);
    }

    .filter-chip.active {
        background: linear-gradient(135deg, #667eea 0%, #f093fb 100%);
        border-color: #f093fb;
        color: #ffffff;
    }

    /* Hero section modernisée */
    .hero {
        text-align: center;
        padding: 4rem 2rem;
        position: relative;
    }

    .hero h1 {
        font-size: 4rem;
        margin-bottom: 1rem;
        background: linear-gradient(135deg, #fff 0%, #667eea 50%, #f093fb 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        animation: gradientShift 3s ease infinite;
    }

    @keyframes gradientShift {
        0%, 100% { filter: hue-rotate(0deg); }
        50% { filter: hue-rotate(20deg); }
    }

    .hero p {
        font-size: 1.3rem;
        color: #ffffff;
        max-width: 700px;
        margin: 0 auto;
        text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
    }

    /* Stats interactives */
    .stats-container {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 2rem;
        max-width: 1400px;
        margin: 3rem auto;
        padding: 0 2rem;
    }

    .stat-card {
        background: rgba(255, 255, 255, 0.08);
        backdrop-filter: blur(10px);
        border: 2px solid rgba(102, 126, 234, 0.5);
        border-radius: 20px;
        padding: 2rem;
        text-align: center;
        transition: all 0.3s ease;
        cursor: pointer;
    }

    .stat-card:hover {
        transform: translateY(-10px) scale(1.05);
        background: rgba(102, 126, 234, 0.25);
        box-shadow: 0 10px 40px rgba(102, 126, 234, 0.6);
        border-color: #f093fb;
    }

    .stat-number {
        font-size: 3rem;
        font-weight: 800;
        background: linear-gradient(135deg, #667eea 0%, #f093fb 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }

    .stat-label {
        font-size: 1.1rem;
        color: #ffffff;
        margin-top: 0.5rem;
        font-weight: 500;
    }

    /* Container principal */
    .container {
        max-width: 1400px;
        margin: 0 auto;
        padding: 2rem;
    }

    /* Cartes de classe ultra-modernes */
    .classes-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
        gap: 2rem;
        margin: 3rem 0;
    }

    .class-card {
        background: rgba(255, 255, 255, 0.08);
        backdrop-filter: blur(20px);
        border: 2px solid rgba(102, 126, 234, 0.5);
        border-radius: 25px;
        padding: 3rem;
        cursor: pointer;
        transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        position: relative;
        overflow: hidden;
    }

    .class-card::before {
        content: '';
        position: absolute;
        top: -50%;
        left: -50%;
        width: 200%;
        height: 200%;
        background: linear-gradient(135deg, transparent, rgba(240, 147, 251, 0.4), transparent);
        transform: rotate(45deg);
        transition: all 0.6s ease;
    }

    .class-card:hover::before {
        left: 100%;
    }

    .class-card:hover {
        transform: translateY(-15px) scale(1.02);
        border-color: #f093fb;
        box-shadow: 0 20px 60px rgba(240, 147, 251, 0.6);
        background: rgba(102, 126, 234, 0.15);
    }

    .class-icon {
        font-size: 4rem;
        margin-bottom: 1.5rem;
        display: block;
        animation: bounce 2s ease infinite;
    }

    @keyframes bounce {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(-10px); }
    }

    .class-card h3 {
        font-size: 2rem;
        margin-bottom: 1rem;
        color: #ffffff;
    }

    .class-card p {
        color: #ffffff;
        line-height: 1.6;
        font-weight: 400;
    }

    .class-badge {
        display: inline-block;
        padding: 0.5rem 1rem;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        border-radius: 20px;
        font-size: 0.9rem;
        margin-top: 1rem;
        font-weight: 600;
    }

    /* Matières avec effet glassmorphism */
    .subjects-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 2rem;
        margin: 2rem 0;
    }

    .subject-card {
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(15px);
        border: 2px solid rgba(102, 126, 234, 0.5);
        border-radius: 20px;
        padding: 2rem;
        cursor: pointer;
        transition: all 0.3s ease;
        position: relative;
    }

    .subject-card:hover {
        transform: translateY(-8px) rotate(-1deg);
        border-color: #f093fb;
        box-shadow: 0 15px 50px rgba(240, 147, 251, 0.5);
        background: rgba(102, 126, 234, 0.15);
    }

    .subject-icon {
        font-size: 3rem;
        margin-bottom: 1rem;
        display: block;
    }

    .subject-card h3 {
        font-size: 1.8rem;
        margin-bottom: 0.5rem;
        color: #ffffff;
    }

    .course-count {
        color: #ffffff;
        font-size: 0.9rem;
        font-weight: 500;
    }

    /* Liste de cours avec animations */
    .pdf-list {
        list-style: none;
        display: grid;
        gap: 1rem;
        margin-top: 2rem;
    }

    .pdf-item {
        background: rgba(255, 255, 255, 0.08);
        backdrop-filter: blur(10px);
        border: 2px solid rgba(102, 126, 234, 0.4);
        padding: 1.5rem;
        border-radius: 15px;
        cursor: pointer;
        transition: all 0.3s ease;
        display: flex;
        align-items: center;
        gap: 1.5rem;
        position: relative;
        overflow: hidden;
    }

    .pdf-item::before {
        content: '';
        position: absolute;
        left: 0;
        top: 0;
        height: 100%;
        width: 4px;
        background: linear-gradient(135deg, #667eea 0%, #f093fb 100%);
        transform: scaleY(0);
        transition: transform 0.3s ease;
    }

    .pdf-item:hover::before {
        transform: scaleY(1);
    }

    .pdf-item:hover {
        transform: translateX(10px);
        background: rgba(102, 126, 234, 0.15);
        border-color: #f093fb;
        box-shadow: 0 5px 20px rgba(240, 147, 251, 0.4);
    }

    .pdf-icon {
        font-size: 2.5rem;
        transition: transform 0.3s ease;
    }

    .pdf-item:hover .pdf-icon {
        transform: scale(1.2) rotate(5deg);
    }

    .pdf-info strong {
        display: block;
        font-size: 1.2rem;
        margin-bottom: 0.3rem;
        color: #ffffff;
    }

    .pdf-info p {
        color: #ffffff;
        font-size: 0.95rem;
        font-weight: 400;
    }

    /* Boutons modernes */
    .btn {
        padding: 1rem 2.5rem;
        border: none;
        border-radius: 50px;
        font-size: 1.1rem;
        font-weight: 600;
        cursor: pointer;
        transition: all 0.3s ease;
        position: relative;
        overflow: hidden;
        z-index: 1;
    }

    .btn-primary {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: #fff;
    }

    .btn-primary::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: linear-gradient(135deg, #764ba2 0%, #f093fb 100%);
        transition: left 0.4s ease;
        z-index: -1;
    }

    .btn-primary:hover::before {
        left: 0;
    }

    .btn-primary:hover {
        transform: translateY(-3px);
        box-shadow: 0 10px 30px rgba(102, 126, 234, 0.5);
    }

    .back-btn {
        background: rgba(255, 255, 255, 0.15);
        color: #ffffff;
        border: 2px solid rgba(240, 147, 251, 0.6);
        margin-bottom: 2rem;
    }

    .back-btn:hover {
        background: rgba(240, 147, 251, 0.3);
        transform: translateX(-5px);
        border-color: #f093fb;
    }

    /* Section biographie redesignée */
    .bio-section {
        background: rgba(255, 255, 255, 0.08);
        backdrop-filter: blur(20px);
        border: 2px solid rgba(102, 126, 234, 0.5);
        border-radius: 30px;
        padding: 4rem;
        margin: 3rem 0;
    }

    .bio-content {
        display: grid;
        grid-template-columns: 250px 1fr;
        gap: 3rem;
        align-items: center;
    }

    .bio-avatar {
        width: 250px;
        height: 250px;
        border-radius: 30px;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 6rem;
        box-shadow: 0 20px 60px rgba(102, 126, 234, 0.5);
        animation: float 3s ease-in-out infinite;
    }

    @keyframes float {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(-20px); }
    }

    .bio-text h2 {
        font-size: 3rem;
        margin-bottom: 1rem;
        background: linear-gradient(135deg, #fff 0%, #667eea 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }

    .bio-text p {
        line-height: 1.8;
        color: #ffffff;
        margin-bottom: 1rem;
        font-size: 1.1rem;
    }

    .contact-badges {
        display: flex;
        gap: 1rem;
        flex-wrap: wrap;
        margin-top: 2rem;
    }

    .contact-badge {
        background: rgba(102, 126, 234, 0.25);
        border: 2px solid rgba(240, 147, 251, 0.5);
        padding: 1rem 2rem;
        border-radius: 25px;
        backdrop-filter: blur(10px);
        transition: all 0.3s ease;
        color: #ffffff;
        font-weight: 500;
    }

    .contact-badge:hover {
        background: rgba(240, 147, 251, 0.3);
        transform: scale(1.05);
        border-color: #f093fb;
    }

    /* Section cachée */
    .hidden {
        display: none;
    }

    /* Footer moderne */
    footer {
        background: rgba(26, 26, 46, 0.98);
        backdrop-filter: blur(20px);
        padding: 3rem 2rem;
        text-align: center;
        margin-top: 5rem;
        border-top: 2px solid rgba(102, 126, 234, 0.5);
    }

    footer p {
        color: #ffffff;
        margin: 0.5rem 0;
        font-weight: 400;
    }

    /* Responsive */
    @media (max-width: 768px) {
        .hero h1 {
            font-size: 2.5rem;
        }

        .nav-links {
            gap: 1rem;
            flex-wrap: wrap;
        }

        .bio-content {
            grid-template-columns: 1fr;
            text-align: center;
        }

        .bio-avatar {
            margin: 0 auto;
        }

        .classes-grid,
        .subjects-grid {
            grid-template-columns: 1fr;
        }
    }

    /* Effet de chargement */
    .fade-in {
        animation: fadeIn 0.6s ease;
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
</style>
```

</head>
<body>
    <!-- Fond animé -->
    <div class="background-animation"></div>
    <div class="particles" id="particles"></div>

```
<!-- Header -->
<header>
    <nav>
        <div class="logo" onclick="goHome()">
            <span>🎓</span>
            <span>Génie du Futur</span>
        </div>
        <ul class="nav-links">
            <li><a href="#accueil">Accueil</a></li>
            <li><a href="#classes">Classes</a></li>
            <li><a href="#biographie">Biographie</a></li>
        </ul>
    </nav>
</header>

<!-- Barre de recherche -->
<div class="search-container">
    <div class="search-box">
        <span class="search-icon">🔍</span>
        <input type="text" class="search-input" id="searchInput" placeholder="Rechercher un cours, une matière, une classe..." oninput="handleSearch()">
        <span class="filter-icon" onclick="toggleFilters()">⚙️</span>
    </div>
    <div class="quick-filters" id="quickFilters">
        <div class="filter-chip active" onclick="filterBy('all')">Tout</div>
        <div class="filter-chip" onclick="filterBy('3eme')">3ème</div>
        <div class="filter-chip" onclick="filterBy('premiere')">Première</div>
        <div class="filter-chip" onclick="filterBy('terminale')">Terminale</div>
        <div class="filter-chip" onclick="filterBy('svt')">SVT</div>
        <div class="filter-chip" onclick="filterBy('maths')">Maths</div>
        <div class="filter-chip" onclick="filterBy('physique')">Physique</div>
    </div>
</div>

<!-- Hero -->
<div class="hero">
    <h1>Génie du Futur</h1>
    <p>Votre plateforme interactive de révision en ligne - Excellez dans vos études avec nos cours PDF de qualité</p>
</div>

<!-- Statistiques -->
<div class="stats-container">
    <div class="stat-card">
        <div class="stat-number">50+</div>
        <div class="stat-label">Cours disponibles</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">3</div>
        <div class="stat-label">Classes</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">7</div>
        <div class="stat-label">Matières</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">100%</div>
        <div class="stat-label">Gratuit</div>
    </div>
</div>

<!-- Container principal -->
<div class="container">
    <!-- Section Classes -->
    <div id="classesSection" class="fade-in">
        <h2 style="text-align: center; font-size: 2.5rem; margin-bottom: 2rem;">📚 Choisissez Votre Classe</h2>
        <div class="classes-grid">
            <div class="class-card" onclick="showClass('troisieme')" data-class="3eme">
                <span class="class-icon">📗</span>
                <h3>Classe de 3ème</h3>
                <p>Préparez-vous efficacement au Brevet avec nos cours complets et nos exercices</p>
                <span class="class-badge">Brevet</span>
            </div>
            <div class="class-card" onclick="showClass('premiere')" data-class="premiere">
                <span class="class-icon">📘</span>
                <h3>Première D/C</h3>
                <p>Programme scientifique complet pour réussir votre année de Première</p>
                <span class="class-badge">Sciences</span>
            </div>
            <div class="class-card" onclick="showClass('terminale')" data-class="terminale">
                <span class="class-icon">📕</span>
                <h3>Terminale D/C</h3>
                <p>Préparation intensive au Baccalauréat avec cours et révisions ciblées</p>
                <span class="class-badge">Bac</span>
            </div>
        </div>
    </div>

    <!-- Section Matières -->
    <div id="subjectsSection" class="hidden fade-in">
        <button class="btn back-btn" onclick="backToClasses()">← Retour aux classes</button>
        <h2 id="subjectsTitle" style="text-align: center; font-size: 2.5rem; margin-bottom: 2rem;"></h2>
        <div class="subjects-grid">
            <div class="subject-card" onclick="showCourses('svt')" data-subject="svt">
                <span class="subject-icon">🧬</span>
                <h3>SVT</h3>
                <p class="course-count">12 cours disponibles</p>
            </div>
            <div class="subject-card" onclick="showCourses('maths')" data-subject="maths">
                <span class="subject-icon">📐</span>
                <h3>Mathématiques</h3>
                <p class="course-count">15 cours disponibles</p>
            </div>
            <div class="subject-card" onclick="showCourses('physique')" data-subject="physique">
                <span class="subject-icon">⚛️</span>
                <h3>Physique-Chimie</h3>
                <p class="course-count">14 cours disponibles</p>
            </div>
            <div class="subject-card" onclick="showCourses('francais')" data-subject="francais">
                <span class="subject-icon">📖</span>
                <h3>Français</h3>
                <p class="course-count">10 cours disponibles</p>
            </div>
            <div class="subject-card" onclick="showCourses('anglais')" data-subject="anglais">
                <span class="subject-icon">🌍</span>
                <h3>Anglais</h3>
                <p class="course-count">8 cours disponibles</p>
            </div>
            <div class="subject-card" onclick="showCourses('histoire')" data-subject="histoire">
                <span class="subject-icon">🏛️</span>
                <h3>Histoire-Géo</h3>
                <p class="course-count">11 cours disponibles</p>
            </div>
        </div>
    </div>

    <!-- Section Cours -->
    <div id="coursesSection" class="hidden fade-in">
        <button class="btn back-btn" onclick="backToSubjects()">← Retour aux matières</button>
        <h2 id="coursesTitle" style="text-align: center; font-size: 2.5rem; margin-bottom: 2rem;"></h2>
        <ul class="pdf-list" id="coursesList"></ul>
    </div>

    <!-- Section Biographie -->
    <div class="bio-section" id="biographie">
        <h2 style="text-align: center; font-size: 2.5rem; margin-bottom: 3rem;">👨‍💻 À Propos du Créateur</h2>
        <div class="bio-content">
            <div class="bio-avatar">👨‍💻</div>
            <div class="bio-text">
                <h2>Ondo Obam</h2>
                <p><strong>Développeur Web & Étudiant Passionné</strong></p>
                <p>Créateur de "Génie du Futur", je suis un développeur web passionné par l'innovation technologique et l'éducation. Mon objectif est de rendre l'apprentissage accessible à tous grâce à des plateformes modernes et interactives.</p>
                <p>Actuellement élève au <strong>Lycée de Talla</strong>, je mets mes compétences en programmation au service de mes camarades pour créer des outils pédagogiques innovants qui facilitent la réussite scolaire.</p>
                <div class="contact-badges">
                    <div class="contact-badge">📞 658233250</div>
                    <div class="contact-badge">🏫 Lycée de Talla</div>
                    <div class="contact-badge">💻 Développeur Web</div>
                </div>
            </div>
        </div>
    </div>
</div>

<!-- Footer -->
<footer>
    <p style="font-size: 1.2rem; font-weight: 600;">🎓 Génie du Futur</p>
    <p>&copy; 2024 - Créé avec passion par Ondo Obam</p>
    <p>Plateforme éducative moderne pour l'excellence académique</p>
</footer>

<script>
    // Variables globales
    let currentClass = '';
    let currentSubject = '';

    // Données des cours
    const coursesData = {
        svt: [
            { id: 'svt1', title: 'La Cellule et ses Fonctions', desc: 'Structure et organisation cellulaire', icon: '🔬' },
            { id: 'svt2', title: 'La Génétique', desc: 'ADN, chromosomes et hérédité', icon: '🧬' },
            { id: 'svt3', title: 'Les Écosystèmes', desc: 'Biodiversité et interactions écologiques', icon: '🌿' },
            { id: 'svt4', title: 'Le Corps Humain', desc: 'Anatomie et physiologie', icon: '🫀' },
            { id: 'svt5', title: 'L\'Évolution', desc: 'Théories et mécanismes de l\'évolution', icon: '🦕' },
            { id: 'svt6', title: 'La Reproduction', desc: 'Reproduction humaine et végétale', icon: '🌸' }
        ],
        maths: [
            { id: 'math1', title: 'Algèbre', desc: 'Équations, fonctions et polynômes', icon: '🔢' },
            { id: 'math2', title: 'Géométrie', desc: 'Figures planes et solides', icon: '📐' },
            { id: 'math3', title: 'Analyse', desc: 'Limites, dérivées et intégrales', icon: '📊' },
            { id: 'math4', title: 'Statistiques et Probabilités', desc: 'Analyse de données et probabilités', icon: '📈' },
            { id: 'math5', title: 'Trigonométrie', desc: 'Fonctions trigonométriques et applications', icon: '📏' },
            { id: 'math6', title: 'Suites Numériques', desc: 'Suites arithmétiques et géométriques', icon: '🔄' }
        ],
        physique: [
            { id: 'phys1', title: 'Mécanique', desc: 'Forces, mouvements et énergie', icon: '⚙️' },
            { id: 'phys2', title: 'Électricité', desc: 'Circuits électriques et électromagnétisme', icon: '⚡' },
            { id: 'phys3', title: 'Chimie Organique', desc: 'Molécules et réactions organiques', icon: '🧪' },
            { id: 'phys4', title: 'Chimie Minérale', desc: 'Atomes, ions et réactions chimiques', icon: '⚗️' },
            { id: 'phys5', title: 'Optique', desc: 'Lumière, réflexion et réfraction', icon: '🔦' },
            { id: 'phys6', title: 'Thermodynamique', desc: 'Chaleur, température et énergie', icon: '🌡️' }
        ],
        francais: [
            { id: 'fr1', title: 'Grammaire', desc: 'Syntaxe et structure de la langue', icon: '📝' },
            { id: 'fr2', title: 'Littérature', desc: 'Analyse d\'œuvres littéraires', icon: '📚' },
            { id: 'fr3', title: 'Expression Écrite', desc: 'Rédaction et dissertation', icon: '✍️' },
            { id: 'fr4', title: 'Conjugaison', desc: 'Temps et modes verbaux', icon: '⏰' }
        ],
        anglais: [
            { id: 'eng1', title: 'Grammar', desc: 'English grammar rules', icon: '🔤' },
            { id: 'eng2', title: 'Vocabulary', desc: 'Essential vocabulary and expressions', icon: '📖' },
            { id: 'eng3', title: 'Conversation', desc: 'Speaking and listening skills', icon: '💬' },
            { id: 'eng4', title: 'Writing', desc: 'Essays and compositions', icon: '✏️' }
        ],
        histoire: [
            { id: 'hist1', title: 'Histoire Moderne', desc: 'XVIIIe et XIXe siècles', icon: '🏰' },
            { id: 'hist2', title: 'Géographie Physique', desc: 'Relief, climat et environnement', icon: '🗺️' },
            { id: 'hist3', title: 'Géopolitique', desc: 'Enjeux mondiaux contemporains', icon: '🌐' },
            { id: 'hist4', title: 'Histoire Contemporaine', desc: 'XXe et XXIe siècles', icon: '📰' }
        ]
    };

    // Création des particules animées
    function createParticles() {
        const container = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.top = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            container.appendChild(particle);
        }
    }

    // Navigation
    function goHome() {
        document.getElementById('classesSection').classList.remove('hidden');
        document.getElementById('subjectsSection').classList.add('hidden');
        document.getElementById('coursesSection').classList.add('hidden');
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function showClass(className) {
        currentClass = className;
        const titles = {
            'troisieme': '📗 Matières - Classe de 3ème',
            'premiere': '📘 Matières - Première D/C',
            'terminale': '📕 Matières - Terminale D/C'
        };
        
        document.getElementById('subjectsTitle').textContent = titles[className];
        document.getElementById('classesSection').classList.add('hidden');
        document.getElementById('subjectsSection').classList.remove('hidden');
        document.getElementById('coursesSection').classList.add('hidden');
        
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function backToClasses() {
        document.getElementById('classesSection').classList.remove('hidden');
        document.getElementById('subjectsSection').classList.add('hidden');
        document.getElementById('coursesSection').classList.add('hidden');
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function showCourses(subject) {
        currentSubject = subject;
        const subjectNames = {
            'svt': '🧬 Cours de SVT',
            'maths': '📐 Cours de Mathématiques',
            'physique': '⚛️ Cours de Physique-Chimie',
            'francais': '📖 Cours de Français',
            'anglais': '🌍 Cours d\'Anglais',
            'histoire': '🏛️ Cours d\'Histoire-Géographie'
        };
        
        document.getElementById('coursesTitle').textContent = subjectNames[subject];
        document.getElementById('subjectsSection').classList.add('hidden');
        document.getElementById('coursesSection').classList.remove('hidden');
        
        displayCourses(subject);
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function backToSubjects() {
        document.getElementById('subjectsSection').classList.remove('hidden');
        document.getElementById('coursesSection').classList.add('hidden');
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function displayCourses(subject) {
        const coursesList = document.getElementById('coursesList');
        coursesList.innerHTML = '';
        
        const courses = coursesData[subject] || [];
        courses.forEach(course => {
            const li = document.createElement('li');
            li.className = 'pdf-item';
            li.onclick = () => openPDF(course);
            li.innerHTML = `
                <span class="pdf-icon">${course.icon}</span>
                <div class="pdf-info">
                    <strong>${course.title}</strong>
                    <p>${course.desc}</p>
                </div>
            `;
            coursesList.appendChild(li);
        });
    }

    function openPDF(course) {
        const classNames = {
            'troisieme': 'Classe de 3ème',
            'premiere': 'Première D/C',
            'terminale': 'Terminale D/C'
        };
        
        alert(`📚 Ouverture du cours\n\n` +
              `Classe: ${classNames[currentClass]}\n` +
              `Cours: ${course.title}\n` +
              `Description: ${course.desc}\n\n` +
              `💡 Pour intégrer de vrais PDFs:\n` +
              `1. Hébergez vos fichiers PDF\n` +
              `2. Utilisez PDF.js ou Google Docs Viewer\n` +
              `3. Ajoutez un système de backend\n\n` +
              `Ceci est une démo interactive du design.`);
    }

    // Recherche interactive
    function handleSearch() {
        const searchTerm = document.getElementById('searchInput').value.toLowerCase();
        
        if (searchTerm.length === 0) return;

        // Recherche dans les classes
        const classCards = document.querySelectorAll('.class-card');
        classCards.forEach(card => {
            const text = card.textContent.toLowerCase();
            if (text.includes(searchTerm)) {
                card.style.display = 'block';
                card.style.animation = 'pulse 0.5s ease';
            } else {
                card.style.display = 'none';
            }
        });

        // Recherche dans les matières
        const subjectCards = document.querySelectorAll('.subject-card');
        subjectCards.forEach(card => {
            const text = card.textContent.toLowerCase();
            if (text.includes(searchTerm)) {
                card.style.display = 'block';
                card.style.animation = 'pulse 0.5s ease';
            } else {
                card.style.display = 'none';
            }
        });

        // Recherche dans les cours
        const pdfItems = document.querySelectorAll('.pdf-item');
        pdfItems.forEach(item => {
            const text = item.textContent.toLowerCase();
            if (text.includes(searchTerm)) {
                item.style.display = 'flex';
                item.style.animation = 'pulse 0.5s ease';
            } else {
                item.style.display = 'none';
            }
        });
    }

    // Filtres rapides
    function filterBy(category) {
        // Mettre à jour l'apparence des filtres
        document.querySelectorAll('.filter-chip').forEach(chip => {
            chip.classList.remove('active');
        });
        event.target.classList.add('active');

        // Réinitialiser tous les éléments
        document.querySelectorAll('.class-card, .subject-card, .pdf-item').forEach(el => {
            el.style.display = '';
        });

        if (category === 'all') return;

        // Filtrer les classes
        if (['3eme', 'premiere', 'terminale'].includes(category)) {
            document.querySelectorAll('.class-card').forEach(card => {
                if (!card.getAttribute('data-class').includes(category)) {
                    card.style.display = 'none';
                }
            });
        }

        // Filtrer les matières
        if (['svt', 'maths', 'physique'].includes(category)) {
            document.querySelectorAll('.subject-card').forEach(card => {
                if (card.getAttribute('data-subject') !== category) {
                    card.style.display = 'none';
                }
            });
        }
    }

    function toggleFilters() {
        const filters = document.getElementById('quickFilters');
        filters.style.display = filters.style.display === 'none' ? 'flex' : 'none';
    }

    // Navigation smooth
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
            e.preventDefault();
            const target = document.querySelector(this.getAttribute('href'));
            if (target) {
                target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        });
    });

    // Animation au scroll
    const observerOptions = {
        threshold: 0.1,
        rootMargin: '0px 0px -100px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.style.opacity = '1';
                entry.target.style.transform = 'translateY(0)';
            }
        });
    }, observerOptions);

    // Initialisation
    document.addEventListener('DOMContentLoaded', function() {
        createParticles();
        
        // Observer les éléments
        document.querySelectorAll('.class-card, .subject-card, .stat-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });
    });

    // Animation pulse pour la recherche
    const style = document.createElement('style');
    style.textContent = `
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
    `;
    document.head.appendChild(style);
</script>
```

</body>
</html>