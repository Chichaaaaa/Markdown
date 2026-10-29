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