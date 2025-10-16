# 🚀 Clase 2: Reforzamiento de Git y Primera API con FastAPI

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://fastapi.tiangolo.com/img/logo-margin/logo-teal.png"
          alt="FastAPI Logo"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

## 🎯 Objetivos de aprendizaje
- 🔄 Reforzar los conceptos básicos de Git y control de versiones
- 🐍 Introducir Python como lenguaje para desarrollo backend
- ⚡ Aprender los fundamentos de FastAPI para crear APIs REST
- 🔌 Comprender qué es una API REST y las operaciones CRUD
- 🔢 Entender los códigos de estado HTTP más comunes
- 🌐 Crear y probar tu primera API funcional
- 📤 Publicar cambios en GitHub desde tu repositorio local

---

## 🔄 Actividad inicial: Reforzamiento de Git

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://git-scm.com/images/logos/downloads/Git-Logo-2Color.png"
          alt="Git Logo"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

### 🎯 ¿Por qué reforzar Git?
En la clase anterior, algunos tuvieron dificultades con Git. Hoy haremos una actividad práctica paso a paso para asegurar que todos dominen los conceptos básicos antes de continuar con el desarrollo de APIs.

### 💻 Actividad práctica de Git (20 minutos)

#### Paso 1: Preparación del entorno
1. **📥 Clona tu repositorio** (si no lo hiciste en clase 1):
   ```bash
   git clone https://github.com/TU_USUARIO/curso-backend-fumc.git
   cd curso-backend-fumc
   ```

2. **💻 Abre el proyecto en VS Code:**
   - Abre VS Code
   - File → Open Folder
   - Selecciona la carpeta de tu repositorio clonado

3. **⚙️ Verifica la configuración de Git** (en el terminal integrado de VS Code):
   ```bash
   git config --global user.name
   git config --global user.email
   ```
   Si no aparecen tus datos, configúralos:
   ```bash
   git config --global user.name "Tu Nombre Completo"
   git config --global user.email "tu@email.com"
   ```

#### Paso 2: Tu primer flujo completo de Git
1. **📊 Verifica el estado inicial** (en terminal de VS Code):
   ```bash
   git status
   ```

2. **📝 Crea un archivo de prueba** llamado `git-practice.md` usando VS Code:
   - Right-click en el explorador de archivos → New File
   - Nómbralo `git-practice.md`
   - Copia y pega el siguiente contenido:
   ```markdown
   # Práctica de Git - Clase 2

   ## Mi progreso con Git
   - ✅ Cloné el repositorio
   - ✅ Hice mi primer commit
   - ⏳ Estoy aprendiendo Git paso a paso

   ## Notas importantes
   - Git es fundamental para el desarrollo colaborativo
   - Cada commit debe tener un mensaje descriptivo
   ```

3. **➕ Agrega el archivo al staging** (terminal de VS Code):
   ```bash
   git add git-practice.md
   ```

4. **💾 Realiza tu primer commit**:
   ```bash
   git commit -m "Agrega archivo de práctica de Git - Clase 2"
   ```

5. **☁️ Sube los cambios a GitHub**:
   ```bash
   git push origin main
   ```

#### Paso 3: Más práctica con Git
1. **💻 Modifica el archivo** `git-practice.md` usando VS Code agregando:
   - Abre `git-practice.md` en VS Code
   - Agrega esta sección al final:
   ```markdown
   ## Comandos que aprendí hoy
   - `git status`: Ver estado del repositorio
   - `git add`: Agregar archivos al staging
   - `git commit`: Crear un commit
   - `git push`: Subir cambios al repositorio remoto
   ```

2. **💾 Haz otro commit** (terminal de VS Code):
   ```bash
   git add .
   git commit -m "Actualiza práctica de Git con comandos aprendidos"
   git push origin main
   ```

3. **📜 Revisa el historial**:
   ```bash
   git log --oneline
   ```

### ✅ Verificación
- Ve a tu repositorio en GitHub y verifica que aparezcan los commits
- El archivo `git-practice.md` debe estar visible en el repositorio

