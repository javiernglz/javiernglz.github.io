---
layout: page
icon: fas fa-chalkboard-teacher
order: 3
title: Clases Ciber
permalink: /clases/
---

## Mis Formaciones y Recursos

Aquí comparto el material visual y las diapositivas de las sesiones que he impartido sobre seguridad ofensiva y defensiva.

---

### 1. Cómo empezar en Ciberseguridad
_Roadmap y pilares fundamentales._

<div align="center" class="resource-card">
  <a href="/assets/slides/Inicio%20en%20Ciberseguridad.pdf" target="_blank">
    <img src="/assets/Portadas/iniciociber.png" alt="Inicio Ciberseguridad" class="preview-img">
  </a>
  <br><br>
  <a href="/assets/slides/Inicio%20en%20Ciberseguridad.pdf" class="btn-download">
    <i class="fas fa-file-download"></i> Descargar PDF (Roadmap)
  </a>
</div>

<br>

### 2. Fundamentos de Hacking Ético
_Introducción al Red Team y metodología._

<div align="center" class="resource-card">
  <a href="/assets/slides/Fundamentos%20Hacking%20Ético.pdf" target="_blank">
    <img src="/assets/Portadas/hacking_etico.png" alt="Hacking Ético" class="preview-img">
  </a>
  <br><br>
  <a href="/assets/slides/Fundamentos%20Hacking%20Ético.pdf" class="btn-download">
    <i class="fas fa-user-secret"></i> Descargar PDF (Red Team)
  </a>
</div>

<br>

### 3. Monitorización con SIEMs
_Defensa y Blue Team con Splunk/Wazuh._

<div align="center" class="resource-card">
  <a href="/assets/slides/SIEMs.pdf" target="_blank">
    <img src="/assets/Portadas/siems.png" alt="SIEMs" class="preview-img">
  </a>
  <br><br>
  <a href="/assets/slides/SIEMs.pdf" class="btn-download">
    <i class="fas fa-shield-alt"></i> Descargar PDF (Blue Team)
  </a>
</div>

<br>

### 4. Criptografía y Cifrado
_Protección de la información._

<div align="center" class="resource-card">
  <a href="/assets/slides/cifrado-criptografia.pdf" target="_blank">
    <img src="/assets/Portadas/cifrado.png" alt="Cifrado" class="preview-img">
  </a>
  <br><br>
  <a href="/assets/slides/cifrado-criptografia.pdf" class="btn-download">
    <i class="fas fa-key"></i> Descargar PDF (Cifrado)
  </a>
</div>

---

<style>
  /* 1. Títulos y Barra Lateral */
  h1, #sidebar .site-title {
    background: linear-gradient(90deg, #6a11cb, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 800;
  }
  
  /* 2. Botón Activo del Menú */
  #sidebar .nav-item.active .nav-link {
    background: rgba(106, 17, 203, 0.15) !important;
    color: #d4b3ff !important;
    border: 1px solid rgba(106, 17, 203, 0.3) !important;
  }
  #sidebar .nav-item.active .nav-link i { color: #4568dc !important; }

  /* 3. Enlaces Generales */
  a { color: #8eaafb !important; text-decoration: none; }
  a:hover { color: #6a11cb !important; }

  /* 4. ESTILOS DE LA GALERÍA (NUEVO) */
  
  /* Imágenes con sombra morada */
  .preview-img {
    width: 90%;
    border-radius: 12px;
    border: 1px solid rgba(125, 42, 232, 0.2);
    box-shadow: 0 0 20px rgba(106, 17, 203, 0.2); /* Sombra morada suave */
    transition: transform 0.3s, box-shadow 0.3s;
  }
  
  .preview-img:hover {
    transform: scale(1.02);
    box-shadow: 0 0 30px rgba(69, 104, 220, 0.5); /* Brillo azul al pasar ratón */
  }

  /* Botones de Descarga Personalizados */
  .btn-download {
    display: inline-block;
    background: linear-gradient(90deg, #6a11cb, #4568dc) !important; /* Degradado Space */
    color: white !important;
    font-weight: bold;
    padding: 12px 25px;
    border-radius: 50px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
    transition: all 0.3s ease;
    border: none;
  }

  .btn-download:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(106, 17, 203, 0.6);
    color: white !important;
  }
</style>
