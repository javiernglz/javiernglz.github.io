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
  /* --- 0. RESET NUCLEAR DE COLORES (ESTO MATA LOS COLORES DEL TEMA) --- */
  
  /* Forzamos que CUALQUIER tarjeta, tenga la categoría que tenga, sea oscura */
  #post-list .card, 
  #post-list .card-wrapper {
    background-color: #161625 !important;
    background: #161625 !important;
    
    /* Matamos los bordes de colores específicos de categoría */
    border: 1px solid #161625 !important;
    border-top: 1px solid #161625 !important;
    border-bottom: 1px solid #161625 !important;
    border-left: 1px solid #161625 !important;
    border-right: 1px solid #161625 !important;
    
    border-radius: 12px !important;
    box-shadow: 0 4px 10px rgba(0,0,0,0.4) !important;
  }

  /* --- 1. HOVER ÚNICO (SOLO MORADO) --- */
  
  #post-list .card:hover,
  #post-list .card-wrapper:hover {
    background-color: #1a1a2e !important; 
    
    /* Aquí forzamos el borde morado en los 4 lados */
    border: 1px solid #6a11cb !important; 
    border-color: #6a11cb !important;
    
    box-shadow: 0 0 20px rgba(106, 17, 203, 0.3) !important;
    transform: translateY(-2px); /* Un pequeño movimiento para que se sienta vivo */
  }

  /* --- 2. TEXTOS Y METADATA --- */
  
  .card-title { color: #e0e0e0 !important; }
  .card-text p { color: #a0a0a0 !important; }
  
  /* Forzamos el color de los iconos y texto de abajo, que a veces heredan el color de categoría */
  .post-meta, 
  .post-meta i,
  .post-meta span {
    color: #707090 !important; 
  }
  
  /* Al pasar el ratón */
  #post-list .card:hover .card-title { color: #ffffff !important; }
  #post-list .card:hover .post-meta,
  #post-list .card:hover .post-meta i { 
    color: #d4b3ff !important; 
  }


  /* --- 3. BARRA LATERAL (INTOCABLE) --- */
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

  /* Tags */
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