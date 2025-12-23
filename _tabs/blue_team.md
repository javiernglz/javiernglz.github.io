---
layout: page
icon: fas fa-shield-halved
order: 4
title: Blue Team
permalink: /blueteam/
---

### [1. Análisis de malware en Documentos y URLs]({% post_url 2025-12-21-analisis-docs-url %})
> Guía de triaje para analizar la legitimidad de documentos y enlaces sospechosos según la sensibilidad de la información (confidencial o pública).

### [2. Reglas YARA]({% post_url 2025-12-23-yara-rules %})
> Guía para aprender a detectar amenazas definiendo patrones.

---

<style>
  /* 1. Título principal de la página con degradado */
  h1 {
    background: linear-gradient(90deg, #277ad3, #1a41b7) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 800;
    width: fit-content;
    display: inline-block;
    text-shadow: 0px 0px 30px rgba(69, 104, 220, 0.2);
  }

  /* 2. Tu nombre en la Barra Lateral (J.avi Security) */
  #sidebar .site-title {
    background: linear-gradient(90deg, #277ad3, #1a41b7) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
  }

  /* AL PASAR EL RATÓN (SOLUCIÓN DE LEGIBILIDAD) */
  #sidebar .nav-link:hover {
    color: #ffffff !important; /* TEXTO BLANCO (Se lee perfecto) */
    background: rgba(84, 11, 163, 0.4) !important; /* Fondo Morado Transparente */
    border-radius: 10px;
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4); /* Resplandor */
  }
  
  #sidebar .nav-link:hover i {
    color: #ffffff !important; /* Icono Blanco */
  }

  /* Iconos de abajo */
  #sidebar .sidebar-bottom a, #sidebar .sidebar-bottom i { color: #a3b8ff !important; }
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover { color: #9d52ffff !important; }


  /* 4. Icono del escudo en la barra lateral */
  #sidebar .nav-item.active .nav-link i {
    color: #277ad3 !important;
  }
  
  /* 5. Subtítulos y enlaces */
  h2, h3, a {
    color: #277ad3; 
  }
  a:hover {
    color: #b06ab3; 
    text-decoration: none;
  }
</style>
