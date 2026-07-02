<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Mi Archivador</title>

    <link rel="stylesheet" href="/mi_archivador/css/styles.css">
        <link rel="stylesheet" href="/mi_archivador/css/tyles.css">

    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
</head>

<body>

<!-- =========================
        HEADER
========================= -->
<header>
    <h1>📁 Mi Archivador</h1>
</header>

<!-- =========================
         NAV
========================= -->
<nav>
    <a href="index.php">🏠 Inicio</a>
    <a href="index.php?action=subir">📤 Subir archivo</a>
</nav>

<!-- =========================
        SECTION PRINCIPAL
========================= -->
<section class="content">

    <!-- FLASH MESSAGE -->
    
    <h2>📂 Archivos subidos</h2>

    
   <ul class="file-list">

    
        <li class="file-card">

            <div class="file-left">

                <div class="file-icon">📄</div>

                <div class="file-info">
                    <h3>file_6a441a82768510.61863061.pdf</h3>

                    <span>📦 530.77 KB</span>
                    <span>📅 2026-06-30 21:35:30</span>
                </div>

            </div>

            <div class="file-actions">

                <a href="/mi_archivador/uploads/file_6a441a82768510.61863061.pdf" download>
                    ⬇ Descargar
                </a>

                <a href="index.php?action=eliminar&file=file_6a441a82768510.61863061.pdf"
                   onclick="return confirm('¿Eliminar archivo?')">
                    🗑 Eliminar
                </a>

            </div>

        </li>

    
        <li class="file-card">

            <div class="file-left">

                <div class="file-icon">📄</div>

                <div class="file-info">
                    <h3>file_6a441adc447090.18233883.pdf</h3>

                    <span>📦 530.77 KB</span>
                    <span>📅 2026-06-30 21:37:00</span>
                </div>

            </div>

            <div class="file-actions">

                <a href="/mi_archivador/uploads/file_6a441adc447090.18233883.pdf" download>
                    ⬇ Descargar
                </a>

                <a href="index.php?action=eliminar&file=file_6a441adc447090.18233883.pdf"
                   onclick="return confirm('¿Eliminar archivo?')">
                    🗑 Eliminar
                </a>

            </div>

        </li>

    
        <li class="file-card">

            <div class="file-left">

                <div class="file-icon">📄</div>

                <div class="file-info">
                    <h3>file_6a4522d07a3aa4.47353064.pdf</h3>

                    <span>📦 530.77 KB</span>
                    <span>📅 2026-07-01 16:23:12</span>
                </div>

            </div>

            <div class="file-actions">

                <a href="/mi_archivador/uploads/file_6a4522d07a3aa4.47353064.pdf" download>
                    ⬇ Descargar
                </a>

                <a href="index.php?action=eliminar&file=file_6a4522d07a3aa4.47353064.pdf"
                   onclick="return confirm('¿Eliminar archivo?')">
                    🗑 Eliminar
                </a>

            </div>

        </li>

    
        <li class="file-card">

            <div class="file-left">

                <div class="file-icon">📄</div>

                <div class="file-info">
                    <h3>file_6a452574885156.51773456.pdf</h3>

                    <span>📦 530.77 KB</span>
                    <span>📅 2026-07-01 16:34:28</span>
                </div>

            </div>

            <div class="file-actions">

                <a href="/mi_archivador/uploads/file_6a452574885156.51773456.pdf" download>
                    ⬇ Descargar
                </a>

                <a href="index.php?action=eliminar&file=file_6a452574885156.51773456.pdf"
                   onclick="return confirm('¿Eliminar archivo?')">
                    🗑 Eliminar
                </a>

            </div>

        </li>

    
</ul>

    
</section>

<!-- =========================
        FOOTER
========================= -->
<footer>
    <p>© 2026 Mi Archivador - Sistema POO PHP</p>
</footer>

</body>
</html>
