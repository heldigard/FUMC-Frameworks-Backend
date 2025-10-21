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
   
   **En Windows (CMD):**
   ```cmd
   venv\Scripts\activate.bat
   ```

   **✅ Verificación:** Deberías ver `(venv)` al inicio de la línea en tu terminal.

#### Paso 1.3: Instalar dependencias
5. **📦 Instala FastAPI y todas sus dependencias** (con el entorno virtual activado):
   ```bash
   pip install "fastapi[all]"
   ```
   
   *Nota: `"fastapi[all]"` instala FastAPI junto con `uvicorn`, `pydantic` y otras dependencias necesarias para el curso.*

   **✅ Verificación:** Deberías ver mensajes de instalación exitosa.

#### Paso 1.4: Crear archivo .gitignore
6. **🚫 Crea un archivo `.gitignore`** para excluir librerías y archivos compilados:
   - En el explorador de archivos de VS Code, right-click en la raíz del repositorio → `New File`
   - Nómbralo `.gitignore`
   - Copia y pega el siguiente contenido:
   ```gitignore
   # Byte-compiled / optimized / DLL files
   __pycache__/
   *.py[cod]
   *$py.class
   
   # C extensions
   *.so
   
   # Distribution / packaging
   .Python
   build/
   develop-eggs/
   dist/
   downloads/
   eggs/
   .eggs/
   lib/
   lib64/
   parts/
   sdist/
   var/
   wheels/
   *.egg-info/
   .installed.cfg
   *.egg
   MANIFEST
   
   # Environments
   .env
   .venv
   env/
   venv/
   ENV/
   env.bak/
   venv.bak/
   
   # IDE
   .vscode/
   .idea/
   *.swp
   *.swo
   *~
   
   # OS
   .DS_Store
   Thumbs.db
   ```

   **✅ Verificación:** El archivo `.gitignore` debe aparecer en la raíz de tu repositorio.

---

### � Parte 2: Tu primera API básica (15 min)



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
   ```bash
   python -m uvicorn main:app --reload
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
