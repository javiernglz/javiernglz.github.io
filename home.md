---
layout: page
title: Blog
permalink: /blog/
---

<div id="post-list">
{% for post in site.posts %}
  <article class="card-wrapper card">
    <a href="{{ post.url | relative_url }}" class="post-preview row g-0 flex-md-row-reverse">
      <div class="col-md-12">
        <div class="card-body d-flex flex-column">
          <h1 class="card-title my-2 mt-md-0">{{ post.title }}</h1>

          <div class="card-text content mt-0 mb-3">
            <p>
              {{ post.excerpt | strip_html | truncatewords: 25 }}
            </p>
          </div>

          <div class="post-meta flex-grow-1 d-flex align-items-end">
            <div class="me-auto">
              <i class="far fa-calendar fa-fw me-1"></i>
              {{ post.date | date: "%d/%m/%Y" }}
              
              <i class="far fa-folder-open fa-fw me-1 ms-2"></i>
              {{ post.categories | join: ', ' }}
            </div>
          </div>
        </div>
      </div>
    </a>
  </article>
{% endfor %}
</div>

<style>
  /* --- 1. BARRA LATERAL --- */
  
  /* Título Principal */
  #sidebar .site-title {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important; /* Un poco más claro para leerse mejor */
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 700;
  }
  
  /* Subtítulo */
  #sidebar .site-subtitle { color: #828282 !important; }

  /* Enlaces (About, eJPT...) - Estado Normal */
  #sidebar .nav-link {
    color: #a3b8ff !important; /* Azul hielo suave */
    transition: all 0.3s;
  }
  #sidebar .nav-link i { color: #8eaafb !important; }

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
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover { color: #d4b3ff !important; }


  /* --- 2. ARTÍCULOS --- */

  /* Títulos Normales */
  .card-title a { color: #e0e0e0 !important; }

  /* Títulos al pasar el ratón (Usamos un lila muy claro para que se lea) */
  .card-title a:hover {
    color: #d4b3ff !important; /* Lila claro brillante */
    text-shadow: 0 0 10px rgba(106, 17, 203, 0.6); /* Sombra morada */
    text-decoration: none !important;
  }

  /* Arreglar el subrayado naranja de otros enlaces */
  a:hover {
    text-decoration-color: #9d50bb !important;
  }


  /* --- 3. PANEL DERECHO (TAGS) --- */
  
  /* Títulos de secciones */
  #panel-wrapper h3, #panel-wrapper .panel-heading { color: #828282 !important; }
  
  /* Enlaces recientes */
  #panel-wrapper a { color: #a3b8ff !important; }
  #panel-wrapper a:hover { color: #ffffff !important; text-decoration: underline decoration-purple; }

  /* TAGS (Pastillas) */
.post-tag {
  background: rgba(84, 11, 163, 0.2) !important;
  color: #d4b3ff !important; /* Texto claro */
  border: 1px solid rgba(84, 11, 163, 0.4) !important;
  /* Incluimos un poco de radio base si no lo tiene ya, para que el hover se vea mejor */
  border-radius: 5px; 
}
.post-tag:hover {
  background: rgba(84, 11, 163, 0.4) !important; /* Fondo Morado Transparente (similar al nav-link hover) */
  color: #ffffff !important; /* Texto blanco (similar al nav-link hover) */
  border-color: #540ba3 !important; /* Mantenemos el color del borde si quieres que destaque, o lo ponemos a transparente */
  
  /* ESTILO AÑADIDO PARA EL EFECTO RESPLANDOR */
  border-radius: 10px; /* Borde más redondeado (similar al nav-link hover) */
  box-shadow: 0 0 15px rgba(84, 11, 163, 0.6); /* Resplandor más visible, ajustado un poco */
  
  /* Opcional: Para una transición más suave, podrías añadir esto al .post-tag base */
  /* transition: all 0.3s ease; */
}

</style>