---

## 🐍 Introducción a Python para desarrollo backend

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM.png"
          alt="Python Logo"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

### 🤔 ¿Por qué Python?
- **📚 Sintaxis clara y legible** - Fácil de aprender
- **🔧 Versátil** - Web, ciencia de datos, automatización
- **📦 Gran ecosistema** - Miles de librerías disponibles
- **🚀 Popular en backend** - Usado por empresas como Instagram, Spotify, Netflix

### ⚙️ Instalación de Python
Si no tienes Python instalado:

**Windows:**
```bash
# Descarga desde https://python.org
# Durante instalación, marca "Add Python to PATH"
python --version  # Verifica instalación
```

**Verificación:**
```bash
python --version
# Debería mostrar Python 3.x.x
```

---

## 💻 Introducción a VS Code para desarrollo

<div style="width:40%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://code.visualstudio.com/assets/images/code-stable.png"
          alt="VS Code Logo"
          style="width:40%; height:40%; object-fit:cover; object-position:center;">
</div>

### 🎯 ¿Por qué VS Code?
- **🆓 Gratuito y open source** - Editor moderno y potente
- **🔧 Extensible** - Miles de extensiones para diferentes lenguajes
- **🐍 Soporte nativo para Python** - IntelliSense, debugging, etc.
- **📁 Integración con Git** - Control de versiones integrado
- **🌐 Terminal integrado** - Ejecuta comandos sin salir del editor

### 📥 Instalación de VS Code
**Opción 1: Instalación normal**
- Descarga desde: https://code.visualstudio.com/
- Instala normalmente en Windows

**Opción 2: Versión portable (si no puedes instalar)**
- Descarga la versión portable desde: https://code.visualstudio.com/docs/editor/portable
- Extrae en una carpeta (ej: `C:\VSCodePortable`)
- Ejecuta `Code.exe` desde la carpeta

### ⚙️ Configuración inicial
1. **Instala la extensión de Python:**
   - Abre VS Code
   - Ve a Extensions (Ctrl+Shift+X)
   - Busca "Python" y instala la oficial de Microsoft

2. **Configura el terminal integrado:**
   - Terminal → New Terminal
   - Verifica que puedas ejecutar `python --version`

