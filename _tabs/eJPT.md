---
layout: page
icon: fas fa-shield-virus
order: 1
title: eJPT
permalink: /ejpt/
---
<h1 class="subtitulo-pegado">Junior Penetration Tester</h1>

La reconocida certificación eJPT mide nuestra capacidad para enumerar redes desconocidas y pivotar manualmente mediante enrutamiento estático, además de dominar los fundamentos de Metasploit. Aquí te dejo mi "Cheat Sheet" o chuleta de referencia.

## Mi preparación para eJPTv2
Este esquema cubre el ciclo de vida de una auditoría para la certificación eJPT, lo he enfocado en la Metodología, Routing y Metasploit. Exactamente he dividido el examen en 6 fases o secciones, las cuales se muestran a continuación.

### 1. Networking & Routing
El objetivo de la primera fase es entender dónde estás y alcanzar las redes ocultas. A diferencia de otros exámenes, aquí debes configurar tu enrutamiento manual.

**Identificación de Red**
* `ip a` / `ifconfig`: Ver tu IP y máscara.
* `ip route`: Ver la tabla de rutas actual.

**Descubrimiento de Hosts (Ping Sweep)**
* `fping -a -g 192.168.1.0/24 2>/dev/null`
* `nmap -sn 192.168.1.0/24`: Lo estándar.

**Agregar Rutas (Pivoting Básico)**<br>
Estamos en el escenario en el que hemos comprometido una máquina con dos interfaces.
* Linux: `ip route add 10.10.10.0/24 via <IP_GATEWAY_INTERNA>`
* Windows: `route add 10.10.10.0 mask 255.255.255.0 <IP_GATEWAY>`

### 2. Enumeración & Reconocimiento
El siguiente paso se centra en mapear puertos y servicios vulnerables.

**Nmap (Escaneo de Puertos)**
* `nmap -sC -sV -p- <IP>`: Scripts por defecto y versiones.
* `nmap -sU <IP>`: No nos quedamos sólamente en el protocolo TCP y revisamos también UDP (común en eJPT para SNMP).

**Web Enumeration (HTTP/HTTPS)**
* Nikto: `nikto -h <URL>` (Vieja escuela pero útil para fallos de config).
* Dirbusting:
  `gobuster dir -u <URL> -w /usr/share/wordlists/dirb/common.txt -x php,txt,html`
* Inspección Manual: Ver código fuente (`Ctrl+U`), `robots.txt`.

### 3. Web Attacks (Client-Side & Server-Side)
Llegamos a la fase donde debemos explotar aplicaciones web mal configuradas o vulnerables.

**SQL Injection (SQLi)**
* Manual: Probar `' OR 1=1 -- -` en paneles de login.
* SQLMap: `sqlmap -u "http://target.com/page.php?id=1" --dbs --batch` (Permitido y recomendado).

**Cross-Site Scripting (XSS)**
* Reflejado: ``<script>alert(1)</script>`` en inputs de búsqueda.
* Robo de Cookies: `document.cookie`.

**Brute Force Web**
* Hydra: 
  `hydra -l admin -P /usr/share/wordlists/rockyou.txt <IP> http-post-form "/login.php:user=^USER^&pass=^PASS^:F=incorrect"`

### 4. System Attacks & Exploitation
Ganamos acceso al sistema mediante RCE (Remote Code Execution).

**Búsqueda de Vulnerabilidades**
* `searchsploit "nombre servicio versión"`
* Google Hacking: `"Apache 2.4.xx exploit github"`.

**Metasploit Framework (Muy importante en eJPT)**
1. `search <servicio>`
2. `use exploit/...`
3. `set RHOSTS <IP>`
4. `check`: Verificar si es vulnerable antes de atacar.
5. `exploit`: Lanzar el ataque.

**Brute Force de Servicios**
* SSH: `hydra -L users.txt -P pass.txt ssh://<IP>`
* RDP: `hydra -L users.txt -P pass.txt rdp://<IP>`

### 5. Privilege Escalation
Aquí tendremos que elevar privilegios a SYSTEM (Windows) o Root (Linux).

**Windows PrivEsc**
* Meterpreter: `getsystem` (Intento automático).
* Enumeración Manual:
  * `whoami /priv`
  * `net user <usuario>` (Ver grupos).
  * `systeminfo` (Ver versión del SO y parches para Kernel Exploits).

**Linux PrivEsc**
* Sudo: `sudo -l` (¿Qué puedo ejecutar como root sin contraseña?).
* SUID: `find / -perm -u=s -type f 2>/dev/null` (Buscar binarios con permisos especiales).
* Kernel: `uname -a` (Buscar "Dirty Cow" u otros exploits viejos).

### 6. Post-Exploitation
En esta fase el objetivo es encontrar las "banderas", hashes o archivos finales.

**Búsqueda de Archivos (Linux)**
* `find / -name "flag.txt" 2>/dev/null`
* `grep -r "password" /home/`

**Búsqueda de Archivos (Windows)**
* `dir /s flag.txt`
* `type C:\Users\Administrator\Desktop\flag.txt`

**Cracking de Hashes**<br>
Si encuentras hashes en `/etc/shadow` o bases de datos:
* John: `john --wordlist=rockyou.txt hash.txt`
* Hashcat: `hashcat -m <modo> -a 0 hash.txt rockyou.txt`

---

<style>
  /* 1. Título principal de la página con degradado */
  h1 {
    background: linear-gradient(90deg, #6a11cb, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 800;
    width: fit-content;
    display: inline-block;
    
    margin-bottom: 0px !important;
    padding-bottom: 0px !important;
    line-height: 1 !important; 
    text-shadow: 0px 0px 30px rgba(69, 104, 220, 0.2);
  }
  
  /* 2. ESTILO ESPECÍFICO PARA EL SUBTÍTULO */
  .subtitulo-pegado {
    /* Estética */
    font-size: 1.5em;
    font-weight: 500 !important;
    font-style: italic !important;
    
    position: relative !important;
    top: -25px !important;  /* <--- CAMBIAR ESTE NÚMERO. -60px subirá mucho más. */
    
    /* Reseteamos el margen para que no estorbe */
    margin-top: 0px !important;
    display: block !important; /* Asegura que ocupe su propia línea */
  }

  /* AL PASAR EL RATÓN (SOLUCIÓN DE LEGIBILIDAD) */
  #sidebar .nav-link:hover {
    color: #ffffff !important; /* TEXTO BLANCO (Se lee perfecto) */
    background: rgba(84, 11, 163, 0.4) !important; /* Fondo Morado Transparente */
    border-radius: 10px;
    box-shadow: 0 0 15px rgba(84, 11, 163, 0.4); /* Resplandor */
  }
  
  #sidebar .nav-link:hover i {
    color: #ffffff !important; /* Icono Blanco */
  }

  /* Iconos de abajo */
  #sidebar .sidebar-bottom a, #sidebar .sidebar-bottom i { color: #a3b8ff !important; }
  #sidebar .sidebar-bottom a:hover, #sidebar .sidebar-bottom i:hover { color: #9d52ffff !important; }


  /* 4. Icono del escudo en la barra lateral */
  #sidebar .nav-item.active .nav-link i {
    color: #4568dc !important;
  }
  
  /* 5. Subtítulos y enlaces */
  h2, h3, a {
    color: #a3b8ff; 
  }
  a:hover {
    color: #6a11cb; 
    text-decoration: none;
  }
</style>
