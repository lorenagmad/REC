# Guía de REC: crea tu concurso desde cero

REC convierte tus cuestionarios en un concurso de televisión en directo. Tiene dos partes:

- **El plató:** la web que abre tu alumnado. Muestra tus concursos, pide la contraseña y presenta las preguntas como un programa en directo, presentado por Cam, la cámara.
- **El estudio:** tu espacio de trabajo. Ahí preparas las preguntas, creas los concursos, los publicas y analizas los resultados.

Todo se publica gratis en GitHub Pages y funciona en el navegador, sin servidores ni cuentas para el alumnado. Las preguntas viajan cifradas: solo se abren con la contraseña de cada concurso.

El original de REC está en <https://github.com/lorenagmad/REC>.

---

## Parte 1. Pon en marcha tu sitio (una sola vez)

### Paso 1. Descarga el kit de REC

1. Entra en <https://github.com/lorenagmad/REC>, abre la carpeta `descargas` y pulsa en `rec-kit.zip`.
2. Pulsa el botón de descarga (**Download raw file**, el icono de la flecha hacia abajo).
3. Descomprime el archivo. Dentro encontrarás esta guía y una carpeta llamada **`web`**, que es lo único que subirás a GitHub.

### Paso 2. Crea tu cuenta de GitHub

Si no tienes cuenta, entra en <https://github.com>, pulsa **Sign up** y sigue los pasos (correo, contraseña y nombre de usuario). Tu nombre de usuario formará parte de la dirección de tu concurso, así que elige uno sencillo.

### Paso 3. Crea un repositorio para tu concurso

1. Pulsa el **+** de arriba a la derecha y elige **New repository**.
2. En **Repository name** escribe un nombre corto, sin espacios ni tildes, por ejemplo `concurso-historia`. Aparecerá en la dirección web.
3. Deja marcado **Public**. (Un repositorio privado también sirve, pero para publicarlo necesitas GitHub Pro, que es gratuito para docentes a través de GitHub Education.)
4. No marques ninguna de las opciones de abajo (README, .gitignore, licencia).
5. Pulsa **Create repository**.

### Paso 4. Sube los archivos de REC

1. En la página del repositorio recién creado, pulsa el enlace **uploading an existing file**.
2. Abre en tu ordenador la carpeta `web` del kit, selecciona **todo lo que hay dentro** (`index.html`, `studio.html`, `README.md` y la carpeta `contests`) y arrástralo a la página de GitHub. Arrastra el contenido, no la carpeta `web` entera.
3. Espera a que terminen de cargarse los archivos y pulsa **Commit changes**.

### Paso 5. Publica tu sitio

1. En el repositorio, entra en **Settings** (la rueda dentada de la barra superior) y, en el menú de la izquierda, en **Pages**.
2. En **Source**, deja **Deploy from a branch**. En **Branch**, elige `main` y la carpeta `/ (root)`, y pulsa **Save**.
3. Espera uno o dos minutos y recarga la página. Arriba aparecerá **Your site is live at…** con tu dirección, que tendrá esta forma:

   `https://tu-usuario.github.io/concurso-historia/`

Esa es la dirección para tu alumnado. Ábrela: verás la portada de REC, todavía sin concursos.

Tu estudio está en la misma dirección terminada en `studio.html`:

`https://tu-usuario.github.io/concurso-historia/studio.html`

Guárdala en favoritos: es donde trabajarás a partir de ahora.

---

## Parte 2. Prepara tu concurso en el estudio

Abre tu estudio. Tiene cinco pestañas: **Curso**, **Banco de preguntas**, **Concursos**, **Publicar** y **Resultados**. Arriba a la derecha puedes cambiar el idioma (ES/EN) y abrir esta guía con **Ayuda**.

- Todo lo que haces se **guarda solo** en ese navegador.
- Usa **Guardar proyecto** de vez en cuando para tener una copia en tu ordenador (archivo `.rec.json`), y **Abrir proyecto** para recuperarla o seguir trabajando en otro ordenador.
- ⚠️ El archivo del proyecto contiene las preguntas, las respuestas y las contraseñas sin cifrar. **Guárdalo solo en tu ordenador y no lo subas nunca a GitHub.**

### 1. Curso

Escribe el nombre de tu curso o asignatura (aparecerá en la portada), un subtítulo si quieres y el idioma por defecto del concurso.

### 2. Banco de preguntas

**Importar desde Moodle.** En Moodle, entra en el banco de preguntas de tu curso, elige **Exportar**, el formato **Moodle XML** y la categoría, y descarga el archivo. En el estudio, pulsa **Importar Moodle XML** (puedes elegir varios archivos a la vez).

