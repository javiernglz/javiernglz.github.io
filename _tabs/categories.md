---
layout: categories
icon: fas fa-stream
order: 7
hide: true
---

<style>
  /* Título principal y Barra lateral con degradado */
  h1, #sidebar .site-title {
    background: linear-gradient(90deg, #6a11cb, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 700;
  }
  
  /* Botón activo del menú lateral (Morado cristal) */
  #sidebar .nav-item.active .nav-link {
    background: rgba(125, 42, 232, 0.15) !important;
    color: #bfa3ff !important;
    border: 1px solid rgba(125, 42, 232, 0.3) !important;
  }
  
  /* Icono del botón activo */
  #sidebar .nav-item.active .nav-link i {
    color: #4568dc !important;
  }
  
  /* Enlaces normales (para que no salgan verdes) */
  a {
    color: #a3b8ff !important;
  }
  a:hover {
    color: #b06ab3 !important;
    text-decoration: none;
  }
</style>
