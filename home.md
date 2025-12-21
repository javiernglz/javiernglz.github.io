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
  /* --- 0. RESET NUCLEAR (ELIMINAR EL FANTASMA) --- */
  /* Atacamos todas las clases posibles del tema para hacerlas invisibles */
  
  #post-list article,
  #post-list .card,
  #post-list .card-wrapper,
  #post-list .card-body {
    background-color: transparent !important;
    background: none !important;
    border: none !important;
    box-shadow: none !important;
  }
  
  /* Esto elimina los pseudo-elementos que a veces crean sombras en Chirpy */
  #post-list .card::before, #post-list .card::after {
    display: none !important;
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


  /* --- 2. ARTÍCULOS CENTRALES (EL ESTILO CRISTAL) --- */
  
  .post-preview {
    /* Fondo base oscuro y translúcido */
    background: rgba(25, 25, 35, 0.6) !important; 
    border: 1px solid rgba(84, 11, 163, 0.1) !important;
    border-radius: 15px !important; 
    
    padding: 20px !important;
    margin-bottom: 25px !important; /* Separación vertical */
    
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    backdrop-filter: blur(5px); 
    -webkit-backdrop-filter: blur(5px);
    
    /* Importante: para que ocupe el espacio correcto */
    display: block; 
  }

  /* HOVER: EFECTO ACTIVADO */
  .post-preview:hover {
    background: rgba(84, 11, 163, 0.25) !important; 
    border: 1px solid rgba(132, 0, 255, 0.5) !important; 
    box-shadow: 0 0 25px rgba(84, 11, 163, 0.35) !important; 
    transform: translateY(-5px); /* Salto hacia arriba */
    text-decoration: none !important;
    z-index: 10;
  }

  /* Ajuste de textos dentro de la tarjeta */
  .post-preview:hover .card-title { color: #ffffff !important; text-shadow: 0 0 10px rgba(132,0,255,0.4); }
  .post-preview:hover .card-text p { color: #e0e0e0 !important; }
  .post-preview:hover .post-meta { color: #d4b3ff !important; }
  .post-preview:hover i { color: #d4b3ff !important; }

  .card-title { 
    color: #e0e0e0 !important; 
    font-weight: 700;
    transition: color 0.3s;
  }


  /* --- 3. PANEL DERECHO & TAGS --- */
  
  #panel-wrapper h3, #panel-wrapper .panel-heading { color: #828282 !important; }
  
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

  /* TAGS Redondos */
  .post-tag {
    background: transparent !important; 
    color: #a3b8ff !important;
    border: 1px solid rgba(84, 11, 163, 0.3) !important;
    border-radius: 50px !important; 
    padding: 6px 14px !important;
    font-size: 0.85rem !important;
    transition: all 0.3s ease;
  }

  .post-tag:hover {
    background: rgba(84, 11, 163, 0.5) !important; 
    color: #ffffff !important;
    border-color: rgba(132, 0, 255, 0.6) !important; 
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.5) !important; 
    transform: scale(1.05); 
  }

</style>