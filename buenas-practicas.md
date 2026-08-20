
## 1. Objetivos del repositorio

El repositorio permite centralizar:

- Código utilizado en la investigación.
- Datos y procesos de transformación.
- Análisis exploratorios.
- Experimentos.
- Resultados.
- Documentación metodológica.
- Versiones del proyecto.
- Información necesaria para reproducir los resultados.

La idea principal es garantizar la trazabilidad, transparencia y reproducibilidad de la investigación.

## 2. Estructura del proyecto

Se recomienda utilizar una estructura organizada como la siguiente:

proyecto-investigacion/
│
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
│
├── data/
│   ├── raw/
│   └── processed/
│
├── src/
│
├── notebooks/
│
├── results/
│   ├── figures/
│   └── tables/
│
├── docs/
│
└── tests/

### Descripción

| Elemento | Descripción |
| :--- | :--- |
| README.md | Documentación principal del proyecto |
| LICENSE | Licencia del proyecto |
| .gitignore | Archivos que Git no debe incluir |
| requirements.txt | Dependencias del proyecto |
| data/raw/ | Datos originales |
| data/processed/ | Datos procesados |
| src/ | Código fuente |
| notebooks/ | Análisis exploratorios y experimentos |
| results/ | Resultados del análisis |
| results/figures/ | Figuras y gráficos |
| results/tables/ | Tablas |
| docs/ | Documentación adicional |
| tests/ | Pruebas del código |

## 3. Documentación

El archivo README.md debe explicar claramente el proyecto. Como mínimo, debe incluir:

- Objetivo de la investigación.
- Pregunta o problema de investigación.
- Datos utilizados.
- Metodología.
- Tecnologías utilizadas.
- Instalación.
- Instrucciones para ejecutar el proyecto.
- Estructura del repositorio.
- Resultados principales.
- Limitaciones.
- Información sobre reproducibilidad.
- Licencia.
- Forma de citar el proyecto.

Una persona que nunca haya visto el proyecto debería poder entenderlo leyendo el README.

## 4. Control de versiones con Git

Git permite mantener un historial de los cambios realizados durante la investigación. Los commits deben ser claros, específicos y descriptivos.

**❌ Evitar**
- cambios
- actualización
- final
- final2
- ahora sí
- cosas nuevas

**✅ Preferir**
- Add data preprocessing
- Fix regression analysis
- Update methodology documentation
- Add Figure 3
- Correct variable names
- Update dependencies

Cada commit debería representar un cambio concreto.

## 5. Uso de ramas

Para cambios importantes se recomienda trabajar con ramas independientes.

**Ejemplo de flujo:**

```text
main
├── analysis
├── data-cleaning
├── new-model
├── figures
└── documentation

```

* **main:** Debe contener una versión estable del proyecto.
* **Ramas de trabajo:** Pueden utilizarse para nuevos análisis, modelos, correcciones, documentación, visualizaciones o experimentos.

Una vez terminado el trabajo, la rama puede integrarse mediante un Pull Request.

## 6. Pull Requests

Los Pull Requests (PR) permiten revisar los cambios antes de incorporarlos a `main`. Un PR debería explicar:

1. **¿Qué se modificó?** (ej. Se añadió un nuevo modelo de regresión).
2. **¿Por qué se modificó?** (ej. El modelo anterior no permitía evaluar adecuadamente la relación entre las variables).
3. **¿Qué debe revisarse?** (Código, parámetros, resultados, figuras, metodología).

Los PR son especialmente útiles cuando varias personas trabajan en la investigación.

## 7. Issues

Los Issues permiten organizar tareas, problemas, preguntas y mejoras.

**Ejemplos:**

* #12 Revisar valores faltantes
* #13 Reproducir Figura 2
* #14 Actualizar metodología
* #15 Comparar modelos
* #16 Revisar resultados estadísticos

## 8. Organización de los datos

Los datos originales deben mantenerse separados de los datos procesados.

* **Datos originales (`data/raw/`):** Estos datos deberían conservarse sin modificaciones.
* **Datos procesados (`data/processed/`):** Aquí se almacenan los datos después de aplicar procesos de limpieza, transformación o filtrado mediante código, garantizando la reproducibilidad.

## 9. Protección de datos sensibles

Nunca se deben publicar datos sensibles o información privada (nombres, correos, direcciones, historias clínicas, contraseñas, claves API, etc.) sin autorización.

Si los datos originales no pueden publicarse, incluya:

* Una descripción de los datos.
* Datos anonimizados.
* Un conjunto de datos de ejemplo.
* Instrucciones para solicitar acceso.

## 10. Archivo .gitignore

El archivo `.gitignore` permite evitar que determinados archivos (venv, entornos, cachés, archivos temporales, etc.) sean añadidos accidentalmente al repositorio.

## 11. Protección de claves y contraseñas

Nunca se deben almacenar secretos directamente en el código.

**❌ Incorrecto**

```python
API_KEY = "mi_clave_secreta"
PASSWORD = "mi_contraseña"

```

**✅ Correcto**

```python
import os
API_KEY = os.getenv("API_KEY")

```

## 12. Reproducibilidad

El flujo de trabajo debe garantizar la reproducibilidad documentando la versión del lenguaje, dependencias, datos, parámetros, métodos y entorno.

