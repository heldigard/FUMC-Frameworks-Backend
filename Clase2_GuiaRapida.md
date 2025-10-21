# 📋 Guía Rápida - Clase 2: Primera API con FastAPI

> **Resumen ejecutivo para el docente:** Flujo completo de la clase y tiempos estimados

---

## ⏱️ Cronograma de la clase (2-3 horas)

### Teoría: Clase2.md (60-75 min)
1. **Reforzamiento de Git** (20 min)
   - Práctica con git-practice.md
   - Verificar que todos puedan hacer: add, commit, push
   
2. **Introducción a Python + VS Code** (15 min)
   - Verificar instalaciones
   - Configurar extensiones
   
3. **Conceptos teóricos** (25-40 min)
   - ¿Qué es FastAPI?
   - API REST y CRUD
   - Códigos de estado HTTP

---

### Práctica: Clase2_Taller.md (90-105 min)

#### ✅ Parte 1: Configuración del entorno (10 min)
- Crear entorno virtual
- Instalar `fastapi[all]`
- **Checkpoint:** Todos tienen `(venv)` activo

#### ✅ Parte 2: API básica (15 min)
- Crear carpeta `clase2-api-tareas`
- Código inicial con 2 endpoints simples
- Ejecutar con uvicorn
- **Checkpoint:** Todos ven `/docs` funcionando

#### ✅ Parte 3: Introducción a APIdog (10 min)
- Crear cuenta gratuita
- Probar endpoints básicos
- Crear colección
- **Checkpoint:** Todos hicieron un GET exitoso

#### ✅ Parte 4: Implementar CRUD (30 min)
- Actualizar main.py con código completo
- Explicar modelo Pydantic
- Explicar cada endpoint
- **Checkpoint:** Código compilando sin errores

#### ✅ Parte 5: Probar CRUD con APIdog (20 min)
- POST: Crear 3 tareas
- GET: Listar todas y obtener una
- PUT: Actualizar una tarea
- DELETE: Eliminar una tarea
- **Checkpoint:** Todos completaron las 4 operaciones

#### ✅ Parte 6: Subir a Git (10 min)
- git add, commit, push
- Verificar en GitHub
- **Checkpoint:** Código visible en GitHub

#### ✅ Entregable y cierre (15 min)
- Verificar checklist del entregable
- Responder dudas finales
- Recoger links de repositorios

---

## 🚨 Problemas comunes y soluciones

### Problema 1: "python no se reconoce"
**Solución:**
```bash
# Verificar instalación
where python
# Si no aparece, reinstalar Python marcando "Add to PATH"
```

### Problema 2: No se activa el entorno virtual
**Windows PowerShell - Error de permisos:**
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
.\venv\Scripts\Activate.ps1
```

### Problema 3: "ModuleNotFoundError: No module named 'fastapi'"
**Solución:**
```bash
# Verificar que el entorno virtual esté activo (debe verse (venv))
pip list  # Ver paquetes instalados
pip install "fastapi[all]"  # Reinstalar si es necesario
```

### Problema 4: uvicorn no se ejecuta
**Solución:**
```bash
# Verificar que estás en la carpeta correcta
cd clase2-api-tareas
# Verificar que main.py existe
ls  # o dir en Windows
# Ejecutar con python -m
python -m uvicorn main:app --reload
```

### Problema 5: APIdog no puede conectar a localhost
**Solución:**
- Verificar que uvicorn esté corriendo
- Usar `http://127.0.0.1:8000` en lugar de `localhost`
- Verificar firewall/antivirus

### Problema 6: Git push falla
**Solución:**
```bash
# Verificar configuración
git config --global user.name
git config --global user.email

# Si falta configurar:
git config --global user.name "Nombre Completo"
git config --global user.email "email@ejemplo.com"

# Verificar remote
git remote -v
```

---

## 📊 Checklist para el docente

### Antes de la clase:
- [ ] Verificar que Python está instalado en las aulas
- [ ] Verificar acceso a internet para pip install
- [ ] Tener VS Code portable disponible (si no está instalado)
- [ ] Verificar que GitHub.com es accesible
- [ ] Preparar proyector con `/docs` de ejemplo

### Durante la clase:
- [ ] Hacer pausa después de cada "Checkpoint"
- [ ] Verificar que TODOS completen cada paso antes de continuar
- [ ] Circular por el aula durante las prácticas
- [ ] Tener el código de ejemplo listo para copiar/pegar si hay problemas

### Al final de la clase:
- [ ] Recoger links de repositorios de GitHub
- [ ] Verificar que al menos 80% completó el entregable
- [ ] Responder dudas finales
- [ ] Recordar preparación para próxima clase

---

## 🎯 Objetivos de aprendizaje (verificables)

Al final de la clase, los estudiantes deben poder:

✅ **Crear** un entorno virtual de Python  
✅ **Instalar** paquetes con pip  
✅ **Escribir** una API básica con FastAPI  
✅ **Implementar** las 5 operaciones CRUD  
✅ **Probar** endpoints con APIdog  
✅ **Entender** qué es REST y CRUD  
✅ **Interpretar** códigos HTTP (200, 201, 404, 400)  
✅ **Usar** Git para versionar código  
✅ **Subir** código a GitHub  

---

## 📝 Notas adicionales

### Variaciones según el nivel del grupo:

**Grupo avanzado (termina antes):**
- Agregar puntos extras del taller
- Implementar endpoint de filtrado: `/tareas/completadas`
- Agregar validación: título no vacío
- Crear README.md del proyecto

**Grupo con dificultades:**
- Enfocarse en completar el CRUD básico
- Reducir requisitos de pruebas con APIdog
- Permitir trabajo en parejas
- Extender deadline del entregable

### Adaptaciones para clases virtuales:
- Usar breakout rooms para práctica en grupos pequeños
- Compartir pantalla mostrando cada paso
- Tener sesión de Zoom grabada como referencia
- Crear canal de Slack/Discord para dudas en tiempo real

---

## 🔗 Enlaces importantes

- **Documentación FastAPI:** https://fastapi.tiangolo.com/
- **APIdog:** https://www.apidog.com/
- **Python Downloads:** https://www.python.org/downloads/
- **VS Code:** https://code.visualstudio.com/
- **VS Code Portable:** https://code.visualstudio.com/docs/editor/portable
- **Git Downloads:** https://git-scm.com/downloads

---

**Última actualización:** Octubre 2025  
**Versión:** 1.0 (Revisada y corregida)
