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
  /* 1. J.AVI SECURITY: Degradado Morado Oscuro -> Azul */
  #sidebar .site-title {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 700;
  }

  /* 2. TEXTOS SECUNDARIOS EN GRIS (Analyst, Updated, Trending) */
  #sidebar .site-subtitle,
  #panel-wrapper h3, 
  #panel-wrapper .panel-heading,
  #access-tags .post-tag { 
    color: #828282 !important; /* Gris neutro */
  }

  /* Enlaces de "Recently Updated" en gris normal, morado al pasar ratón */
  #panel-wrapper .access-text { color: #828282 !important; }
  #panel-wrapper .access-text:hover { color: #540ba3 !important; }


  /* 3. QUITAR LÍNEA NARANJA (Breadcrumbs y Artículos) */
  
  /* Migas de pan (Home > Blog) */
  #breadcrumb a { color: #828282 !important; }
  #breadcrumb a:hover { 
    color: #540ba3 !important; /* Se pone morado */
    text-decoration: none !important; /* Sin subrayado */
  }

  /* Títulos de Artículos al pasar el ratón */
  .card-title a:hover {
    color: #540ba3 !important;
    background: none !important; /* Quitamos degradado en texto para legibilidad */
    text-decoration-color: #540ba3 !important; /* Subrayado morado */
    -webkit-text-fill-color: #540ba3 !important; /* Color sólido */
  }


  /* 4. TAGS (ETIQUETAS) - ESTILO TABS (Sin borde azul) */
  
  .post-tag {
    background: rgba(255, 255, 255, 0.05) !important; /* Fondo gris muy sutil */
    color: #a0a0a0 !important; /* Texto gris */
    border: 1px solid transparent !important; /* QUITAR BORDE AZUL */
    border-radius: 10px;
    transition: all 0.3s ease;
  }

  /* Al pasar el ratón: Fondo Morado Desvanecido + Texto Blanco */
  .post-tag:hover {
    background: rgba(84, 11, 163, 0.5) !important; /* Morado translúcido */
    color: #ffffff !important;
    border: 1px solid transparent !important;
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.3); /* Brillo suave */
  }

  /* Fix específico para el borde azul que a veces sale en Chirpy */
  .post-tag:focus, .post-tag:active {
    box-shadow: none !important;
    outline: none !important;
  }
</style>
