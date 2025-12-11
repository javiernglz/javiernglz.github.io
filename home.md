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
  /* --- 1. BARRA LATERAL (IZQUIERDA) --- */
  
  /* Título Principal (J.avi Security) con el NUEVO degradado */
  #sidebar .site-title {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 700;
  }
  
  /* Subtítulo */
  #sidebar .site-subtitle { color: #d4b3ff !important; }

  /* Enlaces del Menú (Home, eJPT, About...) - Adiós Gris */
  #sidebar .nav-link {
    color: #a3b8ff !important; /* Azul hielo suave */
  }
  #sidebar .nav-link i {
    color: #8eaafb !important; /* Iconos azulados */
  }

  /* AL PASAR EL RATÓN (HOVER) - Adiós Rosa */
  #sidebar .nav-link:hover {
    color: #540ba3 !important; /* Tu morado eléctrico */
    background: rgba(84, 11, 163, 0.05) !important; /* Fondo muy sutil */
  }
  #sidebar .nav-link:hover i {
    color: #540ba3 !important; /* Icono morado */
  }

  /* Pie de página (Iconos sociales y Copyright) */
  #sidebar .sidebar-bottom a, #sidebar .sidebar-bottom i, #sidebar .sidebar-bottom p {
    color: #a3b8ff !important;
  }
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover {
    color: #540ba3 !important;
  }


  /* --- 2. CONTENIDO CENTRAL --- */

  /* Títulos de Artículos */
  .card-title a { color: #e0e0e0 !important; transition: all 0.3s; }
  
  .card-title a:hover {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
  }

  /* ELIMINAR LÍNEA NARANJA AL PASAR EL RATÓN */
  /* Forzamos que cualquier enlace tenga decoración morada */
  a:hover {
    text-decoration-color: #540ba3 !important;
  }


  /* --- 3. PANEL DERECHO (TAGS Y RECIENTES) --- */

  /* Títulos de secciones (Trending Tags, Recent Update) */
  #panel-wrapper h3, #panel-wrapper .panel-heading {
    color: #d4b3ff !important;
  }

  /* Enlaces de "Recently Updated" */
  #panel-wrapper a {
    color: #a3b8ff !important;
  }
  #panel-wrapper a:hover {
    color: #540ba3 !important;
    text-decoration: none;
  }

  /* TAGS (Las pastillas grises) -> Ahora Moradas */
  .post-tag {
    background: rgba(84, 11, 163, 0.15) !important; /* Fondo morado oscuro */
    color: #d4b3ff !important; /* Texto lila */
    border: 1px solid rgba(84, 11, 163, 0.3) !important;
  }
  
  /* Al pasar el ratón por un Tag */
  .post-tag:hover {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    color: white !important;
    border: 1px solid transparent !important;
  }
</style>
