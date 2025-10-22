# Clase 5: Evaluación 1 - Endpoints Personales

## Objetivo
En esta evaluación individual, cada estudiante modificará su propio archivo de endpoint en la API de tareas. Cada archivo contiene 3 subendpoints simples que deben personalizar con información propia. Cada estudiante creará su propio archivo de solución para evitar conflictos al hacer commits. La evaluación consta de 4 retos sencillos, bien guiados y comentados.

## Requisitos Previos
- Asegúrate de tener el entorno virtual activado en la carpeta `clase2-api-tareas`.
- Instala las dependencias si no las tienes: `pip install fastapi uvicorn`.
- Usa VS Code para editar y ejecutar el código. El archivo `launch.json` ya está configurado para ejecutar el proyecto fácilmente desde VS Code.

## Cómo Ejecutar el Proyecto
1. Abre la carpeta `clase2-api-tareas` en VS Code.
2. En el depurador de VS Code (Ctrl+Shift+D), selecciona "FastAPI Server" y presiona Play para iniciar el servidor.
3. El servidor se ejecutará en `http://127.0.0.1:8000`. Puedes probarlo en el navegador.

## Cómo Probar tus Endpoints
Usa el navegador para probar tus endpoints. El servidor corre en `http://127.0.0.1:8000`. Recuerda que tu prefijo es `/[tu_nombre_sin_espacios]`.

- Endpoints sin parámetros: `http://127.0.0.1:8000/[tu_nombre]/saludo`
- Endpoints con parámetros en la ruta: `http://127.0.0.1:8000/[tu_nombre]/doble/5`
- Endpoints con parámetros de query: `http://127.0.0.1:8000/[tu_nombre]/es_par?num=4`

Ejemplos para Andrey Perez Blandon:
- `http://127.0.0.1:8000/andrey_perez_blandon/saludo`
- `http://127.0.0.1:8000/andrey_perez_blandon/doble/10`
- `http://127.0.0.1:8000/andrey_perez_blandon/es_par?num=7`

## Tareas a Realizar
1. **Encuentra tu archivo**: Busca tu archivo en la carpeta `clase2-api-tareas` (ej: `andrey_perez_blandon.py`).

2. **Reto 1 (1 punto)**: Modifica la variable `mi_animal_favorito` al inicio del archivo. Cambia "gato" por el nombre de tu animal favorito (ej: "perro", "elefante").

3. **Reto 2 (1 punto)**: Personaliza el endpoint `/saludo`. Cambia el mensaje a algo personal.

4. **Reto 3 (1 punto)**: Cambia el número en el endpoint `/numero_favorito` a tu número favorito.

5. **Reto 4 (1 punto)**: Crea el endpoint `/suma/{a}/{b}` como se indica en los comentarios.

6. **Reto 5 (1 punto)**: Crea el endpoint `/multiplica` como se indica en los comentarios.

## Documentación
Agrega comentarios en tu código explicando cada endpoint, ej: `# Este endpoint devuelve un saludo personalizado`.

## Entrega
- Sube los cambios a tu archivo al repositorio.
- Haz un commit con un mensaje descriptivo, ej: "Personaliza endpoints - [tu_nombre]".
- No debería haber conflictos ya que cada archivo es único.

## Evaluación
- Se evaluará que los 4 retos funcionen correctamente.
- Código comentado y legible.
- Correcta ejecución sin errores.

¡Éxito en la evaluación!</content>
<parameter name="filePath">g:\My Drive\FUMC\ClasesBackend\curso-backend-fumc\Clase5_Evaluacion1.md
