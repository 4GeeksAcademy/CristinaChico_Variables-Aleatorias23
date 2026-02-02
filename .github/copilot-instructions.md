
# Instrucciones rápidas para agentes de código (Copilot / AI)

Propósito: permitir que un agente (Copilot/AI) sea productivo de inmediato en este repositorio de notebooks sobre variables aleatorias.

- **Qué es este repositorio:** colección de notebooks y recursos didácticos.
  - Ejercicios: [notebook/problems.ipynb](notebook/problems.ipynb) y [notebook/problems.es.ipynb](notebook/problems.es.ipynb).
  - Soluciones (no tocar salvo autorización): [notebook/solutions.ipynb](notebook/solutions.ipynb).
  - Dependencias: [requirements.txt](requirements.txt).
  - Recursos: carpeta `assets/` (imágenes usadas en notebooks).

- **Arquitectura / flujo de datos:**
  - No hay servicio ni paquete; la unidad de trabajo es el notebook. Los cambios se aplican dentro de celdas y se validan ejecutando las mismas.
  - Flujo habitual: editar celdas en `notebook/problems*.ipynb` → ejecutar celdas en Jupyter (o en el devcontainer) → contrastar con `notebook/solutions.ipynb`.

- **Entorno recomendado y comandos clave:**
  - Devcontainer: [.devcontainer/devcontainer.json](.devcontainer/devcontainer.json) (usa Python 3.11). Preferir Codespaces o abrir el devcontainer para reproducibilidad.
  - Local (rápido):

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

  - Si añades dependencias, actualiza `requirements.txt` y notifica que el devcontainer debe reconstruirse (onCreateCommand instala las dependencias).

- **Convenciones y restricciones del proyecto:**
  - No editar `notebook/solutions.ipynb` sin permiso humano.
  - Evitar limpiezas masivas de outputs en notebooks (no quitar outputs salvo que lo indiquen explícitamente).
  - Mantener compatibilidad con Python 3.11 (ver `.devcontainer/devcontainer.json`).

- **Casos de uso concretos para un agente:**
  - Depurar una celda que falla en `notebook/problems.es.ipynb` y proponer una celda corregida.
  - Añadir una pequeña celda de verificación que reproduzca un fragmento de `solutions.ipynb` para validar la corrección.
  - Proponer cambios en `requirements.txt` sólo si puedes comprobar que la dependencia no se usa en `notebook/`.

- **Integraciones y puntos de atención:**
  - No hay tests automatizados: la validación principal es ejecutar las celdas del notebook.
  - Recursos externos: imágenes en `assets/` pueden referenciarse desde notebooks; mantener rutas relativas.

- **Ejemplos rápidos (métodos seguros):**
  - Para proponer una corrección, añade una nueva celda en el notebook con la solución y un comentario explicando el cambio.
  - Para cambios en dependencias, abrir un PR que modifique `requirements.txt` y describa por qué la dependencia puede quitarse o actualizarse.

Si algo está incompleto o quieres que incluya ejemplos extraídos de un notebook concreto, dime cuál y lo añado.
# Instrucciones rápidas para agentes de código (Copilot / AI)

Propósito: ayudar a un agente a ser productivo inmediatamente en este repositorio educativo de ejercicios sobre distribuciones de probabilidad en Python.

- **Visión general:** este repo es una colección de notebooks con ejercicios y soluciones. Componentes clave:
  - Notebooks con ejercicios: [notebook/problems.ipynb](notebook/problems.ipynb) y su versión en español [notebook/problems.es.ipynb](notebook/problems.es.ipynb).
  - Soluciones: [notebook/solutions.ipynb](notebook/solutions.ipynb) (no editar salvo indicación explícita).
  - Dependencias: [requirements.txt](requirements.txt).
  - Configuración de desarrollo en contenedor: [.devcontainer/devcontainer.json](.devcontainer/devcontainer.json).

- **Flujo de datos / arquitectura:** no hay un paquete o servicio backend; el trabajo se realiza dentro de notebooks. Los cambios típicos son:
  1. Editar/executar células en `problems*.ipynb`.
 2. Usar librerías listadas en `requirements.txt` (pandas, numpy, matplotlib, sympy, opencv, scikit-learn, ...).
 3. Validar ejecutando el notebook y comparando con `solutions.ipynb` si es necesario.

- **Flujos de desarrollo importantes:**
  - Recomendación de entorno: usar Codespaces o el devcontainer. `.devcontainer/devcontainer.json` usa `mcr.microsoft.com/devcontainers/python:0-3.11` y ejecuta `pip3 install --user -r requirements.txt` en la creación.
  - Pasos mínimos para reproducir localmente:

```
# crear y activar entorno virtual
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

  - Al abrir el notebook, seleccionar el *kernel* apropiado (ver [README.md](README.md)).

- **Convenciones específicas del proyecto:**
  - Los ejercicios están en `notebook/` y las soluciones en `notebook/solutions.ipynb`. No transformar automáticamente las soluciones ni borrarlas.
  - Mantener la compatibilidad con la versión de Python indicada en `.devcontainer/devcontainer.json` (3.11).
  - Si añades dependencias, actualiza `requirements.txt` y avisa que el contenedor debe reconstruirse para que `onCreateCommand` las instale.

- **Patrones detectables / ejemplos concretos:**
  - Dependencias principales: ver [requirements.txt](requirements.txt) (pandas, numpy, matplotlib, sympy, opencv-python, scikit-learn).
  - Recursos estáticos (imágenes) en `assets/` referenciados desde los notebooks y el README.

- **Integraciones y puntos de atención:**
  - Devcontainer: la imagen y `onCreateCommand` instalan dependencias; cambios en `requirements.txt` requieren reconstrucción del contenedor.
  - No hay tests automatizados en la rama actual; la validación principal es ejecutar los notebooks.

- **Qué puede pedir un agente:**
  - Ejecutar/validar células problemáticas en `notebook/problems*.ipynb` y proponer correcciones de código en la misma celda o en una nueva celda de solución.
  - Sugerir mejoras reduciendo dependencias innecesarias sólo si hay evidencia en el repo.

- **Qué evitar:**
  - No eliminar ni reescribir `notebook/solutions.ipynb` sin autorización humana.
  - Evitar cambios grandes en formatos de notebook (limpiar outputs masivamente) salvo que se solicite explícitamente.

Si algo no está claro o quieres que el agente añada más ejemplos concretos (por ejemplo, una celda de ejemplo ejecutable extraída de `problems.ipynb`), dime y lo ajusto.
