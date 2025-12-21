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
  /* --- 1. BARRA LATERAL --- */
  
  #sidebar .site-title {
    background: linear-gradient(90deg, #6a11cb, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 800;
  }
  
  #sidebar .site-subtitle { color: #828282 !important; }

  #sidebar .nav-link {
    color: #a3b8ff !important;
    transition: all 0.3s ease;
  }
  #sidebar .nav-link i { color: #8eaafb !important; }

  /* ESTE ES EL EFECTO QUE QUEREMOS COPIAR */
  #sidebar .nav-link:hover {
    color: #ffffff !important;
    background: rgba(84, 11, 163, 0.4) !important; /* Fondo Morado Transparente */
    border-radius: 10px;
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4); /* Resplandor */
  }
  
  #sidebar .nav-link:hover i { color: #ffffff !important; }

  #sidebar .sidebar-bottom a, #sidebar .sidebar-bottom i { color: #a3b8ff !important; }
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover { color: #9d52ffff !important; }


  /* --- 2. ARTÍCULOS CENTRALES (MODIFICADO) --- */

  /* Aplicamos el efecto a TODA la tarjeta del post, no solo al título */
  .post-preview {
    border-radius: 10px; /* Preparamos las esquinas */
    padding: 10px;       /* Un poco de aire para que el fondo no pegue al texto */
    margin: -10px;       /* Compensamos el padding para no descolocar la lista */
    transition: all 0.3s ease; /* Transición suave igual que el sidebar */
  }

  /* AL PASAR EL RATÓN POR EL ARTÍCULO */
  .post-preview:hover {
    background: rgba(84, 11, 163, 0.4) !important; /* EL MISMO FONDO */
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4);    /* EL MISMO BRILLO */
    text-decoration: none !important;
  }

  /* Qué pasa con los textos de dentro al hacer hover */
  .post-preview:hover .card-title { 
    color: #ffffff !important; /* Título blanco */
    text-shadow: none !important; /* Quitamos sombras raras */
  }
  
  .post-preview:hover .card-text p {
    color: #e0e0e0 !important; /* Resumen en gris claro */
  }
  
  .post-preview:hover .post-meta, 
  .post-preview:hover .post-meta i {
    color: #d4b3ff !important; /* Iconos y fecha en lila claro */
  }

  /* Título normal (sin hover) */
  .card-title { color: #e0e0e0 !important; transition: color 0.3s; }


  /* --- 3. PANEL DERECHO & TAGS (MODIFICADO) --- */
  
  #panel-wrapper h3, #panel-wrapper .panel-heading { color: #828282 !important; }
  
  /* Enlaces de "Updated Recent" */
  #panel-wrapper li a { 
    color: #a3b8ff !important; 
    transition: all 0.3s;
    display: block; /* Para que pille padding */
    padding: 2px 5px;
    border-radius: 5px;
  }
  
  /* Efecto mini-glow para los enlaces de texto de la derecha */
  #panel-wrapper li a:hover { 
    color: #ffffff !important; 
    text-decoration: none !important;
    background: rgba(84, 11, 163, 0.2); /* Un fondo más sutil para listas */
    text-shadow: 0 0 5px rgba(132, 0, 255, 0.5);
  }

  /* TAGS (LAS PASTILLAS) */
  .post-tag {
    background: rgba(84, 11, 163, 0.15) !important; /* Un poco más oscuro en reposo */
    color: #d4b3ff !important;
    border: 1px solid rgba(84, 11, 163, 0.3) !important; /* Borde sutil en reposo */
    border-radius: 10px; /* Redondeado igual que el sidebar */
    transition: all 0.3s ease;
  }

  /* TAGS HOVER - AQUÍ ESTABA EL FALLO */
  .post-tag:hover {
    background: rgba(84, 11, 163, 0.4) !important; /* MISMO FONDO QUE SIDEBAR */
    color: #ffffff !important;
    
    /* TRUCO: Quitamos el borde (o lo ponemos del mismo color que el fondo) 
       para eliminar el efecto "caja" y que parezca luz pura */
    border-color: rgba(84, 11, 163, 0.4) !important; 
    
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4); /* MISMO GLOW QUE SIDEBAR */
  }

</style>