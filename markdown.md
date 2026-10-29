# Despliegue de Servicios Web en Entornos de Producción

## 1. Introducción y Requisitos del Sistema

La **implantación de aplicaciones web** requiere una configuración cuidadosa del entorno, garantizando que cada *servicio* opere de forma aislada y segura mediante utilidades como `systemctl status nginx`.

### Flujo de Instalación

1. Actualizar los índices de paquetes del repositorio.
2. Descargar e instalar el servidor web y dependencias.
3. Configurar los cortafuegos perimetrales para tráfico HTTP y HTTPS.

### Componentes Principales

* Servidor HTTP (Nginx / Apache)
* Gestor de bases de datos relacionales
* Certificados de seguridad TLS/SSL con Certbot

---

## 2. Automatización y Configuración

El siguiente script en Bash automatiza el aprovisionamiento inicial:

```bash
#!/bin/bash
sudo apt update && sudo apt upgrade -y
sudo apt install nginx git -y
sudo systemctl enable --now nginx
```

Para consultar los requisitos técnicos detallados del proyecto, visita el documento de [Detalles Técnicos](docs/detalles.md).  
Para más información general sobre servidores, visita el portal oficial de [Nginx Docs](https://nginx.org/en/docs/).

---

## 3. Galería Multimedia

### Diagrama Local del Despliegue
![Diagrama Local](assets/mi-imagen.png)

### Centro Educativo (Wikimedia Commons)
![IES Clara del Rey]
![Logo](https://upload.wikimedia.org/wikipedia/commons/7/77/Wikimedia_Foundation_logo_-_horizontal.svg)
---

## 4. Comparativa de Servidores Web

| Servidor Web | Modelo de Concurrencia | Uso Recomendado |
| :--- | :--- | :--- |
| Nginx | Asíncrono / Event-driven | Proxy inverso y alta concurrencia |
| Apache | Basado en procesos / hilos | Compatibilidad y módulos `.htaccess` |
