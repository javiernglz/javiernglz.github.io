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
  /* --- 1. BARRA LATERAL (INTOCABLE - ES TU REFERENCIA) --- */
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
    border-radius: 10px; /* Aseguramos la forma base */
  }
  #sidebar .nav-link i { color: #8eaafb !important; }

  /* EL EFECTO QUE TE GUSTA */
  #sidebar .nav-link:hover {
    color: #ffffff !important;
    background: rgba(84, 11, 163, 0.4) !important; 
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4);
  }
  #sidebar .nav-link:hover i { color: #ffffff !important; }

  #sidebar .sidebar-bottom a, #sidebar .sidebar-bottom i { color: #a3b8ff !important; }
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover { color: #9d52ffff !important; }


  /* --- 2. ARTÍCULOS CENTRALES (EL ARREGLO IMPORTANTE) --- */
  
  .post-preview {
    /* Forma base más suave */
    border-radius: 15px !important; 
    padding: 15px !important;
    margin: -15px !important; /* Compensar el padding para que no se mueva */
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1); /* Animación fluida */
    border: 1px solid transparent; /* Para que el borde no salte al aparecer */
  }

  /* HOVER DEL ARTÍCULO: Estilo "Cristal Tecnológico" */
  .post-preview:hover {
    /* 1. Fondo más sutil que en el sidebar para no saturar, pero visible */
    background: rgba(84, 11, 163, 0.15) !important; 
    
    /* 2. Borde brillante para definir la forma (esto da el toque pro) */
    border: 1px solid rgba(132, 0, 255, 0.5) !important;
    
    /* 3. El mismo resplandor que el sidebar */
    box-shadow: 0 0 20px rgba(84, 11, 163, 0.3) !important;
    
    /* 4. Movemos la tarjeta un pelín hacia la derecha para dar dinamismo */
    transform: translateX(5px);
    text-decoration: none !important;
  }

  /* Textos dentro del artículo al hacer hover */
  .post-preview:hover .card-title { color: #ffffff !important; } /* Título blanco puro */
  .post-preview:hover .card-text p { color: #dcdcdc !important; } /* Texto casi blanco */
  .post-preview:hover .post-meta { color: #d4b3ff !important; } /* Metadata lila */
  .post-preview:hover i { color: #d4b3ff !important; } /* Iconos lila */

  .card-title { color: #e0e0e0 !important; transition: color 0.3s; }


  /* --- 3. PANEL DERECHO & TAGS (AHORA IDENTICOS AL SIDEBAR) --- */
  
  #panel-wrapper h3, #panel-wrapper .panel-heading { color: #828282 !important; }
  
  /* Enlaces de "Updated Recent" */
  #panel-wrapper li a { 
    color: #a3b8ff !important; 
    transition: all 0.2s;
    display: block; 
    padding: 5px 10px; /* Les damos cuerpo */
    border-radius: 8px; /* Redondeados */
  }
  
  #panel-wrapper li a:hover { 
    color: #ffffff !important; 
    background: rgba(84, 11, 163, 0.3); /* Fondo coherente */
    text-decoration: none !important;
    box-shadow: 0 0 10px rgba(84, 11, 163, 0.2);
  }

  /* TAGS - Las pastillas */
  .post-tag {
    background: transparent !important;
    color: #a3b8ff !important;
    border: 1px solid rgba(84, 11, 163, 0.3) !important;
    border-radius: 20px !important; /* MUY REDONDOS (Pill shape) */
    padding: 5px 12px;
    transition: all 0.3s ease;
  }

  /* TAGS HOVER - COPIA EXACTA DEL SIDEBAR */
  .post-tag:hover {
    background: rgba(84, 11, 163, 0.5) !important; /* Fondo intenso */
    color: #ffffff !important;
    border-color: transparent !important; /* El borde desaparece, queda la luz */
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.6) !important; /* Glow fuerte */
    transform: scale(1.05); /* Pequeño pop para que se sienta táctil */
  }

</style>