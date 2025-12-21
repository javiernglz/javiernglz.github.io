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
  /* --- 1. TARJETAS DE LOS ARTÍCULOS (EL CAMBIO SUTIL) --- */
  
  #post-list .card {
    /* Fondo Morado Oscuro Profundo (Casi negro, pero con tono) */
    background-color: #161625 !important; 
    
    /* Borde del mismo color para que sea sutil de primeras */
    border: 1px solid #161625 !important;
    
    /* Un poco de redondeo para modernizar */
    border-radius: 12px !important;
    
    /* Sombra suave para que no quede plano del todo */
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3) !important;
  }

  /* ESTADO HOVER (AL PASAR EL RATÓN) */
  #post-list .card:hover {
    /* El fondo se queda igual o cambia mínimamente */
    background-color: #1a1a2e !important; 
    
    /* LO ÚNICO QUE DESTACA: El borde brilla en tu morado */
    border: 1px solid #6a11cb !important;
    
    /* Un resplandor muy suave */
    box-shadow: 0 0 15px rgba(106, 17, 203, 0.2) !important;
  }

  /* --- 2. TEXTOS (PARA QUE SE LEAN SOBRE FONDO OSCURO) --- */
  
  .card-title {
    color: #e0e0e0 !important; /* Blanco roto */
  }
  
  .card-text p {
    color: #a0a0a0 !important; /* Gris medio */
  }
  
  .post-meta {
    color: #707090 !important; /* Azul grisáceo apagado */
  }
  
  /* Al pasar el ratón, los textos se iluminan un poco */
  #post-list .card:hover .card-title { color: #ffffff !important; }
  #post-list .card:hover .post-meta { color: #a3b8ff !important; }


  /* --- 3. BARRA LATERAL (TU ESTILO QUE YA FUNCIONABA) --- */
  
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

  #sidebar .nav-link:hover {
    color: #ffffff !important;
    background: rgba(84, 11, 163, 0.4) !important; 
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4);
  }
  #sidebar .nav-link:hover i { color: #ffffff !important; }
  
  /* Tags del panel derecho */
  .post-tag {
    background: rgba(84, 11, 163, 0.1) !important;
    border: 1px solid rgba(84, 11, 163, 0.3) !important;
    color: #a3b8ff !important;
    border-radius: 50px !important;
  }
  .post-tag:hover {
    background: rgba(84, 11, 163, 0.4) !important;
    color: #fff !important;
  }
</style>