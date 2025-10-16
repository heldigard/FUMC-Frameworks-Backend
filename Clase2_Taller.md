# 🛠️ Taller Evaluativo: Creando tu Primera API con FastAPI

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://fastapi.tiangolo.com/img/logo-margin/logo-teal.png"
          alt="FastAPI Logo"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

## 🎯 Objetivos del Taller
- ✅ Crear y ejecutar una API REST funcional con FastAPI
- ✅ Implementar operaciones CRUD básicas (Create, Read, Update, Delete)
- ✅ Aprender a manejar datos con modelos de Pydantic
- ✅ Probar la API usando APIdog (cliente web)
- ✅ Explorar la documentación automática generada por FastAPI
- ✅ Subir el código a GitHub con commits descriptivos

---

## 💻 Actividad práctica: Tu primera API

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://cdn-icons-png.flaticon.com/512/4712/4712035.png"
          alt="Practice Time"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

### 🎯 Parte 1: Configuración del entorno (10 min)

#### Paso 1.1: Preparación inicial
1. **🐍 Verifica Python instalado:**
   - Abre VS Code
   - Abre una terminal: `Terminal → New Terminal` (o `Ctrl + ñ`)
   - Ejecuta:
   ```bash
   python --version
   ```
   - Deberías ver algo como `Python 3.8.x` o superior
   - Si no tienes Python, descárgalo desde [python.org](https://www.python.org/downloads/)

2. **💻 Abre tu repositorio en VS Code:**
   - `File → Open Folder`
   - Selecciona tu repositorio clonado (ejemplo: `FUMC-Frameworks-Backend`)

#### Paso 1.2: Crear entorno virtual
3. **🔧 Crea un entorno virtual** (en la terminal de VS Code):
   ```bash
   # Asegúrate de estar en la raíz de tu repositorio
   python -m venv venv
   ```

4. **⚡ Activa el entorno virtual:**
   
   **En Windows (PowerShell):**
   ```powershell
   .\venv\Scripts\Activate.ps1
   ```
   
   **En Windows (CMD):**
   ```cmd
   venv\Scripts\activate.bat
   ```
   
   **En Linux/macOS:**
   ```bash
   source venv/bin/activate
   ```

   **✅ Verificación:** Deberías ver `(venv)` al inicio de la línea en tu terminal.

#### Paso 1.3: Instalar dependencias
5. **📦 Instala FastAPI y todas sus dependencias** (con el entorno virtual activado):
   ```bash
   pip install "fastapi[all]"
   ```
   
   *Nota: `"fastapi[all]"` instala FastAPI junto con `uvicorn`, `pydantic` y otras dependencias necesarias para el curso.*

   **✅ Verificación:** Deberías ver mensajes de instalación exitosa.

---

### � Parte 2: Tu primera API básica (15 min)

#### Paso 2.1: Crear estructura del proyecto
1. **📁 Crea la carpeta del proyecto** (en terminal de VS Code, desde la raíz del repositorio):
   ```bash
   mkdir clase2-api-tareas
   cd clase2-api-tareas
   ```

2. **📄 Crea el archivo `main.py`** usando VS Code:
   - En el explorador de archivos de VS Code, busca la carpeta `clase2-api-tareas`
   - Right-click en la carpeta → `New File`
   - Nómbralo `main.py`

#### Paso 2.2: Código inicial - Endpoints básicos
3. **✍️ Escribe el código inicial** en `main.py`:

```python
from fastapi import FastAPI

# Crear la aplicación FastAPI
app = FastAPI(
    title="API de Tareas - Clase 2",
    description="API REST con operaciones CRUD creada en el curso Backend FUMC",
    version="1.0.0"
)

# Ruta raíz - Endpoint de bienvenida
@app.get("/")
async def root():
    return {
        "mensaje": "¡Bienvenido a la API de Tareas!",
        "version": "1.0.0",
        "endpoints": ["/docs", "/tareas"]
    }

# Endpoint de prueba con parámetro
@app.get("/saludar/{nombre}")
async def saludar(nombre: str):
    return {"mensaje": f"¡Hola, {nombre}! Esta API gestiona tareas."}
```

#### Paso 2.3: Ejecutar y probar
4. **🚀 Ejecuta la API** (asegúrate de estar en la carpeta `clase2-api-tareas`):
   ```bash
   uvicorn main:app --reload
   ```
   
   **¿Qué hace este comando?**
   - `main`: Nombre del archivo (sin `.py`)
   - `app`: Nombre de la instancia de FastAPI
   - `--reload`: Reinicia automáticamente cuando cambias el código

5. **🌐 Prueba en el navegador:**
   - **http://127.0.0.1:8000/** → Mensaje de bienvenida
   - **http://127.0.0.1:8000/saludar/TuNombre** → Saludo personalizado
   - **http://127.0.0.1:8000/docs** → Documentación interactiva (Swagger UI)
   - **http://127.0.0.1:8000/redoc** → Documentación alternativa (ReDoc)

**✅ Verificación:** Si ves la documentación en `/docs`, ¡tu API está funcionando!

---

### 🎯 Parte 3: Introducción a APIdog (10 min)

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://assets.apidog.com/blog/2024/09/image-188.png"
          alt="APIdog Logo"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

### 🎯 ¿Qué es APIdog?
APIdog es una **plataforma web completa** para desarrollo y testing de APIs. Su cliente web te permite probar APIs directamente desde el navegador sin necesidad de instalar software - ¡perfecto para aulas!

### 🌐 Ventajas del cliente web de APIdog
- **🆓 Gratuito** - No requiere instalación
- **🌍 Accesible desde cualquier navegador**
- **🎨 Interfaz intuitiva** - Similar a Postman pero más moderna
- **📊 Historial de requests** - Guarda tus pruebas
- **🔄 Entornos** - Configura diferentes ambientes (desarrollo, producción)
- **📋 Colecciones** - Organiza tus requests por proyecto

### 🚀 Cómo usar APIdog para probar tu API

#### Paso 1: Accede a APIdog
1. **Ve al sitio web:** https://www.apidog.com/
2. **Regístrate gratis** (o inicia sesión si ya tienes cuenta)
3. **Accede al cliente web:** Una vez dentro, verás la interfaz de testing

#### Paso 2: Crea un nuevo request
1. **Haz clic en "New Request"**
2. **Configura el método HTTP:**
   - GET (para obtener datos)
   - POST (para enviar datos)
   - PUT (para actualizar)
   - DELETE (para eliminar)

#### Paso 3: Prueba tus endpoints
Para probar tu API local (http://127.0.0.1:8000), configura:

**Endpoint raíz:**
- **Method:** GET
- **URL:** http://127.0.0.1:8000/
- **Haz clic en "Send"**

**Endpoint con parámetro:**
- **Method:** GET
- **URL:** http://127.0.0.1:8000/saludar/TuNombre
- **Haz clic en "Send"**

**Endpoint con query parameters:**
- **Method:** GET
- **URL:** http://127.0.0.1:8000/info
- **Query Params:**
  - edad: 25
  - ciudad: Lima
- **Haz clic en "Send"**

#### Paso 4: Organiza tus pruebas
1. **Crea una colección:** "Mi API FastAPI - Clase 2"
2. **Guarda cada request** en la colección
3. **Agrega descripciones** a cada request

### 💡 Consejos para usar APIdog
- **Verifica el status code:** 200 = éxito, 404 = no encontrado, 500 = error del servidor
- **Revisa la respuesta:** JSON formateado automáticamente
- **Headers:** APIdog agrega automáticamente headers necesarios
- **Historial:** Tus requests se guardan automáticamente

### 🔍 Comparación con otros clientes
| Herramienta | Instalación | Interfaz | Costo |
|-------------|-------------|----------|--------|
| **APIdog Web** | ❌ No requiere | 🌐 Web moderna | 🆓 Gratuito |
| Postman | ✅ Requiere instalación | 🖥️ Desktop | 🆓 Básico, pago avanzado |
| Insomnia | ✅ Requiere instalación | 🖥️ Desktop | 🆓 Básico, pago avanzado |

**APIdog es ideal para aulas** porque no requiere instalación y funciona desde cualquier navegador.

#### Paso 3.1: Prueba tus endpoints básicos
Ahora que conoces APIdog, prueba los endpoints que creaste:

1. **Endpoint raíz (GET):**
   - Method: `GET`
   - URL: `http://127.0.0.1:8000/`
   - Click en **Send** → Deberías ver el mensaje de bienvenida

2. **Endpoint de saludo (GET):**
   - Method: `GET`
   - URL: `http://127.0.0.1:8000/saludar/TuNombre`
   - Click en **Send** → Deberías ver el saludo personalizado

3. **Guarda estos requests** en una colección llamada "API Tareas - Clase 2"

---

### 🎯 Parte 4: Implementando operaciones CRUD (30 min)

#### ¿Qué son las operaciones CRUD?
Ahora vamos a implementar las **4 operaciones básicas** para gestionar tareas:
- **C**reate (Crear) → `POST`
- **R**ead (Leer) → `GET`
- **U**pdate (Actualizar) → `PUT`
- **D**elete (Eliminar) → `DELETE`

#### Paso 4.1: Entendiendo Pydantic
Pydantic es una librería para **validación de datos** que ya viene incluida con `fastapi[all]`. Nos permite definir modelos (schemas) que especifican:
- Qué campos debe tener una tarea
- Qué tipo de dato es cada campo
- Qué campos son obligatorios u opcionales

#### Paso 4.2: Actualizar el código con CRUD completo

1. **⏹️ Detén el servidor** (si está corriendo):
   - En la terminal donde corre uvicorn, presiona `Ctrl + C`

2. **✍️ Reemplaza TODO el contenido** de `main.py` con el siguiente código:

```python
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel
from typing import List

# Crear la aplicación FastAPI
app = FastAPI(
    title="API de Tareas - Clase 2",
    description="API REST con operaciones CRUD creada en el curso Backend FUMC",
    version="1.0.0"
)

# --- MODELO DE PYDANTIC ---
# Define la estructura de una tarea
class Tarea(BaseModel):
    id: int
    titulo: str
    descripcion: str
    completada: bool = False  # Valor por defecto: False

# --- BASE DE DATOS EN MEMORIA ---
# Lista que simula una base de datos (se reinicia al cerrar el servidor)
# Incluimos algunas tareas de ejemplo para que vean datos desde el inicio
db_tareas: List[Tarea] = [
    Tarea(id=1, titulo="Aprender FastAPI", descripcion="Completar el taller de la Clase 2", completada=False),
    Tarea(id=2, titulo="Practicar CRUD", descripcion="Implementar Create, Read, Update y Delete", completada=False),
    Tarea(id=3, titulo="Subir a GitHub", descripcion="Hacer commit y push del proyecto", completada=False)
]

# --- ENDPOINTS ---

# Endpoint raíz - Información de la API
@app.get("/")
async def root():
    return {
        "mensaje": "API de Tareas con CRUD completo",
        "total_tareas": len(db_tareas),
        "endpoints_disponibles": {
            "documentacion": "/docs",
            "crear_tarea": "POST /tareas/",
            "listar_tareas": "GET /tareas/",
            "obtener_tarea": "GET /tareas/{id}",
            "actualizar_tarea": "PUT /tareas/{id}",
            "eliminar_tarea": "DELETE /tareas/{id}"
        }
    }

# CREATE - Crear una nueva tarea
@app.post("/tareas/", response_model=Tarea, status_code=201)
async def crear_tarea(tarea: Tarea):
    """
    Crea una nueva tarea.
    
    - **id**: ID único de la tarea (debe ser único)
    - **titulo**: Título de la tarea
    - **descripcion**: Descripción detallada
    - **completada**: Estado (opcional, por defecto False)
    """
    # Verificar que el ID no exista
    if any(t.id == tarea.id for t in db_tareas):
        raise HTTPException(
            status_code=400, 
            detail=f"Ya existe una tarea con el ID {tarea.id}"
        )
    
    db_tareas.append(tarea)
    return tarea

# READ - Obtener todas las tareas
@app.get("/tareas/", response_model=List[Tarea])
async def obtener_tareas():
    """
    Obtiene la lista completa de tareas.
    """
    return db_tareas

# READ - Obtener una tarea específica por ID
@app.get("/tareas/{tarea_id}", response_model=Tarea)
async def obtener_tarea(tarea_id: int):
    """
    Obtiene una tarea específica por su ID.
    
    - **tarea_id**: ID de la tarea a buscar
    """
    tarea = next((t for t in db_tareas if t.id == tarea_id), None)
    
    if tarea is None:
        raise HTTPException(
            status_code=404, 
            detail=f"No se encontró la tarea con ID {tarea_id}"
        )
    
    return tarea

# UPDATE - Actualizar una tarea existente
@app.put("/tareas/{tarea_id}", response_model=Tarea)
async def actualizar_tarea(tarea_id: int, tarea_actualizada: Tarea):
    """
    Actualiza una tarea existente.
    
    - **tarea_id**: ID de la tarea a actualizar
    - El cuerpo debe incluir todos los campos de la tarea
    """
    # Buscar el índice de la tarea
    tarea_index = next(
        (i for i, t in enumerate(db_tareas) if t.id == tarea_id), 
        None
    )
    
    if tarea_index is None:
        raise HTTPException(
            status_code=404, 
            detail=f"No se encontró la tarea con ID {tarea_id}"
        )
    
    # Actualizar la tarea
    db_tareas[tarea_index] = tarea_actualizada
    return tarea_actualizada

# DELETE - Eliminar una tarea
@app.delete("/tareas/{tarea_id}")
async def eliminar_tarea(tarea_id: int):
    """
    Elimina una tarea por su ID.
    
    - **tarea_id**: ID de la tarea a eliminar
    """
    tarea = next((t for t in db_tareas if t.id == tarea_id), None)
    
    if tarea is None:
        raise HTTPException(
            status_code=404, 
            detail=f"No se encontró la tarea con ID {tarea_id}"
        )
    
    db_tareas.remove(tarea)
    return {
        "mensaje": "Tarea eliminada exitosamente",
        "tarea_eliminada": {
            "id": tarea.id,
            "titulo": tarea.titulo
        }
    }
```

3. **🚀 Ejecuta la API nuevamente:**
   ```bash
   uvicorn main:app --reload
   ```

4. **📖 Explora la documentación interactiva:**
   - Abre: **http://127.0.0.1:8000/docs**
   - Verás los 5 endpoints CRUD con su documentación automática
   - Puedes probar cada endpoint desde aquí

**✅ Verificación:** Deberías ver 6 endpoints en total en la documentación Swagger.


---

### 🎯 Parte 5: Probando operaciones CRUD con APIdog (20 min)

Ahora vamos a probar **todos los endpoints CRUD** usando APIdog paso a paso:

#### Paso 5.1: Crear tareas (POST)
- **Method:** POST
- **URL:** `http://127.0.0.1:8000/tareas/`
- **Body** (JSON):
  ```json
  {
    "id": 1,
    "titulo": "Aprender FastAPI",
    "descripcion": "Completar el taller de la Clase 2",
    "completada": false
  }
  ```
- Haz clic en **Send**. Deberías ver la tarea que creaste como respuesta.

#### Paso 5.1: Crear tareas (POST)

**1. Primera tarea:**
- **Method:** `POST`
- **URL:** `http://127.0.0.1:8000/tareas/`
- **Headers:** (APIdog los agrega automáticamente)
  - `Content-Type: application/json`
- **Body** → Selecciona `JSON` y escribe:
  ```json
  {
    "id": 1,
    "titulo": "Aprender FastAPI",
    "descripcion": "Completar el taller de la Clase 2",
    "completada": false
  }
  ```
- **Click en Send**
- **✅ Resultado esperado:** Status `201 Created` y la tarea creada en la respuesta

**2. Segunda tarea:**
- Mismos pasos, pero con este JSON:
  ```json
  {
    "id": 2,
    "titulo": "Practicar CRUD",
    "descripcion": "Implementar Create, Read, Update y Delete",
    "completada": false
  }
  ```

**3. Tercera tarea:**
  ```json
  {
    "id": 3,
    "titulo": "Subir a GitHub",
    "descripcion": "Hacer commit y push del proyecto",
    "completada": false
  }
  ```

**💡 Consejo:** Guarda estos 3 requests en tu colección "API Tareas - Clase 2"

#### Paso 5.2: Obtener todas las tareas (GET)

- **Method:** `GET`
- **URL:** `http://127.0.0.1:8000/tareas/`
- **Click en Send**
- **✅ Resultado esperado:** Status `200 OK` y un array con las 3 tareas que creaste

#### Paso 5.3: Obtener una tarea específica (GET)

- **Method:** `GET`
- **URL:** `http://127.0.0.1:8000/tareas/1`
- **Click en Send**
- **✅ Resultado esperado:** Status `200 OK` y solo la tarea con ID 1

**Prueba también:**
- `GET /tareas/2` → Debería devolver la tarea 2
- `GET /tareas/999` → Debería devolver `404 Not Found` (tarea no existe)

#### Paso 5.4: Actualizar una tarea (PUT)

Vamos a marcar la primera tarea como completada:

- **Method:** `PUT`
- **URL:** `http://127.0.0.1:8000/tareas/1`
- **Body** (JSON):
  ```json
  {
    "id": 1,
    "titulo": "Aprender FastAPI",
    "descripcion": "Completar el taller de la Clase 2",
    "completada": true
  }
  ```
- **Click en Send**
- **✅ Resultado esperado:** Status `200 OK` y la tarea actualizada con `completada: true`

**Verificación:** Haz un `GET /tareas/1` para confirmar que el cambio se guardó.

#### Paso 5.5: Eliminar una tarea (DELETE)

- **Method:** `DELETE`
- **URL:** `http://127.0.0.1:8000/tareas/3`
- **Click en Send**
- **✅ Resultado esperado:** Status `200 OK` y mensaje de confirmación

**Verificación:** 
- Haz un `GET /tareas/` → Ahora solo deberías ver 2 tareas (eliminaste la #3)
- Intenta `DELETE /tareas/999` → Debería devolver `404 Not Found`

#### Paso 5.6: Organiza tus pruebas en APIdog

1. **Guarda todos los requests** en tu colección
2. **Agrégales descripciones** para recordar qué hace cada uno
3. **Agrupa por operación:** CREATE, READ, UPDATE, DELETE

**✅ Al terminar esta parte, deberías tener:**
- ✅ API funcionando con 6 endpoints
- ✅ Colección en APIdog con todas las pruebas
- ✅ Entendimiento claro de cada operación CRUD

---

### 🎯 Parte 6: Subir tu trabajo a Git (10 min)

#### Paso 6.1: Preparar el commit

1. **⏹️ Detén el servidor** (Ctrl + C en la terminal donde corre uvicorn)

2. **📊 Verifica el estado de Git:**
   ```bash
   # Asegúrate de estar en la raíz del repositorio
   cd ..  # Si estás dentro de clase2-api-tareas
   git status
   ```

3. **➕ Agrega la carpeta del proyecto:**
   ```bash
   git add clase2-api-tareas/
   ```

4. **📝 Verifica qué se agregará:**
   ```bash
   git status
   ```
   Deberías ver: `new file: clase2-api-tareas/main.py`

#### Paso 6.2: Crear commit descriptivo

5. **💾 Crea el commit:**
   ```bash
   git commit -m "Clase 2: Implementa API de tareas con CRUD completo usando FastAPI"
   ```

6. **📜 Verifica el historial:**
   ```bash
   git log --oneline -3
   ```

#### Paso 6.3: Subir a GitHub

7. **☁️ Sube los cambios:**
   ```bash
   git push origin main
   ```

8. **✅ Verificación en GitHub:**
   - Ve a tu repositorio en GitHub
   - Verifica que aparezca la carpeta `clase2-api-tareas`
   - Revisa que el commit tenga el mensaje correcto

**💡 Buenas prácticas de commits:**
- Mensajes descriptivos y claros
- Un commit por funcionalidad completada
- Commits frecuentes (no esperar al final)

---

### 🎯 Mini-proyecto de cierre: Entregable evaluativo

## 🚀 Tu API de Tareas está lista - ¿Qué entregar?

### ✅ Checklist del entregable

Verifica que tu proyecto tenga **todo esto**:

**1. Código funcional:**
- ✅ Carpeta `clase2-api-tareas` en tu repositorio
- ✅ Archivo `main.py` con el código completo
- ✅ 5 endpoints CRUD implementados:
  - `POST /tareas/` - Crear tarea
  - `GET /tareas/` - Listar todas las tareas
  - `GET /tareas/{id}` - Obtener una tarea específica
  - `PUT /tareas/{id}` - Actualizar tarea
  - `DELETE /tareas/{id}` - Eliminar tarea
- ✅ Endpoint raíz `/` con información de la API

**2. Validación con Pydantic:**
- ✅ Modelo `Tarea` con campos: `id`, `titulo`, `descripcion`, `completada`
- ✅ Validación automática de tipos de datos

**3. Manejo de errores:**
- ✅ Códigos de estado HTTP correctos (200, 201, 404, 400)
- ✅ Mensajes de error descriptivos con `HTTPException`

**4. Documentación:**
- ✅ Documentación automática funcionando en `/docs`
- ✅ Todos los endpoints visibles y probables desde Swagger

**5. Control de versiones:**
- ✅ Código subido a GitHub
- ✅ Commit con mensaje descriptivo
- ✅ Push exitoso a la rama `main`

**6. Pruebas con APIdog:**
- ✅ Colección en APIdog con todos los requests
- ✅ Pruebas exitosas de cada operación CRUD

### 📤 Método de entrega

**Qué entregar:**
- Link a tu repositorio de GitHub

**Cómo entregar:**
1. Copia la URL de tu repositorio (ejemplo: `https://github.com/TuUsuario/FUMC-Frameworks-Backend`)
2. Verifica que el repositorio sea **público** o agregues al docente como colaborador
3. Comparte el link según las instrucciones del docente

**Fecha límite:** Fin de la clase

### 🎖️ Criterios de evaluación

| Criterio | Puntos | Descripción |
|----------|--------|-------------|
| **Código funcional** | 40% | API ejecuta sin errores, endpoints responden correctamente |
| **CRUD completo** | 30% | Las 5 operaciones implementadas y funcionando |
| **Validación** | 15% | Uso correcto de Pydantic y manejo de errores |
| **Git & GitHub** | 10% | Commits descriptivos, código en repositorio |
| **Documentación** | 5% | Swagger UI funcional y completo |

### 🌟 Puntos extras (opcional)

Impresiona al docente agregando:
- ✨ Endpoint adicional (por ejemplo: `GET /tareas/completadas` que filtre tareas completadas)
- ✨ Comentarios en el código explicando la lógica
- ✨ README.md en la carpeta del proyecto con instrucciones de uso
- ✨ Validaciones adicionales (por ejemplo: título no puede estar vacío)

---


## 🎓 Resumen del taller

### Lo que lograste hoy:
- ✅ Configuraste un entorno virtual de Python
- ✅ Instalaste FastAPI y sus dependencias
- ✅ Creaste tu primera API REST funcional
- ✅ Implementaste las 5 operaciones CRUD completas
- ✅ Aprendiste a usar modelos de Pydantic para validación
- ✅ Probaste tu API con APIdog (cliente web)
- ✅ Exploraste la documentación automática con Swagger UI
- ✅ Subiste tu código a GitHub con commits descriptivos
- ✅ Entendiste los códigos de estado HTTP (200, 201, 404, 400)

### Conceptos clave aprendidos:
- 🔑 **CRUD**: Create, Read, Update, Delete
- 🔑 **REST**: Arquitectura para APIs web
- 🔑 **Pydantic**: Validación de datos con modelos
- 🔑 **FastAPI**: Framework moderno para APIs en Python
- 🔑 **HTTP Methods**: GET, POST, PUT, DELETE
- 🔑 **Status Codes**: Significado de 200, 201, 404, 400
- 🔑 **JSON**: Formato de intercambio de datos
- 🔑 **Swagger/OpenAPI**: Documentación automática de APIs

**¡Excelente trabajo! Tu primera API REST con operaciones CRUD está lista 🚀**

---

## 📚 Para la próxima clase

Si intentas obtener las tareas de nuevo, la lista estará vacía.

### Preparación técnica
- [ ] **Asegúrate** de tener Python y FastAPI instalados
- [ ] **Instala y configura VS Code** (o versión portable)
- [ ] **Crea una cuenta gratuita en APIdog** para probar APIs
- [ ] **Prueba** tu API localmente antes de la clase
- [ ] **Familiarízate** con la documentación de FastAPI: https://fastapi.tiangolo.com/

### Investigación previa
- [ ] Lee sobre **endpoints REST** (GET, POST, PUT, DELETE)
- [ ] Investiga qué es **JSON** y por qué se usa en APIs
- [ ] Busca ejemplos de **códigos de estado HTTP** (200, 404, 500, etc.)
- [ ] Busca ejemplos de APIs reales (GitHub API, JSONPlaceholder)

### Recursos recomendados
- 📖 [Documentación oficial de FastAPI](https://fastapi.tiangolo.com/)
- 🎥 YouTube: "FastAPI en 15 minutos"
- 🔧 [JSONPlaceholder](https://jsonplaceholder.typicode.com/) - API de prueba gratuita
- 🐍 [Python.org](https://python.org) - Descarga e instalación
- 💻 [VS Code](https://code.visualstudio.com/) - Editor recomendado para el curso
- 🐕 [APIdog](https://www.apidog.com/) - Cliente web para probar APIs

---

## 📝 Notas importantes

- **Repositorio del curso:** Todo el material estará disponible en el repositorio de GitHub de la clase
- **Próximo tema:** Endpoints avanzados, validación de datos y bases de datos con FastAPI

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
- ✅ Cómo crear, ejecutar y probar una API REST
- ✅ Documentación automática con Swagger/ReDoc
- ✅ Integración de Git con desarrollo de APIs
- ✅ Uso de APIdog para probar APIs desde el navegador

**¡Excelente trabajo! Tu primera API REST con operaciones CRUD y códigos de estado está lista 🚀**
