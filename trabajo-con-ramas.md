
markdown_content = """# Investigación: Trabajo con ramas en GitHub

## 1. Introducción

El trabajo con ramas (*branches*) es una de las características fundamentales de Git y GitHub para desarrollar proyectos de forma organizada. Una rama permite trabajar sobre una versión independiente del proyecto sin modificar directamente la rama principal.

En GitHub, normalmente se utiliza una rama llamada `main` como rama principal. Los desarrolladores pueden crear otras ramas para desarrollar funcionalidades, corregir errores o realizar modificaciones y, cuando el trabajo está listo, integrarlo a `main` mediante un Pull Request. GitHub permite gestionar las ramas, establecer cómo se realizan las fusiones y proteger ramas importantes.

---

## 2. ¿Qué es una rama?

Una rama es una línea independiente de desarrollo dentro de un repositorio Git.

Por ejemplo, imaginemos un proyecto con esta estructura:

```text
main
 │
 ├── versión estable del proyecto
 │
 └── nueva-funcionalidad

```

La rama `main` puede contener la versión estable del proyecto, mientras que `nueva-funcionalidad` permite realizar cambios sin afectar inmediatamente a `main`.

Esto es especialmente útil cuando varias personas trabajan simultáneamente en un mismo proyecto.

### Ejemplo

Supongamos que tenemos una página web y queremos agregar un sistema de inicio de sesión. En lugar de modificar directamente `main`, podemos crear:

```text
main
   \
    └── feature/login

```

En `feature/login` podemos:

* Crear nuevos archivos.
* Modificar código.
* Hacer varios commits.
* Probar la funcionalidad.
* Corregir errores.

Mientras tanto, `main` permanece estable.

---

## 3. ¿Por qué utilizar ramas?

El uso de ramas proporciona varias ventajas:

* **Separación del trabajo:** Cada funcionalidad o corrección puede desarrollarse en su propia rama (ej: `feature/login`, `feature/pagos`, `fix/error-login`).
* **Protección de la versión principal:** Los cambios no tienen que llegar directamente a `main`. Esto permite revisar y probar el trabajo antes de incorporarlo.
* **Trabajo colaborativo:** Varias personas pueden trabajar al mismo tiempo en diferentes ramas sin modificar constantemente el trabajo de los demás.
* **Historial organizado:** Los commits relacionados con una determinada funcionalidad quedan agrupados dentro de su rama.
* **Experimentación:** Una rama también puede utilizarse para probar una idea sin poner en riesgo el código estable.

---

## 4. Rama main

`main` suele utilizarse como la rama principal de un repositorio. Sin embargo, `main` no es técnicamente una rama "especial" de Git; es simplemente el nombre convencional para la rama principal. GitHub permite incluso cambiar cuál es la rama predeterminada de un repositorio.

Una buena práctica es evitar realizar cambios directamente sobre `main` en proyectos donde trabajan varias personas.

---

## 5. Crear una rama

Una rama puede crearse desde GitHub o desde Git en el ordenador.

Utilizando Git:

```bash
# Crear la rama
git branch feature/login

# Cambiar a ella
git checkout feature/login

```

O utilizar el comando moderno:

```bash
git switch -c feature/login

```

Para comprobar en qué rama estamos:

```bash
git branch

```

El `*` indica la rama actualmente seleccionada.

---

## 6. Trabajar dentro de una rama

Una vez creada la rama, podemos modificar el proyecto, añadir cambios, hacer commits y enviarlos a GitHub:

```bash
git switch -c feature/login

# Realizamos cambios en los archivos
git add .
git commit -m "Agregar sistema de inicio de sesión"

# Enviar la rama a GitHub
git push -u origin feature/login

```

---

## 7. ¿Qué es un Pull Request?

Un Pull Request (PR) es una solicitud para incorporar los cambios de una rama en otra. Permite revisar los cambios antes de fusionarlos, incluyendo:

* Título y descripción.
* Archivos modificados y diferencias (diffs).
* Comentarios y revisiones.
* Comprobaciones automáticas.

---

## 8. Flujo de trabajo habitual

1. **Crear una rama** a partir de `main`.
2. **Realizar cambios** y commits en la rama.
3. **Push** al repositorio remoto.
4. **Crear Pull Request** en GitHub.
5. **Revisar** el código.
6. **Merge** a `main`.

---

## 9. Merge

El *merge* es el proceso mediante el cual se incorporan los cambios de una rama a otra. GitHub permite diferentes métodos para fusionar Pull Requests:

* **Merge commit:** Conserva los commits de las ramas y crea un commit de merge.
* **Squash:** Combina varios commits de una rama en uno solo antes de incorporarlos a la rama principal.
* **Rebase:** Reorganiza los commits para construir una historia más lineal.

---

## 10. Conflictos entre ramas

Un conflicto ocurre cuando Git no puede determinar automáticamente cómo combinar cambios (por ejemplo, si dos ramas modifican la misma línea de un archivo). En este caso, el desarrollador debe resolver manualmente el conflicto y hacer un nuevo commit.

---

## 11. Mantener una rama actualizada

Si trabajamos en una rama (`feature/login`) mientras otras personas incorporan cambios a `main`, nuestra rama podría quedar desactualizada. Para actualizarla:

```bash
git switch main
git pull
git switch feature/login
git merge main

```

---

## 12. Protección de la rama main

En proyectos importantes, `main` puede estar protegida. Se pueden exigir:

* Revisiones de otros desarrolladores.
* Comprobaciones de estado exitosas (tests).
* Restricciones sobre quién puede hacer push o borrar ramas.

---

## 13. Reglas y rulesets

GitHub utiliza *rulesets* para establecer reglas para determinadas ramas o etiquetas. Permiten definir:

* Qué ramas están protegidas.
* Quién puede hacer cambios.
* Condiciones que debe cumplir un Pull Request.

---

## 14. Eliminar una rama

Una vez que una funcionalidad ya fue incorporada a `main`, normalmente ya no es necesario conservar la rama de trabajo. GitHub permite configurar la eliminación automática de las ramas después de que sus Pull Requests sean fusionados.

---

## 15. Buenas prácticas

* **No trabajar directamente sobre `main**` en proyectos colaborativos.
* **Nombres descriptivos:** `feature/login`, `fix/error-registro`, `docs/manual`.
* **Commits pequeños y claros.**
* **Actualizar la rama** antes de realizar el merge.
* **Utilizar Pull Requests** para revisar cambios.
* **Proteger `main**` en proyectos importantes.
* **Ejecutar pruebas** antes de fusionar.

---

## 16. Ventajas y desventajas

| Ventaja | Desventaja |
| --- | --- |
| Permiten trabajar en paralelo | Pueden generar muchas ramas |
| Protegen el código principal | Pueden producir conflictos |
| Facilitan las revisiones | Requieren aprender Git |
| Permiten experimentar | Un mal manejo puede complicar el historial |
| Facilitan el trabajo en equipo | Las ramas desactualizadas pueden causar problemas |

---

## 17. Conclusión

El trabajo con ramas es fundamental para desarrollar proyectos de forma segura y colaborativa utilizando GitHub. Permiten separar el desarrollo, los Pull Requests garantizan la revisión de cambios, y la protección de ramas mantiene estable el proyecto.

---

*Fuentes: Documentación oficial de GitHub.*
"""


