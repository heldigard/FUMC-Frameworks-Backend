# 🚀 Clase 1: Introducción al desarrollo web y control de versiones (Git)

<div style="width:100%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://www.suratica.es/wp-content/uploads/2020/10/que-es-el-backend-y-que-es-el-frontend-1.jpg"
          alt="Arquitectura Web"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

## 🎯 Objetivos de aprendizaje
- 🏗️ Entender la arquitectura básica de una aplicación web
- 🎨 Comprender la diferencia entre frontend y backend
- 🔌 Conocer qué son las APIs y los microservicios
- 📦 Aprender los fundamentos de Git para control de versiones
- 💻 Realizar tu primer repositorio y commits

---

## 🌐 Arquitectura web: Frontend vs Backend

<div style="width:100%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://media.licdn.com/dms/image/v2/C4D12AQE9wN-P0wx3yQ/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1597981500202?e=1763596800&v=beta&t=2SSdmEyDzLlP40W_ahsyAVlFoCtJTfAhwPz3SEAAlzU"
          alt="Frontend vs Backend"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

### 🎨 Frontend
- **¿Qué es?** La parte visual con la que interactúa el usuario
- **Tecnologías:** HTML, CSS, JavaScript, frameworks como Angular
- **Responsabilidad:** Interfaz de usuario, experiencia visual, interactividad

### ⚙️ Backend
- **¿Qué es?** La lógica, datos y procesamiento detrás del sistema
- **Tecnologías:** Python/FastAPI, Node.js, bases de datos
- **Responsabilidad:** Lógica de negocio, seguridad, gestión de datos

### 🔄 Comunicación
- Ambas partes se comunican a través de **APIs REST/HTTP**
- El frontend hace peticiones, el backend responde con datos

---

## 🔌 ¿Qué es una API?

<div style="width:100%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://media.geeksforgeeks.org/wp-content/uploads/20230216170349/What-is-an-API.png"
          alt="API Diagram"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

**API** = Application Programming Interface (Interfaz de Programación de Aplicaciones)

- Es el **puente de comunicación** entre diferentes aplicaciones
- Permite que el frontend solicite datos o acciones al backend
- Define las "reglas del juego" para la comunicación

### 🎭 Ejemplos prácticos con APIs divertidas

**🧙‍♂️ API de Harry Potter:**
```bash
GET https://hp-api.onrender.com/api/characters
```
Devuelve todos los personajes del mundo mágico.

**⭐ API de Star Wars:**
```bash
GET https://swapi.dev/api/people/1/
```
Devuelve información de Luke Skywalker.

**🔬 API de Rick and Morty:**
```bash
GET https://rickandmortyapi.com/api/character/1
```
Devuelve información de Rick Sanchez.

### 💡 ¿Por qué son importantes?
- ✅ Permiten la **separación de responsabilidades**
- ✅ Facilitan la **integración** entre sistemas
- ✅ Posibilitan que múltiples clientes (web, móvil, etc.) usen el mismo backend

---

## 🏗️ Arquitectura de Microservicios

<div style="width:100%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://blog.feedback-it.com/wp-content/uploads/2020/10/Microservicios-vs-monolitico-1-1024x495.png"
          alt="Microservicios"
          style="width:100%; height:100%; object-fit:cover; object-position:center;">
</div>

### 🤔 ¿Qué son los microservicios?
Arquitectura que divide una aplicación en **componentes independientes** (servicios pequeños), cada uno con una responsabilidad específica.

### 🎯 Ventajas
- 📈 **Escalabilidad:** Puedes escalar solo los servicios que lo necesiten
- 🔧 **Mantenimiento:** Más fácil actualizar partes específicas sin afectar todo el sistema
- 🎯 **Simplicidad:** Cada servicio es más pequeño y manejable
- 🛠️ **Tecnología flexible:** Cada microservicio puede usar diferentes tecnologías

### 📋 Ejemplo
En lugar de una aplicación monolítica, tendrías:
- 🔐 Servicio de **autenticación**
- 💳 Servicio de **pagos**
- 📦 Servicio de **productos**
- 📢 Servicio de **notificaciones**

---

## 📦 Introducción a Git

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://1000logos.net/wp-content/uploads/2018/11/GitHub-logo.jpg"
          alt="Git Logo"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

### 🤔 ¿Qué es Git?
- Sistema de **control de versiones distribuido**
- Permite **registrar cambios** en el código a lo largo del tiempo
- Facilita la **colaboración** entre desarrolladores
- Posibilita **restaurar versiones anteriores** del código

### 💡 ¿Por qué usarlo?
- 📚 Historial completo de cambios
- 👥 Trabajo en equipo sin conflictos
- 💾 Respaldo automático del código
- 🧪 Experimentación segura (ramas)

---

## 🔧 Comandos básicos de Git

### ⚙️ Configuración inicial
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

### 📋 Comandos esenciales
| Comando | Descripción | Emoji |
|---------|-------------|--------|
| `git init` | Inicia un nuevo repositorio Git | 🆕 |
| `git status` | Verifica el estado actual del repositorio | 📊 |
| `git add <archivo>` | Prepara cambios para el commit | ➕ |
| `git add .` | Prepara todos los cambios | 📁 |
| `git commit -m "mensaje"` | Guarda los cambios con un mensaje descriptivo | 💾 |
| `git push` | Sube los cambios al repositorio remoto | ☁️ |
| `git pull` | Descarga cambios del repositorio remoto | 📥 |
| `git log` | Muestra el historial de commits | 📜 |
| `git log --oneline` | Historial resumido | 📝 |

