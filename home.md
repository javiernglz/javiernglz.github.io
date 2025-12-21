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
  /* --- 0. RESET NUCLEAR (ESTO SOLUCIONA LA MEZCLA DE TEMAS) --- */
  /* Borramos los estilos por defecto de Chirpy/Bootstrap que ensucian el diseño */
  
  #post-list .card, 
  #post-list .card-body {
    background-color: transparent !important; /* Quita el fondo gris/blanco feo */
    border: none !important;                 /* Quita el borde aburrido */
    box-shadow: none !important;             /* Quita la sombra por defecto */
  }

  /* --- 1. BARRA LATERAL (TU REFERENCIA) --- */
  
  #sidebar .site-title {
    background: linear-gradient(90deg, #6a11cb, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 800;
  }
  
  #sidebar .site-subtitle { color: #828282 !important; }

  #sidebar .nav-link {
    color: #a3b8ff !important;
    border-radius: 10px;
    transition: all 0.3s ease;
  }
  #sidebar .nav-link i { color: #8eaafb !important; }

  /* Hover Neón del Sidebar */
  #sidebar .nav-link:hover {
    color: #ffffff !important;
    background: rgba(84, 11, 163, 0.4) !important; 
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4);
  }
  #sidebar .nav-link:hover i { color: #ffffff !important; }

  #sidebar .sidebar-bottom a, #sidebar .sidebar-bottom i { color: #a3b8ff !important; }
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover { color: #9d52ffff !important; }


  /* --- 2. ARTÍCULOS CENTRALES (EL ARREGLO VISUAL) --- */
  
  /* Ahora aplicamos el estilo al enlace contenedor (.post-preview) */
  .post-preview {
    background: rgba(30, 30, 40, 0.4) !important; /* Un fondo base muy sutil y oscuro para que no flote en la nada */
    border: 1px solid rgba(84, 11, 163, 0.1) !important; /* Borde casi invisible */
    border-radius: 15px !important; 
    padding: 20px !important;
    margin-bottom: 20px !important; /* Separación entre artículos */
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
  }

  /* EL EFECTO HOVER NEÓN LIMPIO */
  .post-preview:hover {
    background: rgba(84, 11, 163, 0.25) !important; /* Fondo morado translúcido */
    border: 1px solid rgba(132, 0, 255, 0.5) !important; /* Borde brillante */
    box-shadow: 0 0 25px rgba(84, 11, 163, 0.35) !important; /* Resplandor */
    transform: translateY(-3px) scale(1.01); /* Pequeño "salto" hacia el usuario */
    z-index: 10; /* Asegura que brille por encima de todo */
    text-decoration: none !important;
  }

  /* Ajuste de colores de texto al hacer hover */
  .post-preview:hover .card-title { color: #ffffff !important; text-shadow: 0 0 10px rgba(132,0,255,0.4); }
  .post-preview:hover .card-text p { color: #e0e0e0 !important; }
  .post-preview:hover .post-meta { color: #d4b3ff !important; }
  .post-preview:hover i { color: #d4b3ff !important; }

  /* Títulos en estado normal */
  .card-title { 
    color: #e0e0e0 !important; 
    font-weight: 700;
  }


  /* --- 3. PANEL DERECHO & TAGS (UNIFICACIÓN) --- */
  
  #panel-wrapper h3, #panel-wrapper .panel-heading { color: #828282 !important; }
  
  /* Enlaces de "Updated Recent" */
  #panel-wrapper li a { 
    color: #a3b8ff !important; 
    padding: 5px 8px;
    border-radius: 6px;
    display: block;
    transition: all 0.2s;
  }
  
  #panel-wrapper li a:hover { 
    color: #ffffff !important; 
    background: rgba(84, 11, 163, 0.3);
    text-decoration: none !important;
  }

  /* TAGS - Las pastillas redondas */
  .post-tag {
    background: transparent !important; /* Sin fondo en reposo */
    color: #a3b8ff !important;
    border: 1px solid rgba(84, 11, 163, 0.3) !important;
    border-radius: 50px !important; /* SÚPER REDONDO */
    padding: 6px 14px !important;
    font-size: 0.85rem !important;
    transition: all 0.3s ease;
  }

  /* TAGS HOVER - COPIA EXACTA DEL SIDEBAR */
  .post-tag:hover {
    background: rgba(84, 11, 163, 0.5) !important; 
    color: #ffffff !important;
    border-color: rgba(132, 0, 255, 0.6) !important; 
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.5) !important; 
    transform: scale(1.05); 
  }

</style>