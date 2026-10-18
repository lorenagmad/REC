# Guía de REC

REC tiene dos partes:

- **El plató** (`index.html`): la web que abre el alumnado. Muestra los concursos, pide la contraseña y presenta las preguntas como un programa en directo, presentado por Cam, la cámara.
- **El estudio** (`studio.html`): donde el profesorado prepara las preguntas, crea los concursos, los publica y analiza los resultados.

Todo funciona en el navegador. Las preguntas viajan cifradas y solo se pueden abrir con la contraseña de cada concurso.

## 1. Pon en marcha tu sitio (una sola vez)

1. Crea una cuenta en [GitHub](https://github.com) si no tienes.
2. Crea un repositorio nuevo, por ejemplo `rec`. Puede ser público o privado (para publicar desde uno privado necesitas GitHub Pro, gratuito para docentes con GitHub Education).
3. Sube todos los archivos de esta carpeta: **Add file → Upload files**, arrastra `index.html`, `studio.html`, `README.md`, `.nojekyll` y las carpetas `contests` y `docs`, y pulsa **Commit changes**.
4. Ve a **Settings → Pages**, elige la rama `main` y la carpeta `/ (root)` y pulsa **Save**.
5. En uno o dos minutos tendrás tu sitio en `https://tu-usuario.github.io/rec/`. Ese es el enlace para el alumnado. El estudio está en `https://tu-usuario.github.io/rec/studio.html`.

Comprueba que funciona abriendo el concurso de demostración con la contraseña `rec demo`.

## 2. El estudio

Abre `studio.html` en tu sitio (o en tu ordenador, con doble clic). Tiene cinco pestañas: Curso, Banco de preguntas, Concursos, Publicar y Resultados. Puedes cambiar el idioma del estudio (ES/EN) arriba a la derecha.

- Todo lo que haces se **guarda solo** en ese navegador.
- Usa **Guardar proyecto** para tener una copia en tu ordenador (archivo `.rec.json`) y **Abrir proyecto** para recuperarla o pasarla a otro ordenador.
- ⚠️ El archivo del proyecto contiene las preguntas, las respuestas y las contraseñas sin cifrar. **No lo subas nunca a GitHub.**

Para ver un ejemplo completo, abre `docs/proyecto-demo.rec.json` con **Abrir proyecto**.

## 3. Banco de preguntas

### Importar desde Moodle

En Moodle, entra en **Banco de preguntas → Exportar**, elige el formato **Moodle XML**, selecciona la categoría y descarga el archivo. En el estudio, pulsa **Importar Moodle XML** (puedes elegir varios archivos a la vez).

Tipos compatibles: opción múltiple (una o varias correctas), verdadero o falso, emparejamiento, respuesta corta y ordenación (*Ordering*). Se importan también las imágenes y vídeos incrustados y la retroalimentación (general y por respuesta), que el alumnado verá como explicación.

Avisos que puede darte el estudio:

- **Imágenes enlazadas desde otra web:** la pregunta muestra una imagen alojada fuera de Moodle (por ejemplo, en Kahoot). Puede dejar de verse: edita la pregunta, quita esa imagen y añade el archivo.
- **Vídeos que pesan mucho:** cada alumno los descargará enteros. Valora recortarlos o subirlos a YouTube y añadir el enlace.
- **Preguntas omitidas:** de tipos no compatibles o repetidas.

Si exportas desde ¡En el aire!, usa **Importar de ¡En el aire!** con los archivos de la carpeta `originales`: se conservan los concursos y sus códigos.

### Temas

Asigna un tema a cada pregunta (filtra, marca varias y pulsa **Asignar tema**). Los temas se anuncian antes de cada pregunta, alimentan el análisis por temas y la retención, y permiten repartir las evaluaciones globales automáticas.

### Crear y editar preguntas

Pulsa **Nueva pregunta** y elige el tipo. En todas puedes añadir imagen (se comprime sola), vídeo o enlace de YouTube o Vimeo, una explicación tras responder y, si quieres, un tiempo propio.

- **Respuesta corta:** no tiene en cuenta mayúsculas ni tildes (salvo que lo marques). Usa `*` como comodín y puntúa respuestas parciales con un porcentaje.
- **Señalar en imagen:** añade la imagen y arrastra sobre ella para dibujar las zonas correctas (rectángulos, o círculos si marcas «Círculo»). Este tipo no existe en Moodle.

## 4. Concursos

Un concurso es un conjunto de preguntas del banco con su contraseña. Para cada uno:

- **Título interno:** aparece en los resguardos. No lo cambies una vez usado.
- **Sección:** por ejemplo, «Bloque 1». Los concursos de una sección se suman en el ranking.
- **Contraseña:** pulsa **Generar** para una fácil de dictar. Mayúsculas y tildes no cuentan.
- **Visible en la portada**, **análisis de respuestas** (el alumnado descarga un archivo con sus respuestas) y **modo práctica** (sin puntos, sin reloj y con soluciones; usa la misma contraseña).
- **Tiempo y puntuación:** segundos por tipo de pregunta y puntos de un acierto instantáneo y de uno en el último segundo (por defecto, 1000 y 500).
- **Presentación:** el mensaje de bienvenida de Cam y, si quieres, tus propias frases tras un acierto, un fallo o si se acaba el tiempo.

### Evaluaciones globales automáticas

En **Preguntas del concurso → Generar una evaluación global**, elige los concursos de origen, cuántas preguntas sacar de cada uno y, si quieres, un máximo por tema. El estudio las elige al azar y marca el concurso como evaluación global (necesario para calcular la retención). Después puedes ajustarlas a mano.

## 5. Publicar

En la pestaña **Publicar**, el estudio comprueba que todo está listo y avisa de posibles problemas. Pulsa **Generar el paquete (.zip)**:

1. Descomprime el archivo: dentro hay una carpeta `contests`.
2. En tu repositorio, entra en `contests` → **Add file → Upload files**.
3. Arrastra todo el contenido de la carpeta `contests` del .zip (sustituye los que hubiera) y pulsa **Commit changes**.

Cada vez que cambies algo (una pregunta, una contraseña, la visibilidad), genera el paquete de nuevo y súbelo. **Descargar la lista de contraseñas** te da un archivo de texto para tenerlas a mano (no lo subas).

## 6. En clase

Comparte el enlace de tu sitio (por ejemplo, en el campus virtual) y di la contraseña justo antes de empezar. El alumnado:

- escribe su nombre y su identificador (DNI, NIE o n.º de estudiante); solo hay un intento por concurso en cada navegador;
- puede cambiar el idioma (ES/EN), silenciar el sonido y abrir **Accesibilidad** (tamaño del texto, alto contraste, reducir animaciones);
- al terminar, copia su resguardo o descarga el archivo (si el concurso tiene análisis) y lo envía por donde indiques.

**Tiempo extra:** en **Resultados → Tiempo extra** generas un código personal ligado al identificador del alumno (+25 %, +50 %, +75 % o el doble). Vale para todos los concursos del proyecto y su puntuación se calcula sobre el tiempo ampliado.

## 7. Resultados

### Ranking

Elige la sección, pega los resguardos o carga los archivos y pulsa **Preparar la gala**. El estudio verifica cada código, descarta los manipulados, avisa de duplicados y suma los puntos de cada alumno.

La **bonificación** (por ejemplo, preguntas regaladas en el examen) puede ser:

- **Según el porcentaje del máximo** (recomendada): cada alumno sabe desde el principio qué necesita. Ten en cuenta que acertarlo todo respondiendo a mitad de tiempo da un 75 % del máximo.
- **Relativa al primero:** el primero obtiene el máximo y el resto, en proporción.

Puedes cambiar el nombre de la bonificación, el número de niveles y los umbrales; el ranking se recalcula al instante. Descarga la versión para publicar (con el identificador parcialmente oculto) y la hoja CSV completa para ti. **Publica el ranking solo en un espacio cerrado, como el campus virtual.**

### Análisis

Carga los archivos `.json` de los concursos con análisis (por ejemplo, todas las entregas de una tarea de Moodle). Hay dos vistas:

- **Un concurso:** resumen, ideas para la próxima clase, mapa de rapidez y acierto (domina, sabe pero duda, se precipita, necesita repaso), análisis pregunta a pregunta (dificultad, error más frecuente, si la pregunta distingue a quien sabe) y alumno a alumno.
- **Todo lo cargado:** dominio por tema y retención entre los concursos de una sección y su evaluación global.

**Repaso en clase** proyecta a pantalla completa las preguntas más falladas con el reparto de respuestas; la solución aparece al pulsar (flechas y barra espaciadora). **Anonimizar** sustituye nombre e identificador por un código genérico, igual en todos los concursos para el mismo alumno, también en las exportaciones CSV.

## 8. Seguridad y privacidad

- Sin la contraseña, los archivos de los concursos son ilegibles. Con ella, un alumno con conocimientos técnicos podría inspeccionar las respuestas en su navegador: es una medida disuasoria, adecuada para concursos de clase, no para exámenes de alto riesgo.
- Usa contraseñas de dos palabras y un número y no las digas hasta el momento de empezar.
- Los códigos de los resguardos y de tiempo extra impiden modificar puntuaciones a mano, pero el «un intento por concurso» se basa en el navegador.
- Los datos del alumnado no pasan por ningún servidor: los resguardos llegan por el canal que tú elijas y se procesan en tu ordenador.
- Las imágenes y vídeos de terceros que incluyas deben poder usarse con fines docentes. Consulta con tu universidad antes de publicarlos en una web abierta.

## 9. Preguntas frecuentes

**Un alumno dice que ya hizo el concurso, pero no lo terminó.** El intento se registra al terminar. Si cerró antes, puede volver a entrar.

**He cambiado una pregunta y no se ve.** Genera el paquete de nuevo, súbelo y recarga la página.

**Quiero ocultar un concurso.** Desmarca «Visible en la portada», genera el paquete y súbelo. Para verlo igualmente, añade `?all` a la dirección.

**¿Puedo usar REC con varios grupos?** Sí: crea un repositorio por grupo o usa secciones distintas.