Se importan las preguntas de opción múltiple (una o varias correctas), verdadero o falso, emparejamiento, respuesta corta y ordenación (*Ordering*), con sus imágenes, sus vídeos y su retroalimentación, que el alumnado verá como explicación. El estudio te avisará de:

- **imágenes enlazadas desde otra web:** pueden dejar de verse. Edita la pregunta, quita esa imagen y añade el archivo;
- **vídeos que pesan mucho:** cada alumno los descargará enteros. Valora recortarlos o subirlos a YouTube y añadir el enlace;
- **preguntas omitidas:** de tipos no compatibles o repetidas.

**Crear preguntas.** Pulsa **Nueva pregunta** y elige el tipo. En todas puedes añadir una imagen (se comprime sola), un vídeo o un enlace de YouTube o Vimeo, una explicación tras responder y, si quieres, un tiempo propio.

- **Respuesta corta:** no distingue mayúsculas ni tildes (salvo que lo marques). Usa `*` como comodín y da puntos parciales con un porcentaje.
- **Señalar en imagen:** añade la imagen y arrastra sobre ella para dibujar las zonas correctas (rectángulos, o círculos si marcas «Círculo»).

**Temas.** Asigna un tema a cada pregunta: filtra, marca varias y pulsa **Asignar tema**. Los temas se anuncian antes de cada pregunta, alimentan el análisis por temas y permiten repartir las evaluaciones globales automáticas.

### 3. Concursos

Un concurso es un conjunto de preguntas del banco con su propia contraseña. Pulsa **Nuevo concurso** y completa:

- **Título interno:** aparece en los resguardos del alumnado. No lo cambies una vez usado el concurso.
- **Sección:** por ejemplo, «Tema 1» o «Bloque 1». Los concursos de una misma sección se suman en el ranking.
- **Nombre visible y descripción:** lo que verá el alumnado en la portada.
- **Contraseña:** pulsa **Generar** para obtener una fácil de dictar. Las mayúsculas y las tildes no cuentan.
- **Visible en la portada**, **análisis de respuestas** (el alumnado descarga un archivo xAPI con sus respuestas) y **modo práctica** (sin puntos, sin reloj y con soluciones; usa la misma contraseña).
- **Tiempo y puntuación:** segundos por tipo de pregunta y puntos de un acierto instantáneo y de uno en el último segundo (por defecto, 1000 y 500).
- **Idioma en el que aparece:** en los dos idiomas (por defecto), solo en español o solo en inglés. Útil si preparas el mismo concurso en ambas lenguas: cada versión aparece solo en su idioma.
- **Presentación:** el mensaje de bienvenida de Cam y, si quieres, tus propias frases tras un acierto, un fallo o cuando se acaba el tiempo.

Después elige las preguntas del banco. Para una **evaluación global**, usa **Generar una evaluación global**: eliges los concursos de origen, cuántas preguntas sacar de cada uno y, si quieres, un máximo por tema. El estudio las escoge al azar y puedes ajustarlas a mano.

### 4. Publicar

En la pestaña **Publicar**, el estudio comprueba que todo está listo. Pulsa **Generar el paquete (.zip)** y descomprímelo: dentro hay una carpeta `contests`. Para subirla:

1. En tu repositorio de GitHub, entra en la carpeta `contests`.
2. Pulsa **Add file → Upload files**.
3. Arrastra **todo el contenido** de la carpeta `contests` del paquete (el archivo `index.json` y los archivos `.bin`). Sustituirán a los que ya hubiera.
4. Pulsa **Commit changes**. En uno o dos minutos, tus concursos aparecerán en la portada.

Cada vez que cambies algo (una pregunta, una contraseña, la visibilidad de un concurso), genera el paquete de nuevo y vuelve a subirlo. **Descargar la lista de contraseñas** te da un archivo de texto para tenerlas a mano; no lo subas.

---

## Parte 3. En clase

Comparte la dirección de tu sitio (por ejemplo, en el campus virtual) y di la contraseña justo antes de empezar. El alumnado:

- escribe su nombre y su identificador (DNI, NIE o número de estudiante). Hay un intento por concurso en cada navegador;
- puede cambiar el idioma (ES/EN), silenciar el sonido y abrir **Accesibilidad** (tamaño del texto, alto contraste y reducir animaciones);
- al terminar, copia su resguardo o descarga el archivo (si el concurso tiene análisis) y te lo envía por donde indiques, por ejemplo, una tarea de Moodle.

**Tiempo extra.** En **Resultados → Tiempo extra** generas un código personal ligado al identificador del alumno (+25 %, +50 %, +75 % o el doble). Se lo das en privado y lo escribe antes de empezar. No hay que subir nada a GitHub: el código vale para todos los concursos publicados desde tu proyecto, y su puntuación se calcula sobre el tiempo ampliado. Si empiezas un proyecto nuevo, los códigos repartidos dejan de valer.