Flujo ideal:
`Datos → Preprocesamiento → Análisis exploratorio → Modelo → Evaluación → Resultados → Figuras y tablas`

## 13. Dependencias

Las dependencias deben estar documentadas. En Python, utilice `requirements.txt` o herramientas como Conda (`environment.yml`), `renv.lock` (R), Docker, u otros gestores de entornos.

## 14. Notebooks

Los notebooks son útiles para exploración, visualización y experimentación, pero la lógica importante y reutilizable debería mantenerse en módulos `.py` dentro de `src/`.

## 15. Documentar las decisiones metodológicas

No basta con indicar qué se hizo; explique por qué. Documente criterios de inclusión/exclusión, tratamiento de valores faltantes, transformaciones, selección de variables y parámetros.

## 16. Separar análisis exploratorio y análisis final

Diferencie los experimentos exploratorios (`notebooks/`) de los análisis utilizados para las conclusiones finales.

## 17. Organización de resultados

Los resultados deben organizarse en `results/figures/` y `results/tables/`. Utilice nombres de archivos descriptivos, evitando nombres como `grafico_final2.png`.

## 18. Registro de experimentos

Cuando se realizan múltiples experimentos, registre sus características y resultados en una tabla.

| Experimento | Modelo | Parámetros | Resultado |
| --- | --- | --- | --- |
| EXP-001 | Modelo A | Default | 0.81 |
| EXP-002 | Modelo A | Optimizado | 0.85 |
| EXP-003 | Modelo B | Default | 0.83 |

## 19. Versionado de la investigación

Utilice etiquetas (tags) para identificar estados importantes del proyecto (ej. `v1.0.0 - Final analysis`).

## 20. Tests

Cuando sea necesario, incluya pruebas (`tests/`) para detectar errores y cambios accidentales en el código.

## 21. Automatización

Cuando sea posible, automatice tareas repetitivas (datos, entrenamiento, reportes) usando GitHub Actions.

## 22. Trazabilidad

Cada resultado debe relacionarse con su origen (código, datos procesados, datos originales, versión del proyecto).

## 23. Licencia

Indique siempre la licencia del proyecto (ej. MIT, Apache, etc.).

## 24. Citar el proyecto

Si el repositorio forma parte de una publicación, indique cómo citarlo. Para investigación científica, considere usar archivado con DOI.

## 25. Checklist de reproducibilidad

* [ ] El README explica el objetivo de la investigación.
* [ ] La pregunta de investigación está documentada.
* [ ] La estructura del proyecto es clara.
* [ ] Los datos están organizados.
* [ ] Los datos sensibles no están publicados.
* [ ] El código está documentado.
* [ ] Las dependencias están especificadas.
* [ ] El entorno de ejecución está documentado.
* [ ] El análisis puede reproducirse.
* [ ] Las decisiones metodológicas están documentadas.
* [ ] Los resultados están organizados.
* [ ] Los commits son descriptivos.
* [ ] Las versiones importantes están etiquetadas.
* [ ] Los tests están incluidos cuando son necesarios.
* [ ] La licencia está definida.
* [ ] La forma de citar el proyecto está indicada.

## 26. Flujo de trabajo recomendado

`Definir pregunta → Crear repo → Documentar → Organizar datos → Crear entorno → Análisis exploratorio → Documentar decisiones → Desarrollar análisis → Pruebas → Resultados → Revisar → Versionar → Archivar/Publicar → Citar`

## 27. Principio general

Un repositorio de investigación debe permitir relacionar la pregunta de investigación con los datos, el procesamiento, análisis, experimentos, resultados, conclusiones y, finalmente, la publicación.

**El objetivo es: Reproducible · Trazable · Documentado · Versionado · Transparente**

## 28. Resumen de buenas prácticas

| Área | Buena práctica |
| --- | --- |
| Organización | Mantener una estructura clara |
| Documentación | Utilizar un README completo |
| Git | Realizar commits pequeños y descriptivos |
| Ramas | Separar cambios importantes |
| Pull Requests | Revisar cambios antes de integrarlos |
| Issues | Registrar tareas y problemas |
| Datos | Separar datos originales y procesados |
| Seguridad | No publicar información sensible |
| Reproducibilidad | Documentar código, datos y entorno |
| Metodología | Registrar las decisiones y sus razones |
| Resultados | Utilizar nombres descriptivos |
| Experimentos | Registrar parámetros y resultados |
| Versiones | Crear versiones de etapas importantes |
| Tests | Verificar el funcionamiento del código |
| Licencia | Definir las condiciones de uso |
| Citas | Indicar cómo citar el proyecto |
| Trazabilidad | Relacionar resultados con código y datos |

## Conclusión

Un buen repositorio de investigación debe permitir que otra persona pueda responder fácilmente: ¿Qué se investigó?, ¿qué datos se utilizaron?, ¿cómo fueron procesados?, ¿qué metodología se utilizó?, ¿qué código produjo los resultados?, ¿qué versión del código se utilizó?, ¿es posible reproducir el análisis?

La finalidad no es solamente tener un repositorio ordenado, sino construir un proceso de investigación transparente, reproducible y trazable.
"""

with open("README_investigacion.md", "w", encoding="utf-8") as f:
f.write(markdown_content)

```


He organizado el contenido con una jerarquía clara, utilizando tablas para facilitar la lectura y manteniendo el formato Markdown limpio y profesional, tal como solicitaste.

```
