# Seguridad y Protección de Datos Sensibles

Este proyecto implementa medidas básicas de seguridad para evitar la exposición de información confidencial en el control de versiones.

## Archivos Excluidos

El archivo `.gitignore` impide que se suban al repositorio los siguientes tipos de archivos:

### 1. Archivos de configuración y credenciales
- `.env`, `*.env.local`, `config/*.yaml`, etc.
- Contienen variables de entorno, contraseñas, claves API o rutas privadas.
- **Riesgo:** Exponerlos públicamente podría permitir acceso no autorizado a servicios o bases de datos.

### 2. Archivos temporales y logs
- `*.log`, `*.tmp`, `*.cache`, `*.bak`
- Contienen datos de depuración o información de uso interno del sistema.
- **Riesgo:** Podrían incluir trazas con datos personales o de sesión.

### 3. Archivos de sistema o de IDE
- `.idea/`, `.vscode/`, `.DS_Store`, `Thumbs.db`
- Son específicos del entorno de desarrollo de cada usuario.
- **Riesgo:** No aportan valor al proyecto y pueden causar conflictos o fugas de configuración local.

### 4. Binarios y dependencias
- `vendor/`, `node_modules/`, `dist/`, `build/`
- Se generan automáticamente a partir del código fuente.
- **Riesgo:** Aumentan el tamaño del repositorio y pueden incluir componentes de terceros con licencias o código no verificable.

### 5. Archivos personales o locales
- `*.local`, `*.secret`
- Configuraciones personales del desarrollador.
- **Riesgo:** Pueden contener datos privados o información irrelevante para el resto del equipo.

## Buenas Prácticas

- Nunca subir credenciales o claves reales al repositorio.
- Usar variables de entorno y archivos `.env` (que no se suben) para configuraciones sensibles.
- Revisar los commits antes de subirlos para evitar filtraciones accidentales.
- En caso de subir información sensible por error, **revocar inmediatamente las claves comprometidas** y purgar el historial del repositorio.

---

¿Quieres que te lo prepare como archivos descargables (`.gitignore` y `SECURITY.md`) para tu proyecto?
