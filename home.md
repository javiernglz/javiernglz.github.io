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
  /* --- 1. BARRA LATERAL (J.avi Security) --- */
  
  /* Título Principal: Vuelta al degradado eléctrico original */
  #sidebar .site-title {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 700;
  }
  
  /* Subtítulo: Gris normal y elegante */
  #sidebar .site-subtitle { color: #8c8c8c !important; }


  /* --- 2. MENÚ IZQUIERDO (Estilo Glow) --- */
  
  /* Estado normal (Gris azulado suave) */
  #sidebar .nav-link {
    color: #a0a0a0 !important;
    transition: all 0.3s;
  }
  #sidebar .nav-link i { color: #8c8c8c !important; }

  /* Hover: Texto Blanco + Fondo Morado Desvanecido */
  #sidebar .nav-link:hover {
    color: #ffffff !important;
    background: rgba(84, 11, 163, 0.5) !important; /* El desvanecido morado */
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4); /* Resplandor */
    border-radius: 10px;
  }
  #sidebar .nav-link:hover i { color: #ffffff !important; }

  /* Iconos sociales de abajo */
  #sidebar .sidebar-bottom a, #sidebar .sidebar-bottom i { color: #8c8c8c !important; }
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover { color: #540ba3 !important; }


  /* --- 3. CONTENIDO CENTRAL Y BREADCRUMBS --- */

  /* Forzar que CUALQUIER enlace al pasar el ratón sea morado (Adiós Naranja) */
  a:hover {
    color: #540ba3 !important;
    text-decoration-color: #540ba3 !important;
  }

  /* Breadcrumbs (Home > Blog) */
  nav[aria-label="breadcrumb"] a { color: #a0a0a0 !important; }
  nav[aria-label="breadcrumb"] a:hover { color: #540ba3 !important; }

  /* Títulos de Artículos */
  .card-title a { color: #e0e0e0 !important; }
  .card-title a:hover {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    text-shadow: none !important;
    text-decoration: none !important; /* Quitamos subrayado feo */
    border-bottom: none !important; /* Aseguramos que no salga línea naranja */
  }


  /* --- 4. PANEL DERECHO (TAGS) --- */
  
  /* Títulos en Gris Normal */
  #panel-wrapper h3, #panel-wrapper .panel-heading { 
    color: #8c8c8c !important; 
    font-size: 1rem !important; /* Un poco más fino */
  }
  
  /* Enlaces recientes en gris */
  #panel-wrapper a { color: #a0a0a0 !important; }
  #panel-wrapper a:hover { color: #540ba3 !important; }

  /* TRENDING TAGS: Estilo idéntico a los Tabs */
  .post-tag {
    background: rgba(255, 255, 255, 0.05) !important; /* Fondo sutil por defecto */
    color: #a0a0a0 !important; /* Letra gris */
    border: 1px solid transparent !important; /* Sin bordes azules */
    border-radius: 10px; /* Redonditos */
    transition: all 0.3s ease;
  }
  
  /* Al pasar el ratón: Glow Morado + Texto Blanco */
  .post-tag:hover {
    background: rgba(84, 11, 163, 0.5) !important;
    color: #ffffff !important;
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4); /* El mismo brillo que los tabs */
    border: 1px solid transparent !important;
  }
</style>