### 🔄 Flujo básico de trabajo
```bash
# 1. 📝 Modificas archivos
# 2. 👀 Verificas qué cambió
git status

# 3. ➕ Agregas los cambios
git add .

# 4. 💾 Haces commit
git commit -m "Descripción de los cambios"

# 5. ☁️ Subes al repositorio
git push
```

---

## ⚡ Comandos avanzados de Git

### Para usuarios más experimentados
| Comando | Descripción | ⚠️ Precaución |
|---------|-------------|---------------|
| `git reflog` | Muestra historial completo de movimientos en HEAD | - |
| `git rebase` | Reescribe la base de una rama para mantener historial limpio | Puede reescribir historia |
| `git cherry-pick <hash>` | Copia un commit específico a tu rama actual | - |
| `git reset --hard <hash>` | Vuelve a un commit específico (descarta cambios) | ⚠️ Pierdes cambios |
| `git push --force` | Sobreescribe el repositorio remoto con tu versión local | ⚠️ Muy peligroso |
| `git stash` | Guarda cambios temporalmente sin hacer commit | - |
| `git stash pop` | Recupera los cambios guardados | - |

> **Nota:** Los comandos marcados con ⚠️ deben usarse con extremo cuidado

---

## 💻 Actividad práctica

<div style="width:50%; max-width:800px; overflow:hidden; margin:0 auto;">
   <img src="https://enciclopedia.net/wp-content/uploads/2014/06/practicaprofesional-380x380.jpg"
          alt="Practice Time"
          style="width:50%; height:50%; object-fit:cover; object-position:center;">
</div>

### 🎯 Parte 1: Configuración inicial (15 min)
1. **📝 Crea tu cuenta en GitHub** → [github.com](https://github.com/)
2. **🛠️ Herramientas para probar APIs:**
   - **ApiDog** (interfaz web ligera y práctica) — recomendado para las primeras prácticas
   - **Postman** (opcional, si se instala en las aulas) — útil para flujos avanzados y colecciones
3. **⚙️ Configura Git** con tu nombre y email

### 🚀 Parte 2: Tu primer repositorio (20 min)
1. **🆕 Crea un nuevo repositorio** en GitHub llamado `curso-backend-fumc`
2. **📥 Clona el repositorio** o crea uno local con `git init`
3. **📄 Crea un archivo `README.md`** con:
   - Tu nombre
   - Una breve descripción sobre ti
   - Tus expectativas del curso
4. **💾 Realiza tu primer commit:**
   ```bash
   git add README.md
   git commit -m "Primer commit: Información personal"
   git push
   ```

### 🔍 Parte 3: Explorando el historial (10 min)
1. **✏️ Realiza 3 cambios adicionales** al README.md (agrega hobbies, tecnologías que conoces, etc.)
2. **💾 Haz un commit por cada cambio**
3. **📜 Explora el historial** con:
   ```bash
   git log
   git log --oneline
   git reflog
   ```
4. **🌐 Verifica tus cambios en GitHub**

---

## 🚀 Mini-proyecto de cierre

### Entregable de hoy
Crea un archivo `README.md` profesional en tu repositorio que incluya:

✅ **Información personal:**
- Nombre completo
- Programa: Técnico Laboral como Auxiliar en Análisis y Gestión de Datos
- Módulo: Frameworks para desarrollo web - Backend

✅ **Sección "Sobre mí":**
- Breve descripción personal
- Intereses en tecnología

✅ **Objetivos del curso:**
- ¿Qué esperas aprender?
- ¿Qué te gustaría construir?

### Formato sugerido
```markdown
# Mi nombre - Curso Backend FUMC

## 👨‍💻 Sobre mí
[Tu descripción aquí]

## 🎯 Objetivos del curso
- [ ] Aprender FastAPI/Node.js
- [ ] Crear mi primera API
- [ ] ...

## 🛠️ Tecnologías de interés
- Python
- JavaScript
- ...
```

**Fecha de entrega:** Próxima clase
**Método:** Link a tu repositorio de GitHub

---

## 📚 Para la próxima clase

### Preparación técnica
- [ ] **Familiarízate** con herramientas para probar APIs: **ApiDog** (web) y **Postman** (si está disponible en las aulas)
- [ ] **Asegúrate** de tener tu repositorio de GitHub listo y accesible
- [ ] **Verifica** si en las aulas pueden instalar **VS Code** o una versión portable de VS Code para prácticas locales

### Investigación previa
- [ ] Lee sobre qué es una **API REST**
- [ ] Busca ejemplos de APIs públicas (pueden ser muy simples)
- [ ] Investiga qué significa **endpoint** en el contexto de APIs

### Recursos recomendados
- 📖 [¿Qué es una API REST?](https://www.redhat.com/es/topics/api/what-is-a-rest-api)
- 🎥 YouTube: "API REST explicada en 10 minutos"
- 🔧 Prueba APIs públicas en ApiDog o Postman: `https://api.github.com/users/github`
- 🧰 VS Code (recomendado para la práctica en clase) — considerar instalación o versión portable según disponibilidad en los equipos

---

## 📝 Notas importantes

- **Repositorio del curso:** Todo el material estará disponible en el repositorio de GitHub de la clase
- **Próximo tema:** Construcción de tu primera API REST con FastAPI

---

## 🎓 Resumen de la clase

Hoy aprendimos:
- ✅ La diferencia entre Frontend y Backend
- ✅ Qué son las APIs y por qué son importantes
- ✅ Arquitectura de microservicios
- ✅ Fundamentos de Git y control de versiones
- ✅ Comandos básicos y avanzados de Git
- ✅ Cómo crear y gestionar un repositorio

**¡Buen trabajo! Nos vemos en la próxima clase 🚀**
