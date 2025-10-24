# POLÍTICA DE SEGURIDAD

La seguridad del código fuente y la protección de los datos sensibles son aspectos fundamentales para este proyecto.  
Todas las contribuciones deben seguir las normas descritas a continuación con el fin de preservar la integridad del repositorio y evitar la exposición de información confidencial.

---

## 1. PROCEDIMIENTO PARA REPORTAR VULNERABILIDADES

En caso de detectar una vulnerabilidad o comportamiento sospechoso, **no publiques la información de forma pública** ni crees un Issue o Pull Request que la revele.

Para mantener la seguridad del proyecto y de sus usuarios, los informes deben enviarse de manera privada.

**Pasos a seguir:**

1. Envía un correo electrónico con los detalles a **[tuncorreo@email.com]**.  
2. Incluye en tu mensaje:
   - Una descripción clara del problema detectado.  
   - Pasos concretos para reproducir el error o vulnerabilidad.  
   - La versión o *commit hash* donde se encontró el fallo.  

El equipo de mantenimiento responderá en un plazo máximo de **48 horas**.  
Mientras se trabaja en la solución, se pide mantener la información en confidencialidad hasta que se publique una corrección oficial.

---

## 2. ARCHIVOS EXCLUIDOS DEL CONTROL DE VERSIONES

El archivo `.gitignore` se utiliza para impedir que ciertos ficheros sean rastreados por Git, evitando así subir información privada, archivos temporales o dependencias generadas automáticamente.

### Archivos temporales y de registro

Estos archivos se excluyen para evitar la exposición de información de depuración o datos internos.

| Patrones | Motivo |
|-----------|--------|
| `*.log`, `logs/` | Los registros pueden contener información sensible o datos irrelevantes para el repositorio. |
| `npm-debug.log*`, `yarn-debug.log*` | Archivos de depuración generados por gestores de paquetes; varían según el entorno local. |

### Dependencias y archivos generados

Excluir dependencias y archivos de compilación evita inconsistencias y mantiene el repositorio ligero y reproducible.

| Patrones | Motivo |
|-----------|--------|
| `node_modules/` | Contiene dependencias externas que deben instalarse mediante `package.json`. |
| `dist/`, `build/`, `.vite/` | Archivos generados durante la compilación; pueden regenerarse localmente. |
| `.eslintcache` | Caché temporal de herramientas de análisis; no aporta valor al repositorio. |

### Configuraciones locales y del entorno de desarrollo

Estos archivos almacenan configuraciones personales o datos sensibles que no deben compartirse.

| Patrones | Motivo |
|-----------|--------|
| `*.local`, `.env*` | Pueden incluir claves API, credenciales o rutas privadas. |
| `.vscode/`, `.idea/` | Configuraciones específicas del entorno de cada desarrollador. |
| `.DS_Store`, `*.suo`, `*.sln` | Archivos del sistema operativo o del IDE sin relevancia para el proyecto. |

---

## 3. PROTECCIÓN DE LA DOCUMENTACIÓN Y DEL REPOSITORIO

La documentación se considera parte crítica del proyecto y debe protegerse con las mismas medidas que el código fuente.

### Ramas protegidas

- La rama principal (`main` o `master`) está configurada como protegida.  
- No se permiten *pushes* directos sobre ella.  
- Todos los cambios deben realizarse a través de *pull requests* (PRs).  
- Se requiere al menos una revisión aprobada antes de fusionar una PR.  
- Si existen pruebas automatizadas, estas deben superarse antes de la integración.

### Revisión de cambios

Cada *pull request* debe revisarse por un colaborador autorizado, verificando:

- La exactitud y claridad de la documentación.  
- Que no se introduzcan claves, contraseñas o datos privados.  
- Que los cambios cumplan con las normas del proyecto.

### Auditoría del historial

- Se fomenta el uso de mensajes de *commit* claros y descriptivos.  
- No se permite el uso de `git push --force` sobre ramas compartidas o principales.  
- El historial debe mantenerse completo para facilitar la trazabilidad y auditoría.

---

## 4. RECUPERACIÓN DEL REPOSITORIO Y COPIAS DE SEGURIDAD

En caso de pérdida de datos o fallo grave, se dispone de mecanismos para restaurar el repositorio y mantener la continuidad del desarrollo.

### Copias de seguridad

- Se realizan **copias de seguridad automáticas y diarias** del repositorio completo en un servicio externo independiente.  
- Las copias se conservan durante al menos **30 días**.  
- Se ejecutan **pruebas trimestrales de restauración** para comprobar la integridad de los respaldos.

### Redundancia del hosting

- El proyecto se mantiene replicado en **dos plataformas diferentes** (por ejemplo, GitHub y GitLab) para evitar interrupciones del servicio principal.  

### Historial distribuido de Git

- Cada clon del repositorio contiene una copia completa del historial, lo que permite recuperar el proyecto incluso si el repositorio central se pierde.  
- En caso de corrupción, cualquier colaborador con una copia actualizada puede restaurar el estado anterior.

---

## 5. BUENAS PRÁCTICAS GENERALES

- No subir nunca contraseñas, claves o tokens de acceso.  
- Usar archivos `.env` (no versionados) para configuraciones sensibles.  
- Revisar los cambios antes de hacer *commit* o *push*.  
- Activar autenticación en dos pasos (2FA) en los servicios de alojamiento.  
- Mantener actualizado el entorno de desarrollo y dependencias de seguridad.
