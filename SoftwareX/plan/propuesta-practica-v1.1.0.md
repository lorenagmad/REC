# Propuesta para REC v1.1.0: registro del modo práctica

*(Texto para pegar en la conversación donde se desarrolla REC.)*

---

Quiero añadir a REC un **registro del modo práctica** para la versión **v1.1.0**, que también incluirá la demo en inglés y los textos suavizados que ya están en `main`. Lo necesito para usar los cuestionarios de repaso de una asignatura del primer semestre y analizar después cómo los usa el alumnado.

## Cómo funciona ahora

En modo práctica, el plató muestra *"Sin puntos, sin resguardo y sin reloj"*:
- no pide nombre ni documento;
- desactiva el análisis (`ANALISIS = … && !PRACTICE`);
- al terminar solo muestra `renderPracticeEnd()`.

Sin embargo, `finish()` ya guarda cada respuesta en `S.log` (respuesta, resultado, tiempo empleado, tema), también en práctica.

## Qué quiero

### 1. Plató (`index.html`)

1. **Identificación obligatoria en práctica cuando el concurso tiene activado «Análisis de respuestas».** Se piden nombre y documento como en el modo evaluable. Si el análisis no está activado, la práctica sigue siendo anónima y sin fichero, como ahora.
2. **Sin puntos y sin reloj visible, pero guardando el tiempo** de cada respuesta. El tiempo no tiene límite y se registra solo para el análisis.
3. **Registro acumulado.** Cada práctica completada se añade a un registro guardado en el navegador (`localStorage`), por concurso y por alumno (documento normalizado). Cada intento lleva número, fecha de inicio y de fin, y las respuestas.
4. **Descarga de un único fichero xAPI con todos los intentos:**
   - Desde la pantalla final de la práctica, con un botón del tipo «Descargar mi registro de práctica».
   - También desde la portada, en la tarjeta del concurso, para que el alumno pueda descargarlo al final del curso.
   - Formato:
     - las mismas declaraciones que `buildXapi()`;
     - una extensión `…/xapi/practice: true` en todas las declaraciones;
     - el número de intento en el contexto (`…/xapi/attempt`);
     - el nombre de fichero distinto del resguardo (p. ej. `practica-<concurso>-<id>.json`).
   - No hace falta código de verificación, porque no puntúa.
5. **Concurso solo en práctica.** Un ajuste por concurso en el estudio, «Solo modo práctica», que oculte el modo evaluable en la portada aunque el alumno tenga la contraseña. Así, el profesor puede abrir para repaso al final del curso un concurso que ya se evaluó en clase.

### 2. Estudio (`studio.html`)

6. **Reconocer los registros de práctica** al cargar ficheros (por la extensión `practice`) y **dejarlos fuera del ranking**. Si llegan varios ficheros del mismo alumno, por ejemplo uno del móvil y otro del portátil, se unen por documento sin duplicar intentos (identificador único de intento).
7. **Nueva vista «Práctica»** dentro del análisis:
   - **Por alumno:** número de prácticas, preguntas practicadas, y acierto en el primer intento frente al último.
   - **Por pregunta:** porcentaje de fallo en práctica, y preguntas que se siguen fallando en el último intento.
   - **Comparación con la sesión evaluada.** Si se cargan a la vez los resguardos del concurso evaluado en clase y los registros de práctica, para cada pregunta: acierto en la sesión frente a acierto en el último intento de práctica, por alumno y en total. Es un análisis parecido al de retención (sesiones frente a evaluación global), pero aplicado a sesión frente a repaso.
   - Exportación anonimizada en CSV/xAPI, igual que el resto del análisis.

### 3. Documentación y versión

8. Actualizar `docs/GUIA.md` y `docs/GUIDE.md`: cómo activar el registro de práctica, el ajuste «Solo modo práctica», y qué fichero deben enviar los alumnos.
9. Regenerar `descargas/rec-kit.zip`, que debe incluir el `LICENSE`, como ahora en `web/LICENSE`.
10. Interfaz en español e inglés para todos los textos nuevos.

## Cómo lo voy a usar

- Al final de cada sesión, el cuestionario se hace en **modo evaluable**, con la contraseña dada en clase.
- Al final del curso, el mismo concurso se abre en **solo modo práctica** para repasar antes del examen, tantas veces como quieran.
- Al terminar, cada alumno sube su registro de práctica al Campus Virtual.
- Con eso quiero comparar lo que fallaron en la sesión con lo que siguen fallando, o ya no, en su último repaso.

## Comprobaciones antes de publicar

- Una práctica sin análisis activado funciona exactamente como ahora: anónima y sin fichero.
- Un registro de práctica no entra en el ranking ni cuenta como resguardo duplicado.
- Dos ficheros del mismo alumno se unen sin duplicar intentos.
- Los resguardos de v1.0.0 se siguen leyendo igual.
