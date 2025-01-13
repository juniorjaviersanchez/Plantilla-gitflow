# Plantilla Gitflow

Este proyecto utiliza el flujo de trabajo **Gitflow Workflow** para gestionar el desarrollo del código. A continuación, se describe la funcionalidad de cada rama y cómo se utilizan en este proyecto.

---

## **Ramas principales**

### `main`
- **Propósito:** Contiene el código más estable y listo para producción.
- **Uso:**
  - Todas las versiones finales del proyecto se almacenan en esta rama.
  - Solo se actualiza mediante fusiones (merges) desde las ramas `release` o `hotfix`.

### `develop`
- **Propósito:** Base para el desarrollo activo.
- **Uso:**
  - Aquí se fusionan las ramas `feature` una vez que las funcionalidades han sido desarrolladas y probadas.
  - Sirve como un espacio intermedio antes de preparar un lanzamiento.

---

## **Ramas de soporte**

### `feature/<nombre-de-la-funcionalidad>`
- **Propósito:** Se utiliza para desarrollar nuevas funcionalidades o características.
- **Uso:**
  - Las ramas `feature` se crean a partir de `develop`.
  - Ejemplo de creación:
    ```bash
    git checkout develop
    git checkout -b feature/nueva-funcionalidad
    ```
  - Una vez completada la funcionalidad, se fusiona de vuelta en `develop`.

### `release/<versión>`
- **Propósito:** Preparar una nueva versión para su lanzamiento.
- **Uso:**
  - Las ramas `release` se crean a partir de `develop` cuando el proyecto está listo para ser lanzado.
  - Aquí se realizan ajustes finales como correcciones de errores menores, optimización de código o actualizaciones de documentación.
  - Ejemplo de creación:
    ```bash
    git checkout develop
    git checkout -b release/v1.0.0
    ```
  - Una vez finalizada, se fusiona tanto en `main` como en `develop`.

### `hotfix/<nombre-del-hotfix>`
- **Propósito:** Aplicar correcciones rápidas a problemas críticos en producción.
- **Uso:**
  - Las ramas `hotfix` se crean a partir de `main` cuando es necesario solucionar un problema urgente en producción.
  - Ejemplo de creación:
    ```bash
    git checkout main
    git checkout -b hotfix/correccion-urgente
    ```
  - Una vez solucionado, se fusiona tanto en `main` como en `develop`.

---

## **Resumen del flujo de trabajo**
1. **Desarrollo de nuevas funcionalidades:**
   - Crear una rama `feature` desde `develop`.
   - Desarrollar, probar y fusionar en `develop`.

2. **Preparación para lanzamiento:**
   - Crear una rama `release` desde `develop`.
   - Realizar ajustes finales y fusionar en `main` y `develop`.

3. **Correcciones urgentes:**
   - Crear una rama `hotfix` desde `main`.
   - Solucionar el problema y fusionar en `main` y `develop`.

---

## **Comandos útiles**
- Crear una rama nueva:
  ```bash
  git checkout -b <nombre-de-la-rama>
  ```
- Fusionar una rama:
  ```bash
  git checkout <rama-destino>
  git merge <rama-a-fusionar>
  ```
- Subir una rama al repositorio remoto:
  ```bash
  git push origin <nombre-de-la-rama>
  ```

---

Este enfoque ayuda a mantener el proyecto organizado y facilita la colaboración entre los desarrolladores. ¡A desarrollar con éxito! 🚀

