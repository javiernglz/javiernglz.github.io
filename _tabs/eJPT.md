---
layout: page
icon: fas fa-shield-virus
order: 1
title: eJPT
permalink: /ejpt/
---

<small>_Haz clic en un título para leer el artículo completo y acceder a las 
descargas:_</small>
La reconocida certificación eJPT evalúa la capacidad para enumerar redes desconocidas y pivotar manualmente mediante enrutamiento estático, además de dominar los fundamentos de Metasploit. Aquí te dejo mi "Cheat Sheet" o chuleta de referencia.

Cheatsheet: Preparación eJPTv2 (Junior Penetration Tester)
Este mapa mental cubre el ciclo de vida de una auditoría para la certificación eJPT, enfocado en Metodología, Routing y Metasploit.

1. Networking & Routing
Objetivo: Entender dónde estás y alcanzar las redes ocultas. A diferencia de otros exámenes, aquí debes configurar tu enrutamiento manual.

Identificación de Red:

ip a / ifconfig: Ver tu IP y máscara.

ip route: Ver la tabla de rutas actual.

Descubrimiento de Hosts (Ping Sweep):

fping -a -g 192.168.1.0/24 2>/dev/null: Rápido y limpio.

nmap -sn 192.168.1.0/24: Estándar.

Agregar Rutas (Pivoting Básico):

Escenario: Has comprometido una máquina con dos interfaces.

ip route add 10.10.10.0/24 via <IP_GATEWAY_INTERNA>: Comando clave en Linux.

Windows: route add 10.10.10.0 mask 255.255.255.0 <IP_GATEWAY>

2. Enumeración & Reconocimiento
Objetivo: Mapear puertos y servicios vulnerables.

Nmap (Escaneo de Puertos):

nmap -sC -sV -p- <IP>: Scripts por defecto y versiones.

nmap -sU <IP>: No olvides el escaneo UDP (común en eJPT para SNMP).

Web Enumeration (HTTP/HTTPS):

Nikto: nikto -h <URL>. (Vieja escuela pero muy útil en eJPT para encontrar fallos rápidos de configuración).

Dirbusting:

gobuster dir -u <URL> -w /usr/share/wordlists/dirb/common.txt -x php,txt,html

Inspección Manual: Ver código fuente (Ctrl+U), robots.txt.

3. Web Attacks (Client-Side & Server-Side)
Objetivo: Explotar aplicaciones web mal configuradas o vulnerables.

SQL Injection (SQLi):

Manual: Probar ' OR 1=1 -- - en paneles de login.

SQLMap: sqlmap -u "http://target.com/page.php?id=1" --dbs --batch (Permitido y recomendado).

Cross-Site Scripting (XSS):

Reflejado: <script>alert(1)</script> en inputs de búsqueda.

Robo de Cookies (Concepto): document.cookie.

Brute Force Web:

Hydra: hydra -l admin -P /usr/share/wordlists/rockyou.txt <IP> http-post-form "/login.php:user=^USER^&pass=^PASS^:F=incorrect"

4. System Attacks & Exploitation
Objetivo: Ganar acceso al sistema (Remote Code Execution).

Búsqueda de Vulnerabilidades:

searchsploit "nombre servicio versión"

Google Hacking: "Apache 2.4.xx exploit github".

Metasploit Framework (Tu mejor amigo en eJPT):

search <servicio>

use exploit/...

set RHOSTS <IP>

check: Verificar si es vulnerable antes de atacar.

exploit: Lanzar el ataque.

Brute Force de Servicios:

SSH: hydra -L users.txt -P pass.txt ssh://<IP>

RDP: hydra -L users.txt -P pass.txt rdp://<IP>

5. Privilege Escalation

Objetivo: Elevar privilegios a SYSTEM (Windows) o Root (Linux).

Windows PrivEsc:

Meterpreter: getsystem (Intento automático).

Enumeración Manual:

whoami /priv (Buscar SeImpersonate).

net user <usuario> (Ver grupos).

systeminfo (Ver versión del SO y parches para Kernel Exploits).

Linux PrivEsc:

Sudo: ´sudo -l´ (¿Qué puedo ejecutar como root sin contraseña?).

SUID: ´find / -perm -u=s -type f 2>/dev/null´ (Buscar binarios con permisos especiales).

Kernel: ´uname -a´ (Buscar "Dirty Cow" u otros exploits viejos si el kernel es antiguo).

### 6. Post-Exploitation

En esta fase el objetivo es encontrar las "banderas", hashes o archivos finales.

Búsqueda de Archivos (Linux):

´find / -name "flag.txt" 2>/dev/null´

´grep -r "password" /home/´

Búsqueda de Archivos (Windows):

´dir /s flag.txt´

´type C:\Users\Administrator\Desktop\flag.txt´

Cracking de Hashes:

Si encuentras hashes en /etc/shadow` o bases de datos:

John: `john --wordlist=rockyou.txt hash.txt`

Hashcat: `hashcat -m <modo> -a 0 hash.txt rockyou.txt`

---

<style>
  /* 1. Título principal de la página con degradado */
  h1 {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    font-weight: 800;
    text-shadow: 0px 0px 30px rgba(69, 104, 220, 0.2);
  }

  /* 2. Tu nombre en la Barra Lateral (J.avi Security) */
  #sidebar .site-title {
    background: linear-gradient(90deg, #540ba3, #4568dc) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
  }

  /* 3. El botón activo de la izquierda (la pastilla que ahora es gris/verde) */
  /* Lo ponemos morado oscuro con texto brillante */
  #sidebar .nav-item.active .nav-link {
    background: rgba(125, 42, 232, 0.15) !important; /* Fondo lila transparente */
    color: #bfa3ff !important; /* Texto lila claro */
    border: 1px solid rgba(125, 42, 232, 0.3) !important;
    box-shadow: 0 0 10px rgba(125, 42, 232, 0.2);
  }

  /* 4. Icono del escudo en la barra lateral */
  #sidebar .nav-item.active .nav-link i {
    color: #4568dc !important;
  }
  
  /* 5. Subtítulos y enlaces (para que no sean verdes) */
  h2, h3, a {
    color: #a3b8ff; /* Azul hielo suave en lugar de verde */
  }
  a:hover {
    color: #b06ab3; /* Morado al pasar el ratón */
    text-decoration: none;
  }
</style>

  