### 💡 Consejos para usar VS Code
- **Abrir carpeta:** File → Open Folder (tu repositorio clonado)
- **Crear archivos:** Right-click en el explorador → New File
- **Terminal integrado:** View → Terminal (Ctrl+`)
- **Extensiones útiles:** Python, GitLens, Prettier

---

## ⚡ Introducción a FastAPI

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://fastapi.tiangolo.com/img/logo-margin/logo-teal.png"
          alt="FastAPI Logo"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

### 🎯 ¿Qué es FastAPI?
- **Framework moderno y rápido** para crear APIs REST con Python
- **Basado en estándares** como OpenAPI y JSON Schema
- **Documentación automática** - Genera docs interactivas
- **Validación automática** de datos
- **Asíncrono por defecto** - Alto rendimiento

### 🔧 Instalación de FastAPI
```bash
pip install fastapi uvicorn
```

**¿Qué instala?**
- `fastapi`: El framework principal
- `uvicorn`: Servidor ASGI para ejecutar la aplicación

---

## 🔌 Fundamentos de APIs REST y CRUD

<div style="width:100%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://images.ctfassets.net/vwq10xzbe6iz/5sBH4Agl614xM7exeLsTo7/9e84dce01735f155911e611c42c9793f/rest-api.png"
          alt="REST API Diagram"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

### 🤔 ¿Qué es una API REST?

**REST** = **RE**presentational **S**tate **T**ransfer

Es un **estilo de arquitectura** para diseñar APIs web que siguen principios específicos:

#### 🎯 Principios fundamentales de REST
1. **📋 Stateless (Sin estado):** Cada request es independiente, el servidor no guarda estado entre requests
2. **🌐 Client-Server:** Separación clara entre cliente (frontend) y servidor (backend)
3. **⚙️ Uniform Interface:** Interfaz uniforme usando HTTP methods estándar
4. **🔗 Resources:** Todo se trata como "recursos" identificados por URLs
5. **📦 Representations:** Los recursos se representan en formatos como JSON

### 🎭 ¿Por qué REST es importante?
- **✅ Estándar universal** - Entendido por todos los desarrolladores
- **🔄 Independiente del lenguaje** - Funciona con cualquier tecnología
- **📱 Escalable** - Soporta miles de clientes simultáneos
- **🛠️ Mantenible** - Arquitectura clara y predecible

---

## 📊 Operaciones CRUD en APIs REST

<div style="width:100%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://www.atatus.com/glossary/content/images/size/w960/2021/07/CRUD.jpeg"
          alt="CRUD Operations"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

**CRUD** son las **4 operaciones básicas** que puedes hacer con cualquier recurso en una API:

### 📖 **C**reate - Crear
- **Método HTTP:** `POST`
- **Propósito:** Crear un nuevo recurso
- **Ejemplo:** Registrar un nuevo usuario, crear un producto
- **Respuesta típica:** `201 Created`

### 📖 **R**ead - Leer
- **Método HTTP:** `GET`
- **Propósito:** Obtener información de un recurso
- **Ejemplo:** Ver perfil de usuario, listar productos
- **Respuesta típica:** `200 OK`

### 📝 **U**pdate - Actualizar
- **Método HTTP:** `PUT` (reemplaza completo) o `PATCH` (actualiza parcial)
- **Propósito:** Modificar un recurso existente
- **Ejemplo:** Cambiar email de usuario, actualizar precio de producto
- **Respuesta típica:** `200 OK` o `204 No Content`

### 🗑️ **D**elete - Eliminar
- **Método HTTP:** `DELETE`
- **Propósito:** Eliminar un recurso
- **Ejemplo:** Borrar cuenta de usuario, eliminar producto
- **Respuesta típica:** `204 No Content`

---

## 🌐 Métodos HTTP y URLs en REST

### 📋 Tabla completa de métodos HTTP comunes

| Método | CRUD | Descripción | Ejemplo URL | Cuerpo Request |
|--------|------|-------------|-------------|----------------|
| `GET` | **R**ead | Obtener datos | `/usuarios` | ❌ No |
| `GET` | **R**ead | Obtener un elemento | `/usuarios/123` | ❌ No |
| `POST` | **C**reate | Crear nuevo | `/usuarios` | ✅ Sí (JSON) |
| `PUT` | **U**pdate | Actualizar completo | `/usuarios/123` | ✅ Sí (JSON) |
| `PATCH` | **U**pdate | Actualizar parcial | `/usuarios/123` | ✅ Sí (JSON) |
| `DELETE` | **D**elete | Eliminar | `/usuarios/123` | ❌ No |

### 🎯 Ejemplos prácticos con una API de usuarios

**Crear usuario (POST):**
```bash
POST /usuarios
{
  "nombre": "Juan Pérez",
  "email": "juan@email.com",
  "edad": 25
}
```

**Obtener todos los usuarios (GET):**
```bash
GET /usuarios
# Respuesta: [{"id": 1, "nombre": "Juan Pérez", ...}, ...]
```

**Obtener usuario específico (GET):**
```bash
GET /usuarios/1
# Respuesta: {"id": 1, "nombre": "Juan Pérez", ...}
```

**Actualizar usuario (PUT):**
```bash
PUT /usuarios/1
{
  "nombre": "Juan Pérez García",
  "email": "juan.garcia@email.com",
  "edad": 26
}
```

**Eliminar usuario (DELETE):**
```bash
DELETE /usuarios/1
# Respuesta: 204 No Content
```

### 💡 Conceptos clave
- **📍 Endpoints:** Las URLs específicas de tu API
- **🔢 Status Codes:** Códigos que indican el resultado (200, 201, 404, 500, etc.)
- **📄 JSON:** Formato estándar para enviar/recibir datos
- **🔐 Headers:** Información adicional (Content-Type, Authorization, etc.)

---

## 🔢 Códigos de Estado HTTP

<div style="width:100%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*w_iicbG7L3xEQTArjHUS6g.jpeg"
          alt="HTTP Status Codes"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

Los **códigos de estado HTTP** son números de 3 dígitos que indican el resultado de una petición a un servidor. Son **cruciales** para entender si tu API funciona correctamente.
[https://httpstatusdogs.com](https://httpstatusdogs.com)

### 📊 Estructura de los códigos
- **Primer dígito:** Categoría general (2, 3, 4, 5)
- **Segundo y tercer dígito:** Código específico dentro de la categoría

---

## ✅ 2xx - Éxito (Successful)

<div style="width:100%; max-width:600px; overflow:hidden; margin:0 auto;">
   <img src="https://httpstatusdogs.com/img/200.jpg"
          alt="200 OK Dog"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

Estos códigos indican que la petición fue **procesada correctamente**.

| Código | Nombre | Significado | Cuando usarlo |
|--------|--------|-------------|---------------|
| **200** | **OK** | ✅ Todo bien, petición exitosa | GET exitoso, datos devueltos |
| **201** | **Created** | 🆕 Recurso creado exitosamente | POST que crea un nuevo elemento |
| **202** | **Accepted** | ⏳ Petición aceptada, procesamiento pendiente | Operaciones asíncronas |
| **204** | **No Content** | 📭 Éxito pero sin contenido | DELETE exitoso, PUT sin respuesta |

**Ejemplos en tu API:**
```python
# 200 OK - GET exitoso
@app.get("/usuarios")
async def obtener_usuarios():
    return {"usuarios": []}  # Devuelve lista (puede estar vacía)

# 201 Created - POST exitoso
@app.post("/usuarios")
async def crear_usuario(usuario: dict):
    # Crear usuario...
    return {"id": 1, "mensaje": "Usuario creado"}  # Status 201 automático

# 204 No Content - DELETE exitoso
@app.delete("/usuarios/{id}")
async def eliminar_usuario(id: int):
    # Eliminar usuario...
    return  # Sin contenido, status 204 automático
```

---

## 🔄 3xx - Redirección (Redirection)

<div style="width:100%; max-width:600px; overflow:hidden; margin:0 auto;">
   <img src="https://httpstatusdogs.com/img/301.jpg"
          alt="301 Moved Permanently Dog"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

Indican que el cliente debe **tomar acción adicional** para completar la petición.

| Código | Nombre | Significado | Ejemplo |
|--------|--------|-------------|---------|
| **301** | **Moved Permanently** | 📍 Recurso movido permanentemente | `/api/v1` → `/api/v2` |
| **302** | **Found** | 🔍 Recurso encontrado temporalmente | Redirecciones temporales |
| **304** | **Not Modified** | 📋 Sin cambios desde última petición | Caché del navegador |

**Nota:** En APIs REST rara vez se usan 3xx, son más comunes en navegadores web.

---

## ❌ 4xx - Error del Cliente (Client Error)

<div style="width:100%; max-width:600px; overflow:hidden; margin:0 auto;">
   <img src="https://httpstatusdogs.com/img/404.jpg"
          alt="404 Not Found Dog"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

Indican que hubo un **error en la petición del cliente**.

| Código | Nombre | Significado | Cuando usarlo |
|--------|--------|-------------|---------------|
| **400** | **Bad Request** | 🚫 Petición mal formada | JSON inválido, parámetros faltantes |
| **401** | **Unauthorized** | 🔐 No autorizado | Falta token de autenticación |
| **403** | **Forbidden** | 🚪 Prohibido | Usuario sin permisos |
| **404** | **Not Found** | 🔍 No encontrado | Recurso no existe |
| **405** | **Method Not Allowed** | 🚷 Método no permitido | POST en endpoint que solo acepta GET |
| **409** | **Conflict** | ⚡ Conflicto | Crear recurso que ya existe |
| **422** | **Unprocessable Entity** | 📝 Datos inválidos | Validación falla (FastAPI lo usa mucho) |
| **429** | **Too Many Requests** | 🕐 Demasiadas peticiones | Rate limiting |

**Ejemplos en FastAPI:**
```python
from fastapi import HTTPException

@app.get("/usuarios/{id}")
async def obtener_usuario(id: int):
    if id <= 0:
        raise HTTPException(status_code=400, detail="ID debe ser positivo")

    usuario = buscar_usuario(id)
    if not usuario:
        raise HTTPException(status_code=404, detail="Usuario no encontrado")

    return usuario

@app.post("/usuarios")
async def crear_usuario(usuario: Usuario):
    if usuario_existe(usuario.email):
        raise HTTPException(status_code=409, detail="Email ya registrado")

    # Crear usuario...
    return {"mensaje": "Usuario creado"}
```

---

## 💥 5xx - Error del Servidor (Server Error)

<div style="width:50%; max-width:600px; overflow:hidden; margin:0 auto;">
   <img src="https://httpstatusdogs.com/img/500.jpg"
          alt="500 Internal Server Error Dog"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

Indican que el **servidor falló** al procesar una petición válida.

| Código | Nombre | Significado | Causa común |
|--------|--------|-------------|-------------|
| **500** | **Internal Server Error** | 💥 Error interno del servidor | Excepción no manejada, bug en código |
| **501** | **Not Implemented** | 🚧 No implementado | Método HTTP no soportado |
| **502** | **Bad Gateway** | 🌉 Puerta de enlace mala | Problema con proxy/servidor intermedio |
| **503** | **Service Unavailable** | 🚫 Servicio no disponible | Servidor sobrecargado o en mantenimiento |
| **504** | **Gateway Timeout** | ⏰ Tiempo agotado | Servidor no responde a tiempo |

**Ejemplos comunes:**
```python
# 500 Internal Server Error - Error no manejado
@app.get("/usuarios")
async def obtener_usuarios():
    # Si hay un error en la base de datos...
    raise Exception("Error de conexión a BD")  # Genera 500

# 503 Service Unavailable - Mantenimiento
@app.get("/mantenimiento")
async def mantenimiento():
    raise HTTPException(
        status_code=503,
        detail="Servicio en mantenimiento, vuelve pronto"
    )
```

---

## 🎯 Guía práctica para elegir códigos de estado

### 📋 Checklist para elegir el código correcto:

**¿La petición fue procesada correctamente?**
- ✅ **Sí** → 2xx (200, 201, 204)
- ❌ **No** → Continúa...

**¿El error es culpa del cliente?**
- ✅ **Sí** → 4xx (400, 404, 422)
- ❌ **No** → 5xx (500, 503)

### 🔍 Códigos más comunes en APIs REST:

| Operación | Éxito | Error común |
|-----------|-------|-------------|
| **GET** (obtener) | 200 OK | 404 Not Found |
| **POST** (crear) | 201 Created | 400 Bad Request / 409 Conflict |
| **PUT** (actualizar) | 200 OK / 204 No Content | 404 Not Found / 400 Bad Request |
| **DELETE** (eliminar) | 204 No Content | 404 Not Found |

### 💡 Consejos importantes:
- **Sé específico:** Usa 404 en lugar de 400 cuando algo no existe
- **Consistente:** Mantén los mismos códigos en endpoints similares
- **Documenta:** Incluye códigos de estado en tu documentación API
- **FastAPI automático:** Muchos códigos se asignan automáticamente

---

## 🎓 Resumen de la clase

Hoy aprendimos:
- ✅ Reforzamos los conceptos básicos de Git con práctica real
- ✅ Introducción a Python como lenguaje backend
- ✅ Fundamentos de FastAPI para crear APIs
- ✅ ¿Qué es una API REST? Principios y arquitectura
- ✅ Operaciones CRUD: Create, Read, Update, Delete
- ✅ Métodos HTTP y diseño de endpoints REST
- ✅ Códigos de estado HTTP: 2xx, 4xx, 5xx con ejemplos

**¡Excelente trabajo! Los fundamentos de APIs REST y FastAPI están listos para la práctica 🚀**