---

## Parte 4. Resultados

### Ranking

Elige la sección, pega los resguardos o carga los archivos, y pulsa **Preparar la gala**. El estudio comprueba cada código, descarta los manipulados, avisa de los duplicados y suma los puntos de cada alumno.

La **bonificación** (por ejemplo, preguntas regaladas en el examen) puede ser:

- **Según el porcentaje del máximo** (recomendada): cada alumno sabe desde el principio qué necesita. Ten en cuenta que acertarlo todo respondiendo a mitad de tiempo da un 75 % del máximo.
- **Relativa al primero:** quien más puntos logra obtiene el máximo y el resto, en proporción.

Puedes cambiar el nombre de la bonificación, el número de niveles y los umbrales: el ranking se recalcula al instante. Descarga la versión para publicar (con el identificador parcialmente oculto) y la hoja CSV completa para ti. **Publica el ranking solo en un espacio cerrado, como el campus virtual.**

### Análisis

Carga los archivos `.json` de los concursos con análisis (por ejemplo, todas las entregas de una tarea de Moodle). Hay dos vistas:

- **Un concurso:** resumen, ideas para la próxima clase, mapa de rapidez y acierto (domina, sabe pero duda, se precipita y necesita repaso), análisis pregunta a pregunta (dificultad, error más frecuente y si la pregunta distingue a quien sabe) y alumno a alumno.
- **Todo lo cargado:** dominio por tema y retención entre los concursos de una sección y su evaluación global.

**El archivo xAPI.** El archivo que descarga el alumnado está en formato **xAPI** (Experience API), el estándar para registrar actividades de aprendizaje: contiene una declaración por cada pregunta (qué respondió, si acertó y cuánto tardó) y, dentro, el resguardo verificable que usan el ranking y el análisis. Es un solo archivo por alumno y concurso. El botón **Descargar todas las interacciones en xAPI** junta las declaraciones de todos los archivos cargados en uno, listo para importar en un LRS (el almacén de datos de aprendizaje de tu centro, si lo tiene); con «Anonimizar» marcado, sale sin nombres ni identificadores.

**Repaso en clase** proyecta a pantalla completa las preguntas más falladas con el reparto de respuestas del grupo; la solución aparece al pulsar (también con las flechas y la barra espaciadora). **Anonimizar** sustituye nombre e identificador por un código genérico, el mismo para cada alumno en todos los concursos, también en las exportaciones CSV.

---

## Parte 5. Mantenimiento

**Actualizar REC.** Cuando haya una versión nueva, descarga el kit de nuevo y sube a tu repositorio solo `index.html` y `studio.html` (**Add file → Upload files**), sustituyendo los anteriores. Tus concursos no se tocan.

**Ocultar un concurso.** Desmarca «Visible en la portada», genera el paquete y súbelo. Para verlo igualmente, añade `?all` al final de la dirección.

**Varios grupos o asignaturas.** Crea un repositorio para cada uno siguiendo la Parte 1, o usa secciones distintas en el mismo proyecto.

---

## Seguridad y privacidad

- Sin la contraseña, los archivos de los concursos son ilegibles. Con ella, alguien con conocimientos técnicos podría inspeccionar las respuestas en su navegador: es una medida disuasoria, adecuada para concursos de clase, no para exámenes de alto riesgo.
- Usa contraseñas de dos palabras y un número, y no las digas hasta el momento de empezar.
- Los códigos de los resguardos y de tiempo extra impiden modificar puntuaciones a mano, pero el «un intento por concurso» depende del navegador.
- Los datos del alumnado no pasan por ningún servidor: los resguardos te llegan por el canal que elijas y se procesan en tu ordenador.
- Las imágenes y los vídeos de terceros que incluyas deben poder usarse con fines docentes. Consulta con tu centro antes de publicarlos en una web abierta.

## Preguntas frecuentes

**Un alumno dice que ya hizo el concurso, pero no llegó a terminarlo.** El intento se registra al terminar. Si cerró antes, puede volver a entrar.

**He cambiado una pregunta y no se ve.** Genera el paquete de nuevo, súbelo a la carpeta `contests` y recarga la página.

**La portada dice que no se puede cargar el listado de concursos.** Comprueba que la carpeta `contests` de tu repositorio contiene el archivo `index.json`.

**He perdido el proyecto del estudio.** Si borraste los datos del navegador, ábrelo desde la copia que guardaste con **Guardar proyecto**. Por eso conviene guardarlo de vez en cuando.
