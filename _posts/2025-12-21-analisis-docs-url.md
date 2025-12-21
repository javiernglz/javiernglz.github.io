---
layout: post
title: "Análisis de malware en Documentos y URLs"
date: 2025-12-21
categories: [Blue Team]
---

[cite_start]Análisis de malware en Documentos y URLs [cite: 1]

[cite_start]A continuación se detallan los diferentes métodos y herramientas para verificar la legitimidad de archivos y enlaces web. [cite: 2]

[cite_start]Las técnicas se clasifican según la sensibilidad de la información. [cite: 3]

## [cite_start]1. Análisis de Documentos (PDF y Office) [cite: 4]

### [cite_start]Identificación Básica (Cualquier archivo) [cite: 5]

| Objetivo | Herramienta | Descripción | Comando |
| :--- | :--- | :--- | :--- |
| Identificar tipo | file | Detecta la extensión real. | `file <archivo>` |
| Obtener Hash | sha256sum | Genera firma para buscar reputación online. | `sha256sum <archivo>` |
[cite_start][cite: 6]

### [cite_start]Documento confidencial (Análisis Local / Sin Internet) [cite: 7]

| Objetivo | Herramienta | Descripción | Comando |
| :--- | :--- | :--- | :--- |
| Detectar Macros | olevba | Extrae código VBA malicioso de Office. | `olevba <archivo>` |
| Triaje PDF | pdfid | "Cuenta elementos peligrosos (/JS, /AA)." | `pdfid <archivo>` |
| Explorar PDF | pdf-parser | Busca y decodifica scripts ocultos. | `pdf-parser --search javascript <archivo>` |
| Extraer Obj. | pdf-parser | Extrae contenido raw de un objeto (ID). | `pdf-parser -o <id> -r -f <archivo>` |
| Metadatos | exiftool | Muestra autor y software de creación. | `exiftool <archivo>` |
| Simular Red | FakeNet-NG | Captura peticiones C2 sin salir a internet. | `fakenet (En VM)` |
[cite_start][cite: 8]

### [cite_start]Documento público (Solo archivos genéricos) [cite: 9]

| Objetivo | Herramienta | Descripción |
| :--- | :--- | :--- |
| Sandbox Visual | Any.Run | Ejecución interactiva en la nube. |
| Reporte Completo | Hybrid Analysis | Análisis detallado de comportamiento y red. |
[cite_start][cite: 10]

## [cite_start]2. Análisis de URLs [cite: 11]

### [cite_start]URL confidencial (Spear Phishing / Tokens) [cite: 12]

[cite_start]Métodos pasivos o sin ejecución de código. [cite: 13]

| Objetivo | Herramienta | Descripción | Comando |
| :--- | :--- | :--- | :--- |
| Decodificar | CyberChef | "Limpia URLs ofuscadas (Base64, %20)." | - |
| Info Dominio | whois | Consulta fecha de creación del dominio. | `whois <dominio>` |
| IP del servidor | dig | Obtiene la IP sin conectar por HTTP. | `dig <dominio> +short` |
| Visita Segura | curl | Pide cabeceras sin ejecutar scripts. | `curl -I -L --user-agent "Mozilla/5.0" "<url>"` |
[cite_start][cite: 14]

### [cite_start]URL Pública (Spam) [cite: 15]

| Objetivo | Herramienta | Descripción |
| :--- | :--- | :--- |
| Ver la web | UrlScan.io | Captura de pantalla y código DOM remoto. |
| Reputación | VirusTotal | Consulta listas negras de antivirus. |
| Navegar | Browserling | Navegador desechable online. |
[cite_start][cite: 16]