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
  /* 1. Título Lateral: DEGRADADO OFICIAL (#540ba3 -> #4568dc) */
  #sidebar .site-title {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 700;
  }

  /* 2. Subtítulo (Cybersecurity Analyst...) - Lila claro */
  #sidebar .site-subtitle {
    color: #d4b3ff !important;
    font-weight: 500;
  }

  /* 3. Títulos de los artículos: Efecto Hover Nuevo */
  .card-title a {
    color: #e0e0e0 !important;
    transition: all 0.3s;
  }
  .card-title a:hover {
    /* Mismo degradado al pasar el ratón */
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
  }

  /* 4. Pie de página (Iconos sociales y Copyright) - Adiós al gris */
  #sidebar .sidebar-bottom a, 
  #sidebar .sidebar-bottom i,
  #sidebar .sidebar-bottom p {
    color: #a3b8ff !important; /* Azul hielo */
    transition: color 0.3s;
  }
  
  /* Al pasar el ratón por los iconos de abajo */
  #sidebar .sidebar-bottom a:hover, 
  #sidebar .sidebar-bottom i:hover {
    color: #540ba3 !important; /* Tu morado nuevo */
  }
</style>
