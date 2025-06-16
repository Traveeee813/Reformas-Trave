from zipfile import ZipFile
import os

# Crear el contenido del archivo index.html
html_content = """<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Construcciones XYZ</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f8f8f8;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #2c3e50;
      color: white;
      padding: 20px;
      text-align: center;
    }
    section {
      padding: 40px;
      max-width: 800px;
      margin: auto;
    }
    h2 {
      color: #2c3e50;
    }
    form {
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    label {
      display: block;
      margin-top: 10px;
    }
    input, textarea {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #27ae60;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background-color: #219150;
    }
    footer {
      text-align: center;
      padding: 20px;
      background: #2c3e50;
      color: white;
    }
  </style>
</head>
<body>

<header>
  <h1>Construcciones XYZ</h1>
  <p>Tu socio de confianza en proyectos de construcción</p>
</header>

<section>
  <h2>Servicios</h2>
  <ul>
    <li>Reformas integrales</li>
    <li>Construcción de viviendas</li>
    <li>Rehabilitación de edificios</li>
    <li>Obras públicas y privadas</li>
  </ul>
</section>

<section>
  <h2>Agenda tu llamada</h2>
  <form action="https://formsubmit.co/TU_CORREO@ejemplo.com" method="POST">
    <label for="nombre">Nombre completo:</label>
    <input type="text" id="nombre" name="nombre" required>

    <label for="telefono">Número de teléfono:</label>
    <input type="tel" id="telefono" name="telefono" required>

    <label for="fecha">Fecha preferida para la llamada:</label>
    <input type="date" id="fecha" name="fecha" required>

    <label for="mensaje">¿En qué podemos ayudarte?</label>
    <textarea id="mensaje" name="mensaje" rows="4" required></textarea>

    <input type="hidden" name="_captcha" value="false">
    <button type="submit">Agendar llamada</button>
  </form>
</section>

<footer>
  <p>&copy; 2025 Construcciones XYZ - Todos los derechos reservados</p>
</footer>

</body>
</html>
"""

# Ruta del archivo HTML
html_path = "/mnt/data/index.html"

# Escribir el archivo HTML
with open(html_path, "w", encoding="utf-8") as f:
    f.write(html_content)

# Crear el archivo ZIP
zip_path = "/mnt/data/pagina_construccion.zip"
with ZipFile(zip_path, 'w') as zipf:
    zipf.write(html_path, arcname="index.html")

zip_path
