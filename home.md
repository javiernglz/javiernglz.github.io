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
  /* --- 1. FORZADO DE TARJETAS (SOBREESCRIBIR TEMA) --- */
  
  /* Atacamos tanto a .card como a .card-wrapper para que no escape nada */
  #post-list .card, 
  #post-list .card-wrapper {
    /* FONDO: Morado muy oscuro (Casi negro) */
    background-color: #161625 !important;
    background: #161625 !important;
    
    /* BORDE INICIAL: Del mismo color que el fondo (Invisible/Sutil) */
    /* El !important aquí anula el color naranja/azul de las categorías */
    border: 1px solid #161625 !important;
    border-color: #161625 !important;
    
    border-radius: 12px !important;
    box-shadow: 0 4px 10px rgba(0,0,0,0.4) !important;
  }

  /* --- 2. HOVER (SOLO MORADO PARA TODOS) --- */
  
  /* Al pasar el ratón, forzamos que SIEMPRE sea morado, da igual la categoría */
  #post-list .card:hover,
  #post-list .card-wrapper:hover {
    background-color: #1a1a2e !important; /* Un pelín más claro */
    
    /* BORDE NEÓN: Aquí imponemos tu color */
    border: 1px solid #6a11cb !important; 
    border-color: #6a11cb !important;
    
    box-shadow: 0 0 20px rgba(106, 17, 203, 0.3) !important;
    text-decoration: none !important;
  }

  /* --- 3. TEXTOS (LEGIBILIDAD) --- */
  
  .card-title {
    color: #e0e0e0 !important;
    transition: color 0.3s;
  }
  
  .card-text p {
    color: #a0a0a0 !important;
  }
  
  .post-meta {
    color: #707090 !important;
  }
  
  .post-meta i {
    color: #707090 !important;
  }
  
  /* Hover Textos */
  #post-list .card:hover .card-title { color: #ffffff !important; }
  #post-list .card:hover .post-meta { color: #d4b3ff !important; }
  #post-list .card:hover .post-meta i { color: #d4b3ff !important; }


  /* --- 4. BARRA LATERAL (INTOCABLE) --- */
  
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

  /* Tags Panel Derecho */
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