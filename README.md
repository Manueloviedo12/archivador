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


Medidas de seguridad implementadas
Almacenamiento de archivos en una carpeta específica
Los archivos se guardan en la carpeta /uploads/, lo que facilita el control y administración de los documentos.
Renombrado automático de archivos
Los nombres de los archivos (por ejemplo, file_6a43645c1e5cb8.40825156.pdf) indican que el sistema genera un nombre único, evitando:
Sobrescribir archivos existentes.
Conflictos de nombres.
Exposición del nombre original del archivo.

Confirmación antes de eliminar archivos

onclick="return confirm('¿Eliminar archivo?')"

Esta confirmación evita eliminaciones accidentales realizadas por el usuario.

Descarga mediante rutas controladas

<a href="/mi_archivador/uploads/archivo.pdf" download>

El atributo download fuerza la descarga del archivo en lugar de abrirlo directamente en el navegador.

Medidas de seguridad recomendadas
1. Validar el tipo de archivo

Permitir únicamente formatos seguros.

$permitidos = ['pdf','doc','docx','jpg','png'];

$extension = strtolower(pathinfo($_FILES['archivo']['name'], PATHINFO_EXTENSION));

if(!in_array($extension,$permitidos)){
    die("Tipo de archivo no permitido");
}
2. Limitar el tamaño del archivo

Evita ataques mediante archivos demasiado grandes.

if($_FILES['archivo']['size'] > 5 * 1024 * 1024){
    die("Archivo demasiado grande");
}

Ejemplo: máximo 5 MB.

3. Validar el nombre del archivo

Evitar caracteres especiales o rutas maliciosas.

$archivo = basename($_GET['file']);

Esto previene ataques como:

../../../windows/system32
4. Evitar la ejecución de archivos PHP

No permitir subir archivos como:

virus.php
shell.php
backdoor.php

Solo aceptar documentos e imágenes.

5. Verificar el tipo MIME

No confiar únicamente en la extensión.

$finfo = finfo_open(FILEINFO_MIME_TYPE);

$tipo = finfo_file($finfo,$_FILES['archivo']['tmp_name']);
6. Proteger la carpeta uploads

Agregar un archivo .htaccess

php_flag engine off

Options -Indexes

Con esto:

No se ejecuta código PHP.
No se muestra el listado de archivos.
7. Sanitizar los parámetros GET

Antes de eliminar un archivo.

$file = basename($_GET['file']);

Nunca utilizar directamente:

$_GET['file']
8. Utilizar sesiones

Solo usuarios autenticados deberían poder:

subir archivos;
eliminar archivos;
descargar archivos.
session_start();

if(!isset($_SESSION['usuario'])){
    header("Location: login.php");
}
9. Proteger contra CSRF

Para acciones como eliminar archivos, usar un token CSRF en lugar de depender únicamente de un enlace GET.

10. Mostrar mensajes seguros

Evitar mostrar errores internos de PHP al usuario.

ini_set('display_errors',0);

Registrar los errores en un archivo de log.

11. Utilizar HTTPS

Transmitir toda la información cifrada para evitar la interceptación de datos.

12. Permisos adecuados

Asignar permisos restringidos a la carpeta de archivos.

Ejemplo:

755

o

750

Nunca utilizar:

777

Conclusión: El proyecto incorpora medidas de seguridad, como el renombrado automático de los archivos, la organización del almacenamiento y la confirmación antes de eliminar documento, eso es lo que puedo explicar acerca de las medidadas de seguridad del proyecto. muchas gracias...


video explicado de el proseso de de la subida de archivo y la eliminacion....
https://youtu.be/Us6k-IuETOg



</body>
</html>
