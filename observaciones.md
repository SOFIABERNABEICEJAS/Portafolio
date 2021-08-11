# Observaciones

Sofi, felicitaciones por tu trabajo. Tu portfolio está muy hermoso, y se nota mucho el esfuerzo por lograr un trabajo con personalidad propia que a la vez cumpla las consignas y el diseño propuesto.

Como dije en clase, este trabajo no se hace para que constates conocimientos, sino para que aprendas: en ese sentido, mi intencion es que estos comentarios te sirvan para aprender, mejorar tu codigo a futuro e ir apreciando mejor qué se espera de nosotras como desarrolladoras front end.

## Estructura correcta de documento HTML

Tu HTML esta realmente excelente. Claro, prolijo, muy bien comentado e identado.

Algo que me llama la atención es tu `header`, dado que allí tenés una orden que no cumple la estructura solicitada para los fonts de google:

```html
    <link href="https://fonts.googleapis.com/css2? family = Roboto & display = swap" rel="hoja de estilo">

<!-- compara con: -->
    <link href="https://fonts.googleapis.com/css2?family=Ultra&display=swap" rel="stylesheet"> 
```

Me da la impresión que el autotraductor del navegador te cambió ese link. La consecuencia es que Roboto no se ve bien en tu TP (yo la veo como Arial)

Tenés tendencia a agregar divs innecesarios. Considerá por ejemplo el div con la clase "contenedor-navegacion". Podrías borrarlo sin consecuencias si pasás sus estilos a "barra-de-navegacion". Cositas así se repiten a lo largo de tu código: está bueno lograr la menor cantidad de elementos posible. Dicho esto, yo prefiero que los divs sobren antes de que falten: un div de más se soluciona muy fácil, un div menos puede ser un gran dolor de cabeza cuando estamos recién arrancando. Este sería un comentario que quizá me reservaría para futuros trabajos, pero veo tan bien tu código que me siento confiada en recomendarte que empieces a ver estas cosas desde ya. 

Un error bastante grave que cometes seguido es escribir "seccion" en lugar de "section" en tus etiquetas. HTML no tiene idea de lo que es la etiqueta "seccion", ni un lector de pantalla. Ojo con eso. 

Utilizás ocasionalmente etiquetas `br` para separar las cosas, y la etiqueta ` <strong>` para darle grosor al texto:: no llegué a comentarlo en clase, pero esto es incorrecto. Esas etiquetas son un resabio de viejas épocas en las cuales css no era tan poderoso como ahora, pero usarla hoy viola uno de los principios básicos de programación: la separación de responsabilidades. Los estilos se dan con css, la estructura se da con html. Una decisión de estilo como un espaciado entre dos elementos debe controlarse con css -flex, elementos en bloque, etc, no con `br`.

Dejas muchos saltos de linea sin sentido en tu HTML que dificultan bastante su lectura. 

## Respeta la consigna

- El portfolio cuenta con las secciones solicitadas
- Al clickear en los links de navegación, debe llevar a la sección correspondiente

Cumplido. 

- Al clickear en los links de contacto, debe llevar a la página externa correspondiente 

No cumplido. No es necesario que agregues tus propias redes si es algo que preferís no hacer, pero
cualquier link a una web externa hubiera servido para cumplir la consigna.

- El portfolio debe tener un diseño responsivo y verse correctamente en distintos dispositivos 

No puedo decidir si este punto está cumplido o no, ya que el responsive está perfecto en todos los elementos menos en el form... pero el form tiene un impacto tan grande en cómo se ve el resto de tu página en celulares, que afecta todo lo demás y no podemos decir que esta web es responsive. El culpable es un display flex innecesario en .formulario

- El portfolio debe estar deployado y ser accesible desde una URL 

Cumplido. 

- El repositorio en GitHub debe tener un readme adecuado

Cumplido

### Respeta el diseño dado

Cumplido, salvo por las tarjetas de Mis Proyectos, que se ven tiradas hacia la izquierda en lugar de centradas. Asumo que vos en tu compu lo ves bien. No le des un width con porcentajes a .proyectos-ilustracion, usa una medida fija (como 1000px) y eso va a ayudar a que se vea consistentemente posicionado en cualquier medida de escritorio. 

### Buena estructura de proyecto

Cumplido. Cuidado con los archivos que tienen mayúscula en el título, algo que podría traerte problemas en el linkeado. Está bien que hayas puesto las imágenes en assets, pero la excepción a esta regla es el favicon, que siempre debería ir en la carpeta principal. Atención también a su nombre: debería ser favicon.ico, no favicon.ico.svg. 

### Código bien indentado

Tabulas muy bien, lo cual parece un detalle extra cuando una recien comienza pero ayuda un monton a su legibilidad, y que lo hayas logrado en esta etapa es un gran mérito. Ya te comenté el exceso de saltos de linea, que dificultan la lectura. Evitalos. 

En tu CSS el tabulado está perfecto, pero no dejas el espaciado correcto en cada orden. En lugar de escribir por ejemplo `.name{`, deja un espacio entre el nombre de la clase y la llave: `.name {`. Tambien dejas saltos de linea innecesarios en css. 


### Comentarios que permiten mejorar la legibilidad del código

Impecables. 

### Uso correcto de etiquetas semánticas

- Me llama la atención que hayas usado `div` para las tarjetas de Mis Conocimientos y Mis Proyectos: yo diría que deberían ser `article`. Pero es el único detalle a comentar aquí (y hay quien podría discutirme que deberían ser divs)

- Ojo con las etiquetas "seccion" en lugar de `section`. Lo mismo en el footer: usas la etiqueta "cite" que no existe. Debería ser un `p`. 

### Buenos nombres de clases

Muy correctos! 

### Código CSS bien estructurado

Cumplido a nivel formal. Noto algunos estilos innecesarios o confusos, que te voy indicando en tu archivo de css.

### Reutilización de estilos

Cumplido en general, veo mucho interés por eso. Repetis muchisimos display: flex que no necesitas, ojo con eso. Display flex sirve para acomodar los hijos de un contenedor: no tiene sentido si el elemento no tiene hijos. 

### Cumple con criterios básicos de accesibilidad

- Los colores tienen un contraste adecuado

Cumplido. 

- Las imágenes tiene el atributo `alt` que corresponde

Cumplido salvo para Mis Conocimientos. Si te pareció innecesario agregar `alt` para esas imagenes, correspondía un aria-hidden en lugar de dejar el alt vacío (que indica que la imagen es decorativa: aquí claramente es ilustrativa). Dejarlo vacía es decirle al usuario que depende del lector de pantalla "aquí hay una imagen y no te voy a decir qué es", lo que no es una buena experiencia. 

- Los íconos y elementos que no presentan texto agregan la información correspondiente por otros medios (etiquetas aria, texto oculto)

Tenés aria-label en tus iconos, pero comentamos en clase que el lector de pantalla va a ignorar los iconos a menos que les agreguemos role="img" como atributo, así que a fines prácticos es lo mismo que si no estuviesen. 


- Los íconos y elementos que no necesitan ser anunciados por un lector de pantalla tienen la etiqueta aria correspondiente

No veo que sea necesario en tu TP. 

- Commits con mensajes adecuados

Cumplido, noto muchos y buenos commits en tu proyecto, lo que siempre se agradece.

- Cuenta con un favicon

Cumplido, aunque debería estar en la carpeta principal y con el tipo de archivo indicado (ico en lugar de svg). 

### Nota: 8
