<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal de Contribuyentes - Accesible y Multilingüe</title>
    <style>
        /* --- Estilos Generales --- */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }
        header {
            background-color: #00529B;
            color: white;
            padding: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        header h1 {
            margin: 0;
            font-size: 1.8em;
        }
        nav {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }
        nav a {
            color: white;
            text-decoration: none;
            padding: 8px 12px;
            border-radius: 4px;
        }
        nav a:hover {
            background-color: #003f70;
        }
        main {
            padding: 20px;
        }
        section {
            margin-bottom: 30px;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.1);
        }
        h2 {
            margin-top: 0;
        }
        /* --- Botones y Selectores --- */
        .button, select {
            padding: 8px 12px;
            border-radius: 5px;
            border: 1px solid #ccc;
            font-size: 1em;
        }
        .button {
            background-color: #00529B;
            color: white;
            cursor: pointer;
        }
        .button:hover {
            background-color: #003f70;
        }
        /* --- Audio Visual --- */
        audio, video {
            width: 100%;
            margin-top: 10px;
            border-radius: 5px;
        }
        /* --- Menús Desplegables --- */
        .submenu {
            display: none;
            margin-top: 10px;
        }
        .submenu.active {
            display: block;
        }
        /* --- Contraste alto / accesibilidad --- */
        .high-contrast {
            background-color: black !important;
            color: yellow !important;
        }
        .large-text {
            font-size: 1.4em !important;
        }
    </style>
