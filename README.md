<div align="center">
  <img src="https://cdn.jsdelivr.net/npm/simple-icons@v11/icons/phpmyadmin.svg" alt="phpMyAdmin Logo" width="120"/>
  <h1 align="center">Stack de phpMyAdmin para Traefik by DigitAllFran</h1>
  <p>
    <img src="https://img.shields.io/badge/phpMyAdmin-5.x-orange?style=for-the-badge&logo=phpmyadmin&logoColor=white" alt="phpMyAdmin"/>
    <img src="https://img.shields.io/badge/Traefik-v3-blueviolet?style=for-the-badge&logo=traefikproxy&logoColor=white" alt="Traefik v3"/>
    <img src="https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white" alt="MariaDB"/>
    <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL"/>
    <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  </p>
</div>

> [!NOTE]
> **Gestión visual de bases de datos**  
> phpMyAdmin expuesto y asegurado por Traefik, listo para administrar tus instancias de MariaDB/MySQL desde cualquier parte.

> [!TIP]
> **Arquitectura y dependencias**
> - **Traefik v3** como proxy inverso ([Stack recomendado](https://github.com/bicibikes15/Traefik))
> - **MariaDB/MySQL** corriendo en la misma red ([Stack recomendado](https://github.com/bicibikes15/Globals-Databases))
> - **Red Docker externa:** `digitallfran_net`

> [!IMPORTANT]
> **El Ritual de Invocación (Instalación)**
> 1. **Clona el repositorio:**
>    ```
>    git clone https://github.com/bicibikes15/phpMyAdmin-Stack-Traefik.git
>    cd phpMyAdmin-Stack-Traefik
>    ```
> 2. **Verifica o crea la red externa:**
>    ```
>    docker network create digitallfran_net
>    ```
> 3. **Configura las coordenadas (.env):**
>    ```
>    cp .env.example .env
>    # Edita .env y define:
>    # PHPMYADMIN_DOMAIN=tu subdominio (ej. pma.tudominio.com)
>    # PMA_HOST=nombre del contenedor de MariaDB/MySQL (ej. mariadb_global)
>    ```
> 4. **Despliega el stack:**
>    ```
>    docker compose up -d
>    ```

> [!WARNING]
> **Verificación y acceso**  
> Traefik asignará el certificado SSL y expondrá phpMyAdmin en tu subdominio configurado.  
> Accede a `https://<PHPMYADMIN_DOMAIN>` y usa cualquier usuario válido de tu MariaDB/MySQL.

> [!NOTE]
> **¿Todo funcionando?**  
> Si ves la pantalla de login y puedes entrar, ¡listo!  
> Tienes gestión visual y segura de tus bases de datos, bajo el escudo DigitAllFran.

---

<div align="center">
  <a href="https://digitallfran.co" target="_blank">
    <img src="https://digitallfran.co/logo.svg" alt="DigitAllFran Logo" width="90"/><br>
    <b>¿Necesitas soporte, automatización o seguridad para tus bases de datos?</b><br>
    <span style="font-size:1.1em;">
      <strong>¡Visita <u>digitallfran.co</u> y agenda tu consulta!</strong>
    </span>
  </a>
</div>
