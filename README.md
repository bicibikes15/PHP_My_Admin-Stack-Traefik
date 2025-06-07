# Stack de phpMyAdmin para Traefik by DigitAllFran

Este stack despliega phpMyAdmin, la popular herramienta de gestión de bases de datos MySQL/MariaDB, y la configura para ser gestionada y asegurada por un stack de Traefik existente.

## Arquitectura y Dependencias

Esta es una herramienta de administración que depende de tu ecosistema para ser útil.

#### **Prerrequisitos Indispensables:**

1.  **El Guardián (Traefik):** Necesitas una instancia de Traefik v3 funcionando.
    * **Stack Recomendado:** [Stack de Traefik de DigitAllFran](https://github.com/bicibikes15/Traefik)

2.  **El Arsenal (Bases de Datos):** Necesitas una instancia de MariaDB o MySQL corriendo. Este stack está diseñado para conectarse al:
    * **[Stack Global de Bases de Datos de DigitAllFran](https://github.com/bicibikes15/Globals-Databases)**

3.  **La Red Compartida:** El estandarte oficial de este ecosistema es `digitallfran_net`.

## El Ritual de Invocación (Instalación)

**1. Clonar el Repositorio**
```bash
git clone [https://github.com/tu-github/phpMyAdmin-Stack.git](https://github.com/tu-github/phpMyAdmin-Stack.git)
cd phpMyAdmin-Stack

2. Verificar la Red Externa

Asegúrate de que la red digitallfran_net existe. Si no, créala:

Bash

docker network create digitallfran_net

3. Configurar las Coordenadas

Crea tu archivo de configuración local a partir de la plantilla.

Bash

cp .env.example .env
Edita el archivo .env (nano .env) y establece los valores:

PHPMYADMIN_DOMAIN: El subdominio que usarás para acceder a phpMyAdmin.
PMA_HOST: Crucial. Este debe ser el nombre del contenedor de tu servicio de MariaDB (ej. mariadb, o mariadb_global si usas el stack de DigitAllFran).

4. Desplegar el Stack

Bash

docker compose up -d
Verificación
Visita el dominio que configuraste. Verás la pantalla de login de phpMyAdmin. Puedes usar cualquier credencial válida de tu servidor MariaDB para entrar (como el usuario root o los usuarios específicos de cada sitio web).