</head>
<body>
    <header>
        <h1 id="title">Portal de Contribuyentes</h1>
        <div>
            <select id="languageSelect">
                <option value="es">Español</option>
                <option value="en">English</option>
                <option value="qu">Kichwa</option>
                <option value="sh">Shuar</option>
            </select>
            <button class="button" id="accessibilityButton">Modo Accesible</button>
        </div>
    </header>

    <nav>
        <a href="#info">Información</a>
        <a href="#tramites">Trámites</a>
        <a href="#videos">Videos Lengua de Señas</a>
        <a href="#contacto">Contacto</a>
    </nav>

    <main>
        <!-- Sección de Información -->
        <section id="info">
            <h2 id="infoTitle">Información del Contribuyente</h2>
            <p id="infoText">
                Bienvenido al portal de contribuyentes. Aquí encontrará información sobre registros, pagos, certificados y procedimientos actualizados.  
            </p>
            <button class="button" onclick="playAudio('infoAudio')">Escuchar Audio Explicativo</button>
            <audio id="infoAudio">
                <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
            </audio>
        </section>

        <!-- Sección de Trámites -->
        <section id="tramites">
            <h2 id="tramitesTitle">Trámites</h2>

            <div>
                <button class="button" onclick="toggleSubmenu('tramite1')">Registro de Contribuyente</button>
                <div class="submenu" id="tramite1">
                    <p>Requisitos:</p>
                    <ul>
                        <li>Documento de identidad</li>
                        <li>Formulario de registro</li>
                        <li>Comprobante de domicilio</li>
                        <li>Pago de tasas (si aplica)</li>
                    </ul>
                    <button class="button" onclick="playAudio('tramite1Audio')">Escuchar Audio</button>
                    <audio id="tramite1Audio">
                        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-2.mp3" type="audio/mpeg">
                    </audio>
                    <video controls>
                        <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
                        Su navegador no soporta videos.
                    </video>
                </div>
            </div>

            <div>
                <button class="button" onclick="toggleSubmenu('tramite2')">Pago de Impuestos</button>
                <div class="submenu" id="tramite2">
                    <p>Pasos para pagar impuestos:</p>
                    <ul>
                        <li>Ingresar al portal con su usuario</li>
                        <li>Seleccionar el impuesto correspondiente</li>
                        <li>Verificar datos y generar recibo</li>
                        <li>Realizar el pago en línea</li>
                    </ul>
                    <button class="button" onclick="playAudio('tramite2Audio')">Escuchar Audio</button>
                    <audio id="tramite2Audio">
                        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-3.mp3" type="audio/mpeg">
                    </audio>
                    <video controls>
                        <source src="https://www.w3schools.com/html/movie.mp4" type="video/mp4">
                        Su navegador no soporta videos.
                    </video>
                </div>
            </div>
        </section>

        <!-- Sección de Videos con Lengua de Señas -->
        <section id="videos">
            <h2 id="videosTitle">Videos Interactivos en Lengua de Señas</h2>
            <video controls>
                <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
                Su navegador no soporta videos.
            </video>
            <p>Estos videos explican los principales trámites con interpretación en lengua de señas.</p>
        </section>

        <!-- Sección de Contacto -->
        <section id="contacto">
            <h2 id="contactoTitle">Contacto</h2>
            <p>Correo: soporte@contribuyentes.gob</p>
            <p>Teléfono: +593 9 123 4567</p>
        </section>
    </main>

    <script>
        // --- Cambiar Idioma (ejemplo simple) ---
        const translations = {
            es: {
                title: "Portal de Contribuyentes",
                infoTitle: "Información del Contribuyente",
                infoText: "Bienvenido al portal de contribuyentes. Aquí encontrará información sobre registros, pagos, certificados y procedimientos actualizados.",
                tramitesTitle: "Trámites",
                videosTitle: "Videos Interactivos en Lengua de Señas",
                contactoTitle: "Contacto"
            },
            en: {
                title: "Taxpayer Portal",
                infoTitle: "Taxpayer Information",
                infoText: "Welcome to the taxpayer portal. Here you will find information about registration, payments, certificates, and updated procedures.",
                tramitesTitle: "Procedures",
                videosTitle: "Sign Language Interactive Videos",
                contactoTitle: "Contact"
            },
            qu: {
                title: "Rikchaykuna Portal",
                infoTitle: "Rikchaykuna Rikchay",
                infoText: "Kay portalmanta rikchaykuna, pagos, certificados, chaylla rikchaykuna rimaykuna.",
                tramitesTitle: "Rikchaykuna",
                videosTitle: "Rimay Kawsay Video",
                contactoTitle: "Ñukanchik Rimay"
            },
            sh: {
                title: "Contribuyente Portal",
                infoTitle: "Contribuyente Ining",
                infoText: "Achik platform, pagos, certificados, procesos.",
                tramitesTitle: "Trámites",
                videosTitle: "Videos Shuar",
                contactoTitle: "Contacto"
            }
        };

        document.getElementById('languageSelect').addEventListener('change', function() {
            const lang = this.value;
            document.getElementById('title').textContent = translations[lang].title;
            document.getElementById('infoTitle').textContent = translations[lang].infoTitle;
            document.getElementById('infoText').textContent = translations[lang].infoText;
            document.getElementById('tramitesTitle').textContent = translations[lang].tramitesTitle;
            document.getElementById('videosTitle').textContent = translations[lang].videosTitle;
            document.getElementById('contactoTitle').textContent = translations[lang].contactoTitle;
        });

        // --- Modo Accesible ---
        const accessibilityButton = document.getElementById('accessibilityButton');
        let accessibilityOn = false;
        accessibilityButton.addEventListener('click', () => {
            accessibilityOn = !accessibilityOn;
            if(accessibilityOn){
                document.body.classList.add('high-contrast');
                document.body.classList.add('large-text');
            } else {
                document.body.classList.remove('high-contrast');
                document.body.classList.remove('large-text');
            }
        });

        // --- Submenus desplegables ---
        function toggleSubmenu(id) {
            const submenu = document.getElementById(id);
            submenu.classList.toggle('active');
        }

        // --- Audio Explicativo ---
        function playAudio(id) {
            const audio = document.getElementById(id);
            audio.play();
        }
    </script>
</body>
</html>
