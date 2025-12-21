---
layout: page
title: Blog
permalink: /blog/
---

<div id="post-list">
{% for post in site.posts %}
  <article class="post-item">
    <a href="{{ post.url | relative_url }}" class="post-preview">
      
      <h1 class="card-title">{{ post.title }}</h1>

      <div class="card-text content">
        <p>
          {{ post.excerpt | strip_html | truncatewords: 25 }}
        </p>
      </div>

      <div class="post-meta">
        <div class="meta-item">
          <i class="far fa-calendar fa-fw me-1"></i>
          {{ post.date | date: "%d/%m/%Y" }}
        </div>
        
        <div class="meta-item">
          <i class="far fa-folder-open fa-fw me-1"></i>
          {{ post.categories | join: ', ' }}
        </div>
      </div>

    </a>
  </article>
{% endfor %}
</div>

<style>
  /* --- 0. CORRECCIÓN DE ALINEACIÓN (CRÍTICO) --- */
  
  /* Esto elimina el desplazamiento a la derecha forzando al contenedor a pegar al borde */
  #post-list {
    padding-left: 0 !important;
    padding-right: 0 !important;
    margin-left: 0 !important;
    margin-right: 0 !important;
    width: 100% !important;
    box-sizing: border-box !important;
  }

  /* --- 1. BARRA LATERAL (REFERENCIA) --- */
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

  #sidebar .sidebar-bottom a, #sidebar .sidebar-bottom i { color: #a3b8ff !important; }
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover { color: #9d52ffff !important; }


  /* --- 2. ARTÍCULOS CENTRALES (ESTILO NEÓN FINAL) --- */
  
  .post-item {
    display: block;
    width: 100% !important; /* Ocupa todo el ancho */
    margin: 0 0 20px 0 !important; /* Solo margen abajo */
    padding: 0 !important;
    border: none !important;
    background: transparent !important;
    list-style: none !important; /* Por si el tema lo trata como lista */
  }

  /* LA TARJETA VISIBLE */
  .post-preview {
    display: flex;             
    flex-direction: column;    
    justify-content: center;
    
    width: 100% !important;    /* Asegura el ancho completo */
    box-sizing: border-box !important; /* Evita que el padding rompa el ancho */
    
    background: rgba(25, 25, 35, 0.6) !important; 
    border: 1px solid rgba(84, 11, 163, 0.1) !important;
    border-radius: 15px !important; 
    padding: 20px 25px !important; 
    
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    backdrop-filter: blur(5px); 
    -webkit-backdrop-filter: blur(5px);
    text-decoration: none !important;
  }

  /* EFECTO HOVER */
  .post-preview:hover {
    background: rgba(84, 11, 163, 0.25) !important; 
    border: 1px solid rgba(132, 0, 255, 0.5) !important; 
    box-shadow: 0 0 25px rgba(84, 11, 163, 0.35) !important; 
    transform: translateY(-4px); 
    z-index: 10;
  }

  /* --- TIPOGRAFÍA --- */

  /* Título */
  .card-title { 
    color: #e0e0e0 !important; 
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 10px;
    margin-top: 0 !important;
    transition: color 0.3s;
  }
  .post-preview:hover .card-title { 
    color: #ffffff !important; 
    text-shadow: 0 0 10px rgba(132,0,255,0.4); 
  }

  /* Texto Resumen */
  .card-text p { 
    color: #a0a0a0 !important; 
    font-size: 0.95rem;
    margin-bottom: 15px;
    line-height: 1.5;
  }
  .post-preview:hover .card-text p { color: #dcdcdc !important; }

  /* Metadata */
  .post-meta {
    color: #828282 !important;
    font-size: 0.85rem;
    display: flex;
    flex-wrap: wrap; /* Para móviles */
    gap: 15px; /* Espacio entre fecha y categorías */
    align-items: center;
  }
  
  .meta-item {
    display: flex;
    align-items: center;
  }

  .post-preview:hover .post-meta { color: #d4b3ff !important; }
  .post-preview:hover .post-meta i { color: #d4b3ff !important; }


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