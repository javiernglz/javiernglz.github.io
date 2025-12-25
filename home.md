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
  /* --- 1. FONDO Y BORDES (MODO NUCLEAR) --- */
  /* Usamos "html body" delante para ganar la guerra de especificidad */
  
  html body #post-list .card, 
  html body #post-list .card-wrapper {
    /* Fondo oscuro exacto */
    background-color: #161625 !important;
    background: #161625 !important;
    
    /* Matamos los colores de categoría (naranja/azul) forzando el borde oscuro */
    border: 1px solid #161625 !important;
    border-color: #161625 !important;
    
    /* Quitamos cualquier sombra de color rara */
    box-shadow: none !important;
    
    /* Forma */
    border-radius: 15px !important;
  }

  /* --- 2. HOVER (EL EFECTO NEÓN) --- */
  
  html body #post-list .card:hover,
  html body #post-list .card-wrapper:hover {
    /* Fondo un pelín más claro al pasar el ratón */
    background-color: #1a1a2e !important;
    
    /* AQUÍ ESTÁ EL BORDÉ MORADO ÚNICO */
    border: 1px solid #6a11cb !important;
    border-color: #6a11cb !important;
    
    /* Resplandor morado */
    box-shadow: 0 0 20px rgba(106, 17, 203, 0.4) !important;
    
    /* Movimiento */
    transform: translateY(-3px) !important;
    z-index: 99 !important;
  }

  /* --- 3. TEXTOS (PARA QUE SE LEAN SIEMPRE) --- */
  
  html body .card-title {
    color: #e0e0e0 !important;
  }
  
  html body .card-text p {
    color: #a0a0a0 !important;
  }
  
  html body .post-meta {
    color: #757590 !important;
  }
  
  html body .post-meta i {
    color: #757590 !important;
  }

  /* Textos al hacer Hover */
  html body #post-list .card:hover .card-title { color: #ffffff !important; }
  html body #post-list .card:hover .post-meta { color: #d4b3ff !important; }
  html body #post-list .card:hover .post-meta i { color: #d4b3ff !important; }

  /* --- 4. EXTRAS PARA LIMPIAR RASTROS --- */
  
  /* A veces Chirpy pone una línea de color a la izquierda. Esto la borra. */
  html body #post-list .card::before, 
  html body #post-list .card::after {
    display: none !important;
    background: none !important;
  }
  
</style>
