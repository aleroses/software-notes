# Curso de Debugging con Chrome DevTools

> 31-05-2024

## 1. Introducción del curso e historia de Debugging Dev Tools

### ¿Por qué Debugging?

El debugging nos ayuda a solucionar problemas que tengas con el software, ese problema debemos encontrarlo y solucionarlo, este proceso se le llama **debugging.**

> Debugging es el proceso de encontrar y resolver defectos o problemas dentro de un programa (software) que impide el funcionamiento correcto del programa o sistema.

[Recurso oficial:](https://developers.google.com/web/tools/chrome-devtools)

## 2. Introducción a DevTools

Las dev tools son herramientas de desarrollo que vienen en todos los navegadores. No todas son iguales por lo que hay tools muy particulares dependiendo del navegador.

```bash
# Abrir DevTools
Ctrl + Shift + I
```

Elements: HTML
Styles: CSS
Sources: Archivos que se descargan al navegador una vez el proyecto empieza a cargar.

### Instalar Firefox Developer Edition en Linux Mint

[Descargar Firefox Developer Edition](https://www.mozilla.org/en-US/firefox/developer/).

Para instalar Firefox 127.0 Beta 9 en Linux Mint a partir del archivo `firefox-127.0b9.tar.bz2`, sigue estos pasos:

```bash
cd ~/Descargas

# Extraer el archivo
tar xjf firefox-127.0b9.tar.bz2

# Mover Firefox al directorio opt
sudo mv firefox /opt/firefox127
# Esto mantendrá el sistema organizado.

# Crear un enlace simbólico
sudo ln -s /opt/firefox127/firefox /usr/bin/firefox127

# Ejecutar Firefox
firefox127
```

**Crear un acceso directo (opcional)**:

Para crear un acceso directo en el menú de aplicaciones:

- Crea un archivo de escritorio usando un editor de texto como `nano` o `gedit`:
	```bash
	sudo nano /usr/share/applications/firefox127.desktop
	```

- Añade el siguiente contenido al archivo:
     ```plaintext
     [Desktop Entry]
     Name=Firefox Beta 127
     Comment=Web Browser
     Exec=/opt/firefox127/firefox
     Icon=/opt/firefox127/browser/chrome/icons/default/default128.png
     Terminal=false
     Type=Application
     Categories=Network;WebBrowser;
     ```

   - Guarda el archivo y cierra el editor. Para guardar y salir de `nano`, sigue estos pasos:
	- **Guardar**: `Ctrl + O`, luego `Enter`
	- **Salir**: `Ctrl + X`

Ahora deberías tener Firefox 127.0 Beta 9 instalado y listo para usar en tu sistema Linux Mint.

- [Atajos para DevTools Chrome](https://developers.google.com/web/tools/chrome-devtools/shortcuts)
- [Atajos para DevTools Firefox](https://firefox-source-docs.mozilla.org/devtools-user/keyboard_shortcuts/index.html#all-keyboard-shortcuts "Link to this heading")

## 3. Editando HTML

Podemos ver el HTML de una página web en la sección de **Elements** del DevTools. Aquí podremos manipular el HTML o usar el selector y al tocar en algo en específico dentro de la página en **Elements** se colocará en la línea de código html que sea ese elemento seleccionado.

Para modificar textos dentro de etiquetas das doble clic, y también en las etiquetas. 

> Los tres puntos a la derecha nos dejan arrastrar todo ese bloque de código hacia otros lugares.

```html
Elements
... 👈👀 <div class="icon" role="presentation" alt=""></div>
```

### Shortcuts

- **Ctrl + Shift + C**, para activar el selector
- **Ctrl + F**, para hacer búsquedas dentro de **Elements**, este comando también sirve para buscar palabras dentro de una página web

## 4. Editando CSS

Para agregar una declaración CSS a un elemento, use la pestaña Estilos cuando desee cambiar o agregar declaraciones CSS a un elemento.

- Haga clic derecho en el elemento a modificar a continuación y seleccione Inspeccionar.
- Haga clic en la etiqueta, clase o Id cerca de la parte superior de la pestaña Estilos.
- Escribe `background-color` o el estilo deseado y presiona Enter.
- Escribe en este caso como ejemplo `honeydewy` presiona Enter, te debe quedar algo así `background-color: honeydewy`. En el Árbol DOM, puede ver que se aplicó una declaración de estilo en línea al elemento.

Se puede dar doble clic sobre un elemento numérico y con las flechas subir y bajar el número.

También podemos ver cómo se comporta un elemento cuando se activa una _pseudo-class_ desde el apartado `:hov` y también modificarla.

En la sub-sección **Computed** podemos ver todos los estilos que estrictamente solo se está aplicando a ese elemento seleccionado y podemos ver el modelo de caja también.

### Dato

Una vez que realizamos los cambios en los estilos para depurar, es común olvidar cuáles fueron todos los cambios que se realizaron en los estilos, para ello podemos acceder a la herramienta **changes** y observar estos cambios:

- Customize and control DevTools (3 puntos)
- More tools / Changes

### Shortcuts

También tenemos shortcuts para aumentar o disminuir el tamaño de los elementos:

- **Shift + flecha arriba o flecha abajo** = modificas 10px el tamaño. 
- **Ctrl + flecha arriba o flecha abajo** = modificas 100px el tamaño. 
- **Alt + flecha arriba o flecha abajo** = modificas 0.1px el tamaño.

## 5. Colores en DevTools

Para abrir el Selector de colores, encuentra una declaración de CSS en el panel Styles que defina un color (como color: blue). A la derecha del valor de la declaración se encuentra un cuadrado pequeño de color. El color del cuadrado coincide con el valor de la declaración. Haz clic en este pequeño cuadrado para abrir el Selector de colores.

```css
element.style {👇
  background: 🟪 darkslateblue;
}
```

Recordar:

Respecto a los colores de Material Design , para poder ver la combinación de colores que se pueden aplicar a una página, en la sección mencionada de Material Design recordar dar un clic sostenido a cada uno para visualizar la línea de colores de esta forma:

Entrar a la paleta de colores y dirigirse a la sección de Material Design

![](https://i.postimg.cc/sxpFcqdq/5-material-design1.png)

Clic sostenido sobre la línea de colores que desee visualizar

![](https://i.postimg.cc/VvPpdgrR/5-material-design2.png)

## 6. Manejo de sombras en DevTools

A quienes no les aparezcan los tres puntitos para editar las sombras hagan esto:

1. Agreguen el estilo **box-shadow**.
2. Seleccionen la opción: **0 0 black**
3. Les aparecerán dos cuadritos superpuestos los cuales sacan un diálogo que dice: **"Open shadow editor"**
4. Hacen clic ahí y listo.
5. Aplica lo mismo para: text-shadow

![open shadow editor](https://i.postimg.cc/xjz8b17p/6-open-shadow.png)

## 7. Animaciones en DevTools

- Customize and control DevTools (3 puntos)
- More tools / Animations

[Página para probar animaciones](https://animate.style/)

Enlaces de bibliotecas de animaciones y efectos CSS:

- [Hover](https://ianlunn.github.io/Hover/)
- [CSShake](https://elrumordelaluz.github.io/csshake/)
- [Anijs](https://anijs.github.io/)
- [CSS Wand](https://www.csswand.dev/?ref=producthunt)
- [Animate Components](https://animate-components.surge.sh/)
- [Keyframes](https://keyframes.app/)
- [AniCollection](https://anicollection.github.io/#/)
- [SpinKit Loader](https://tobiasahlin.com/spinkit/)
- [Animejs](https://animejs.com/)

### Dato

Si cuando ingresan a **animate.css** y les aparece que no están habilitadas las animaciones en su sistema operativo, solo tienen que ir a Configuración de accesibilidad y Activar las animaciones.

## 8. ¿Cómo medir el código que no ocupamos?

- Customize and control DevTools (3 puntos)
- More tools / Coverage

![Coverage](https://i.postimg.cc/tCk9458V/8-coverage1.png)

Para empezar a usar esta herramienta solo das **Click the record button ⚫...**

En esta parte puedes limpiar todo o recargar la página para ver más detalles de los archivos cargados.

En la parte de **Usage Visualization** tenemos barras de carga en rojo y blanco, lo cual indica el **porcentaje de código no utilizado**, también expresado en bytes, de cada uno de los archivos, respecto del peso total de los mismos que está justamente en la columna que está a la izquierda, cuyo nombre es **Total Bytes**.

![](https://i.postimg.cc/c4C8ZrbZ/8-coverage2.png)

Para ver el código solo basta dar clic en alguno de los elementos en el apartado **URL**.

## 9. JavaScript y el DOM

Para obtener un elemento del DOM lo seleccionamos desde **Elements** en los DevTools de navegador y después vamos a la consola y escribimos `$0` esto nos traerá ese elemento previamente seleccionado.

Para empezar a manipular elementos y para agregarles JavaScript podemos usar estas dos formas:

1. `getElementById()` = para llamar a un ID.
2. Vamos al elemento, damos clic derecho, nos saldrá un menú vamos a donde dice (copy) y después donde dice **Copy JS-PATH**
    Obtendremos algo parecido:
    `document.querySelector("Body > header")`    

![Copy JS path](https://i.postimg.cc/k5rgzyZ6/9-copy-js-path.png)

Posteriormente, con el elemento que obtengamos le podremos añadir funciones con JavaScript.

## 10. DevTools como editor (IDE)

- Sources
- Workspace: Add folder
- Seleccionar toda la carpeta
- Allow

También puedes agregar la carpeta desde tu explorador de archivos, arrastrándola hasta **Workspace**. Además puedes usar Ctrl + P para hacer busquedas rapidas de tus archivos.

![Workspace](https://i.postimg.cc/65jBk4YX/10-workspace.png)

**OJO:** El css permite ser modificado desde el inspector de elementos también, mientras que el HTML y el JavaScript, solo permite ser modificado desde la pestaña **Sources**. Los cambios que hagas en el CSS del lado del inspector de elementos, se guardarán automáticamente en el archivo CSS local. Los cambios que hagas y guardes desde la pestaña **Sources**, se guardarán automáticamente en los archivos locales.

⚠️ Es importante tener cuidado al modificar archivos locales importantes, ya que los cambios se guardarán automáticamente y podrían afectar el funcionamiento de tu aplicación web. Siempre es recomendable hacer una copia de seguridad de tus archivos antes de realizar cambios importantes.

[Edit and save files in a workspace](https://developer.chrome.com/docs/devtools/workspaces)

## 11. Simular una ventana móvil

El **Device Mode** es útil para saber de manera aproximada cuál será el aspecto y el rendimiento de tu página en un dispositivo móvil.

Device Mode es el nombre de un conjunto variado de funciones en Chrome DevTools que te ayudan a simular dispositivos móviles. Estas funciones incluyen:

- Simulación del viewport de un dispositivo móvil
- Limitación de la red
- Limitación de la CPU
- Simulación de la ubicación geográfica
- Configuración de la orientación

![device-toolbar.png](https://i.postimg.cc/gcHnSK5t/11-device-mode.png)

- [Responsive](https://responsively.app/)
- [Polypane](https://polypane.app/)

## 12. Manejo de sensores

 **Performance ⚙️** nos da algunas opciones como:
 - **Network** que permiten manipular la velocidad del internet.
 - **CPU** nos permite hacer pruebas simulando diferentes dispositivos con poder de cómputo más o menos potentes.

![](https://i.postimg.cc/sXyh6fYb/12-performance-network.png)

A pesar de que Dev Tools nos da estas herramientas, se recomienda comprar dispositivos no tan caros para poder probar nuestras páginas.

Otra herramienta que nos ofrece Dev Tools es emular los sensores del dispositivo(geolocation, orietation, touch). Puedes acceder en la siguiente ruta:

- Customize and control DevTools (3 puntos)
- More tools / Sensors

![](https://i.postimg.cc/x1Y9hkJf/12-sensors.png)

Para saber las posiciones de orientación de un celular necesitamos escuchar el evento [DeviceOrientationEvent](https://developer.mozilla.org/en-US/docs/Web/API/DeviceOrientationEvent).

Usa la [API](https://developer.mozilla.org/es/docs/WebAPI/Using_geolocation#:~:text=La%20API%20de%20geolocalizaci%C3%B3n%20permite,para%20proporcionar%20informaci%C3%B3n%20de%20ubicaci%C3%B3n) de Geolocalización que tiene HTML5

## 13. Debugging JS con DevTools

Desde **Sources** activamos y escuchamos al evento **Click** desde **Event Listener Breakpoints > Mouse**. 

Esto lo que hace es generar un breakpoint que detiene la ejecución del código en la línea de la función asociada al evento que estamos "escuchando".

![](https://i.postimg.cc/HW2SrRB2/13-event-listener.png)

Podemos hacer pruebas con esta [Demo :3](https://googlechrome.github.io/devtools-samples/debug-js/get-started)

## 14. Reproduciendo y reparando un bug

En JavaScript **typeof** retorna el tipo de dato que tiene una variable.

El panel **Scope** te muestra las variables locales y globales actualmente definidas, junto con el valor de cada variable.

![](https://i.postimg.cc/g04JX3Br/14-bug-fix.png)

Otro ejemplo de uso: [[closures_scope-en-js#**7.** ¿Qué es un Closure?#Ámbito léxico]]

Ver en GitHub [¿Qué es un Closure?](https://github.com/aleroses/software-notes/blob/master/DW/2-intermedio/006.closures_scope-en-js/closures_scope-en-js.md#7-qu%C3%A9-es-un-closure)

📌 Para los que usan Visual Studio Code, dejo un artículo que nos muestra una extensión oficial (creada por Microsoft), para instalar **Debugger for Chrome**, para implementar mucha de la funcionalidad del browser dentro de nuestro editor de texto.

[Debugger for Chrome](https://code.visualstudio.com/blogs/2016/02/23/introducing-chrome-debugger-for-vs-code)

## 15. Nota: proyecto de la clase siguiente

El proyecto que se utiliza en la siguiente clase, **¡ya está disponible!**  
Lo puedes encontrar 👉 [aquí](https://devtools.glitch.me/network/getstarted.html)

## 16. ¿Cuándo utilizar Network en DevTools?

El panel Network es utilizado para asegurarse de que los recursos (HTML, imágenes, CSS, JS, entre otros) se descarguen o carguen como se esperaba.

Los casos de uso más comunes para el panel Network son:

- Asegurarse de que los recursos se estén cargando o descargando.
- Inspeccionar las propiedades de un recurso individual, como sus encabezados HTTP, contenido, tamaño, etc.

**Secciones de Network**:

1. **Name**: Nombre del archivo
2. **Status**: Estatus del HTTP. En este caso 200 significa OK (Todo bien)
3. **Type**: Tipo de archivo. Por ejemplo: document (HTML), stylesheet(CSS), JS, PNG, etc.
4. **Inialitator**: Cuál archivo solicitó a otro archivo. En este caso, el documento HTML solicitó a todos los demás archivos.
5. **Size**: Tamaño del archivo. Se muestra el tamaño no optimizado y optimizado por el navegador.
6. **Time**: Tiempo total que tarda en descargarse el archivo.
7. **Waterfall**: Tiempo (sección por sección) que le tomó al archivo descargarse.

Se muestra de la siguiente manera:

![](https://i.postimg.cc/mgxbpmF0/15-network.png)

**NOTA**: Los códigos de estado de respuesta HTTP indican si se ha completado satisfactoriamente una solicitud HTTP específica. Las respuestas se agrupan en cinco clases:

- Respuestas informativas (100–199),
- Respuestas satisfactorias (200–299),
- Redirecciones (300–399),
- Errores de los clientes (400–499),
- y errores de los servidores (500–599).

**Referencias**:

- [Códigos de estado de respuesta HTTP | MDN](https://developer.mozilla.org/es/docs/Web/HTTP/Status).
- [Inspect Network Activity In Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/network/).

## 17. Revisando detalles con Network

📌 Para ver más detalles como por ejemplo **Waterfall** solo dale clic derecho sobre **Name** y selecciona lo que necesites. Si eliges el icono ⚙️ **Network settings** podrás tener mas opciones.

![](https://i.postimg.cc/6qPGmgkk/17-network-details.png)

En este apartado podemos simulando conexiones de red:

- **Online** (Normal) 
- **Fast 3G**
- **Slow 3G**
- **Offline**
- **Custom**

Si mantenemos presionado el icono de **recargar página** en el navegador podremos elegir la opción **Vaciar caché y volver a cargar de manera forzada** para simular que se está abriendo la web por primera vez.

![](https://i.postimg.cc/xdq8WtRY/17-network-details2.png)

También podemos filtrar o bloquear archivos para que no se descarguen en el navegador.

**Ctrl + Shift + P** y escribimos **Show Request blocking** luego en el icono **+** y añadimos los archivos a bloquear `main.css`

![](https://i.postimg.cc/8kmzy7QT/17-lock-files.png)

Al recargar la página veremos que ese archivo no se cargó.

## 18. ¿Cuando utilizar la sección de Performance?

Para iniciar las pruebas podemos seguir los siguientes pasos:

- CPU: 4x slowdown

![](https://i.postimg.cc/8c7cZ8F5/18-performance-cpu-4x.png)

- Click the record button (Ctrl + E): 3 sec **Stop**

![](https://i.postimg.cc/XJ0t29py/18-performance-record.png)

En la parte inferior vemos un resumen del diagnóstico (summary): Si ves una línea roja, índica problemas.

![](https://i.postimg.cc/JzMqdKq8/18-performance-summary.png)

Además de Summary también existen:

- Bottom-UP
- Call Tree
- Event Log

Para ver más a detalle podemos ver en la siguiente sección: **Frames** y **Main** (con la rueda del mouse puedes ampliar)

![](https://i.postimg.cc/MpTrZqcH/18-performance-details.png)

Si le doy clic a algo que me interese de **Main**  puedo revisar en la parte inferior **Summary** para ver los detalles de la selección hecha.

![](https://i.postimg.cc/ZnjtgHQM/18-performance-main-details.png)

📌 _Idle_ es el tiempo muerto, donde ya la página terminó de realizar todos los pasos anteriores. Una página bien optimizada tendrá un _Idle_ mucho más grande en relación con los otros parámetros en la pestaña de _Summary_. Puede ser hasta más de un 95% mayor que el resto de los parámetros.

Además, si seleccionamos algún archivo con un pin en rojo 🔻en **Summary** veremos el archivo que nos está dando problemas: Ejemplo `app.js 71`.

![](https://i.postimg.cc/9XwLnJ6R/18-performance-main-file.png)

Si le damos clic al archivo nos mostrará todo el código, incluido el tiempo en que tarde en ejecutarse cada línea.

![](https://i.postimg.cc/kX3P1VpC/18-performance-debugging.png)

Las líneas más amarillas son las que se tardan más en ejecutarse.

**Recuerden:** Es una buena práctica generar 60 fps (frame por segundo)

[Janky Animation](https://googlechrome.github.io/devtools-samples/jank/)

### Reto: Comentario de un estudiante

**Conclusión sobre el reto** Bueno, según lo que he podido investigar (corregidme si estoy equivocado) es que el problema está en la forma en que obtiene una nueva posición para el elemento.

**_Algoritmo no optimizado_**

```js
var pos = m.classList.contains('down') ? m.offsetTop + distance : m.offsetTop - distance;
```

Aquí podemos observar que obtiene la posición del elemento con respecto al contenedor más cercano en posición relativa (en este caso body) y esto lo hace para cada iteración y cada elemento teniendo que cada vez volver a consultar esa posición para generar una nueva.

**_Algoritmo optimizado_**

```js
var pos = parseInt(m.style.top.slice(0, m.style.top.indexOf('px'))); m.classList.contains('down') ? pos += distance : pos -= distance;
```

Aquí para obtener la posición lee el estilo top anterior del elemento y a partir de ese genera una nueva posición.

La diferencia es que el primer algoritmo (offsetTop) consume mucho más recursos ya que debe consultar del DOM en cada iteración (es una nueva operación para cada elemento y cada iteración), mientras que con el segundo algoritmo (style.top) solamente consulta la posición anterior del estilo almacenado (no debe hacer una nueva operación).

### Reto: Otro comentario

Creo que lo solucione, en la línea 65 (Dado que la línea que marca el Performance es la 95 que llama a la función **app.update** en la línea 62)

Hay un condicional que dice: `if (!app.optimize)` y en la línea 32: `optimize = false;` al borrar el negar `(!)` se optimiza.

---

Hola @JuanGalvis, como tú dices, si le quitas la negación a la condición se optimiza porque por defecto esta expresión `app.optimize` tiene como valor `false`. Este valor se cambia cada vez que haces clic en el botón “_Optimize_” al igual que su texto, pasando de “_Optimize_” a “_Un-Optimize_”.

![](https://i.postimg.cc/MK6075mj/18-reto-img1.jpg)

Entonces al cambiar la condición, por defecto estás entrando en el código de la condición que está optimizado.

![](https://i.postimg.cc/Hx0558J2/18-reto-img2.png)

Y esto te llevaría a un error visual en cuanto al texto del botón porque si tú cambias la condición y le das clic al botón aunque este diga “_Optimize_” no optimizaría el código, sino todo lo contrario.

👀 Observando un poco más el código con las herramientas del navegador, creo que el error se encuentra en la línea 71.

![](https://i.postimg.cc/qvt3w5hg/18-reto-img3.jpg)

Se puede observar que debajo de la función `app.update` se están están ejecutando otras cosas. **Recalculate Style** y **Layout** ambas con un triángulo rojo indicando que podemos estar haciendo algo mal en el código. Le hago clic a “_Recalculate Style_” y aparece:

- Un warning ⚠️ que dice: _Forced reflow is a likely performance bottleneck_
- _Recalculation forced_ – `app.js:71`
- _First invalidated_ – `app.js:70`

Pero, ¿qué es **Recalculate Style** y **Layout**? 🤔

Para mostrar un _frame_ en la pantalla el navegador sigue una serie de pasos:

![](https://i.postimg.cc/L4Ngppjn/18-reto-img4.jpg)

- **Recalculate Style**: El paso de combinar el DOM y el CSSOM obteniendo así el _Render Tree_.
- **Layout** (o también llamado _++Reflow++_): El paso que hace el navegador para averiguar el tamaño y las posiciones de los elementos en la página.

A veces se puede forzar al navegador a realizar el _layout_ de manera anticipada con JavaScript. A esto se le denomina _**Forced synchronous layout**_. Y eso es lo que le está pasando a este código.

En la línea 70:

```js
m.style.top = pos + 'px';
```

En JavaScript se está cambiando el estilo de la imagen, en este caso la posición top.

En la línea 71:

```js
if (m.offsetTop === 0) {
```

Con `m.offsetTop` se está pidiendo conocer el valor de esa propiedad del elemento para poder hacer la comparación.

Si en la línea anterior (70) no se hace el cambio de estilo no habría problema porque se leería el valor del frame anterior pero al cambiar el estilo, el cambio hace que el navegador invalide ❌ todo lo que tenía registrado y deba actualizar ✅ los estilos (_Recalculate style_) y por lo tanto, ejecutar el _layout_ para poder devolver el _offsetTop_ correcto.

En otras palabras, esto lo hace porque al cambiar el estilo de la imagen y luego preguntar cual es la posición de la imagen el navegador no sabe si la posición ha cambiado y decide volver a ejecutar el paso de _layout_ para poder obtener su posición.

Y como está en un ciclo 🔄, estás operaciones se están continuamente repitiendo. De ahí el warning: “_Forced reflow is a likely performance bottleneck_”.

Para evitar esto se recomienda:

- 1️⃣ Primero ++leer++ los estilos (ejemplo de leer: element.width)
- 2️⃣ Y luego ++escribirlos++ (ejemplo de escribir: element.width = '100px')

En la solución del código optimizado lo que hacen es añadir a la variable `pos` la posición de la imagen y es esta variable la que utilizan en la condición. Lo que consiguen con esto es:

- Que el navegador no tenga que estar averiguando en varias líneas del código que posición tiene la imagen.
- Que no se fuerce el _Layout_ ya que en la línea anterior a la condición se sigue cambiando el estilo de la imagen.

Y si haces trabajar menos al navegador, el rendimiento de la página mejorará 💪.

En el enlace que puso el profesor también se menciona que el código se podría optimizar aún más si se utilizaran propiedades (_transform_ y _opacity_) que sólo afecten al último paso (_Composite_).

En general, con lo que me quedo es que las propiedades que cambiamos o leemos en JavaScript y dónde lo hacemos afectan al rendimiento 😅.

Enlaces recomendados:

- [El que puso el profesor](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance)
- [Y este que habla en profundidad sobre el layout](https://developers.google.com/web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing)

## 19. Auditoría en mobile: Lighthouse

En esta sección elegimos **Mobile**

![](https://i.postimg.cc/9f5v1zXS/19-lighthouse.png)

![](https://i.postimg.cc/N0sZZST7/19-analyze.png)

![](https://i.postimg.cc/1XwW8rw3/19-result.png)

Puedes darle clic a los resultados para ver que podemos mejorar.

- [Preogressive Web App](https://developers.google.com/codelabs/pwa-training/pwa03--going-offline?hl=es#0)
- [Accessibility](https://web.dev/articles/accessibility)

## 20. Auditoría en desktop: Lighthouse

En el icono de refrescar página, lo mantenemos seleccionado y elegimos **Vaciar caché y volver a cargar de manera forzada**.

Ahora en los **Lighthouse** elegimos **Desktop**

## 21. Cierre de curso

Tomar examen…

## 22. Contenido Bonus: PWA

Las Progressive Web Apps (PWAs) son aplicaciones web que combinan lo mejor de las páginas web y las aplicaciones móviles. La idea principal detrás de las PWAs es ofrecer una experiencia similar a la de una aplicación nativa, pero utilizando tecnologías web. 

A continuación, te explico de manera sencilla qué son y cómo funcionan:

### Qué son las Progressive Web Apps

1. **Aplicaciones Web Mejoradas**: Son sitios web o páginas web que se comportan como aplicaciones móviles.
2. **Experiencia de Usuario**: Ofrecen una experiencia rápida, fiable y atractiva, similar a las aplicaciones nativas.
3. **Instalación Opcional**: Pueden instalarse en el dispositivo del usuario sin necesidad de pasar por una tienda de aplicaciones como Google Play o App Store.
4. **Multiplataforma**: Funcionan en cualquier dispositivo con un navegador moderno, sin importar el sistema operativo.

### Cómo Funcionan las Progressive Web Apps

1. **Service Workers**: Este es un componente clave que permite que las PWAs funcionen offline o con conexiones inestables. Los Service Workers son scripts que el navegador ejecuta en segundo plano para manejar caché y solicitudes de red, mejorando la velocidad y la capacidad de trabajo sin conexión.
2. **Manifiesto Web (Web App Manifest)**: Es un archivo JSON que proporciona información sobre la aplicación (nombre, iconos, tema de color, etc.) y cómo debería comportarse cuando se "instala" en el dispositivo del usuario.
3. **HTTPS**: Las PWAs deben ser servidas a través de HTTPS para garantizar que la comunicación entre el servidor y el cliente sea segura.
4. **Aplicación Progresiva**: La "progresividad" significa que las PWAs funcionan para todos los usuarios, sin importar el navegador, ya que están construidas con principios de mejora progresiva. Esto significa que utilizan funciones del navegador que son soportadas por todos y luego añaden funcionalidades adicionales para los navegadores más avanzados.

### Para Qué Sirven las Progressive Web Apps

1. **Accesibilidad Sin Conexión**: Permiten a los usuarios acceder a contenido incluso cuando no tienen conexión a Internet, gracias a los Service Workers.
2. **Rendimiento Mejorado**: Las PWAs suelen ser más rápidas porque cargan desde la caché en lugar de depender completamente de la red.
3. **Experiencia de Usuario Enriquecida**: Ofrecen notificaciones push, pantalla completa, y pueden ser agregadas al inicio del dispositivo, mejorando la interacción del usuario.
4. **Menor Consumo de Recursos**: Ocupan menos espacio y consumen menos recursos del dispositivo comparado con las aplicaciones nativas.
5. **Desarrollo Simplificado**: Los desarrolladores pueden crear una única aplicación que funciona en múltiples plataformas sin necesidad de desarrollar versiones separadas para iOS, Android, etc.

### Ejemplos de Uso

- **E-commerce**: Tiendas online como AliExpress y Flipkart han implementado PWAs para mejorar la experiencia de compra.
- **Medios y Noticias**: Periódicos y sitios de noticias como The Washington Post y Financial Times usan PWAs para ofrecer acceso rápido y offline a sus artículos.
- **Redes Sociales**: Twitter Lite es una versión PWA que ofrece una experiencia de usuario rápida y que consume menos datos.

En resumen, las Progressive Web Apps son una forma moderna y eficiente de ofrecer aplicaciones web con todas las ventajas de las aplicaciones nativas, sin los inconvenientes de instalación y actualización a través de las tiendas de aplicaciones tradicionales.

## Funcionalidades útiles de Chrome devtools no cubiertas en el curso

En este post te voy a mostrar algunas funcionalidades que posee Chrome DevTools y que no fueron cubiertas en el curso.

### 💻 **Variables $1 al $4**

En el curso vimos como podemos usar **$0** para acceder al actual elemento seleccionado en **Elements**, pero adicionalmente existen otros _shortcuts_ como **$1**, **$2**, **$3**, **$4**. En estas variables el devtools guardará los últimos 4 elementos que selecciones en el tab **Elements**.

### 🔍 **Shortcuts para querySelector y querySelectorAll**

Imagina que quieres saber cuantos botones hay en tu HTML, puedes usar `querySelectorAll` para averiguarlo:

```js
var buttons = document.querySelectorAll('button');
console.log(buttons.length)
// muestra el total de elementos
```

Gracias a los DevTools puedes rápidamente reemplazar esta función por el doble dólar **`$$`**

```js
var buttons = $$('button');
console.log(buttons.length)
// muestra el total de elementos
```

Otro ejemplo:

![](https://i.postimg.cc/wBDHRyVS/vs-query-Selector-All.png)

Tener en cuenta que **`$$`** al ser una utilidad del DevTools retornará un arreglo, mientras que `querySelectorAll` retorna un **NodeList**. Pueden comprobarlo con el siguiente código:

```js
var buttons = $$('button');
Array.isArray(buttons) // retorna true

// 
var buttons = document.querySelectorAll('button');
console.log(buttons) // retorna false
```

Para el caso de `querySelector`, su alias es **`$`** y también es una función a la que debemos pasarle un selector, ambas funciones retornan un elemento del DOM y no hay un cambio en el tipo de dato como en `querySelectorAll`

**Tener en cuenta que al ser variables globales pueden ser reemplazadas fácilmente, por ejemplo si tienes jQuery en tu HTML el **`$`** será jQuery y no querySelector**

### ✏️ **Copiar una variable**

Vamos a suponer que tenemos una función que tras realizar una llamada **http** retorna un objeto que representa la información de un usuario.

```js
function fetchUser() {
   var user = {
  	id: 1,
	name: 'Eduardo',
	age: 33,
	country: 'Peru',
	salary: 100
   };
  return user;
}
```

Ahora imagina que necesitas todo ese objeto para pegarlo en otra herramienta y hacer algún proceso con esa información, lo normal sería hacer un `console.log` al objeto, seleccionarlo y copiarlo. !Aburrido! 

DevTools te ahorra ese proceso con su función **copy**

```js
function fetchUser() {
   var user = {
  	id: 1,
	name: 'Eduardo',
	age: 33,
	country: 'Peru',
	salary: 100
   };
  
  copy(user) // ahora tienes este objeto en tu porta papeles
  return user;
}
```

Listo, cuando ejecutes la función podrás hacer `Ctrl/cmd + V` y pegar el objeto en cualquier lado.

### 🕵️ **Seleccionar elementos vía código con inspect**

Buscar y seleccionar un elemento es muy simple con DevTools, simplemente haces clic en el icono de la flecha con el cuadradito (`Ctrl + Shift + C`) y luego vas al HTML y haces clic sobre el elemento que deseas, fácil. Pero hay una manera _fancy_ de hacerlo desde código gracias al método **inspect**.  
Este método acepta como parámetro un elemento del DOM.

```js
var button = document.querySelector('#my-button');
inspect(button);
```

Al ejecutarse la función inspect automáticamente, el DevTools cambiará al tab **Elements** y te mostrará el elemento que corresponda al selector **my-button**.

### 👀 **Monitorear una función**

¿Heredaste un código larguísimo y difícil de entender? ¿Las funciones y variables tienen nombres de letras como **x**, **z**? ¿Estás leyendo esto con voz de vendedor de teleferia? No te preocupes, con la función **monitor** DevTools te avisará cuando alguna función de tu código ha sido llamada.

En el siguiente código veremos a una función que retorna un simple objeto

```js
function fetchUser() {
   var user = {
    id: 1,
    name: 'Eduardo',
    age: 33,
    country: 'Peru',
    salary: 100
   };
  return user;
}
```

Si deseo que los DevTools me avise cada vez que se ha ejecutado la función solo debo hacer lo siguiente:

```js
monitor(fetchUser);
// Ejecutamos la función
fetchUser();
// Nos aparecerá el siguiente mensaje:
// function fetchUser called
```

### 📷 **Tomar screenshots**

Quieres pasarle un screenshot a alguien de un elemento del DOM específico. Pues simple, selecciono el elemento del DOM usando el DevTools, y luego presiono `Ctrl + Shift + P` se abrirá un modal con un listado de comandos de acciones del DevTools, escribimos “capture node screenshot” y automáticamente se guardará la imagen del nodo seleccionado. Adicionalmente, se puede generar screenshot de toda la pantalla o incluso dar la opción de seleccionar una parte en específico.

![](https://i.postimg.cc/KvZsbKw0/capture-node-screenshot.png)

Algo así:

![](https://i.postimg.cc/J7BBhPVn/devtools-capture-screenshot.gif)

## 🔥 Examen

<details>
  <summary>Haz clic para ver los resultados 👀👇</summary>
  <br/>

1. ¿Qué tipo de interacción podemos tener en la sección de Elements?

	- ✅ Manipulación de nuestro HTML.

2. ¿Cuáles son los navegadores que tienen herramientas para desarrolladores?

	- ✅ Todos los navegadores tienen herramientas para desarrolladores.

3. ¿Cómo podría visualizar la paleta de colores que mi proyecto está utilizando?

	- ✅ Desde la sección de estilos, al tener un elemento que tenga aplicado algún color, dándole clic al cuadro de color que aparece ahí, tendremos la opción de Page colors que hace referencia a la paleta de colores del proyecto.

4. Si tengo un error en mi código que se dispara al momento de mandar llamar una función que está ligada a un botón, ¿cómo podría llegar a esa función para comenzar a debuggear el código?

	- ✅ Tendríamos que comenzar con el evento de click en ese botón.

5. Si yo NO tengo la sección de Animación en mi DevTools, ¿Cómo puedo visualizarla?

	- ✅ En la parte de menú de tu devtools, tengo que ir a más herramientas “More Tools”, y ahí buscar por Animaciones.

6. ¿Si en mi proyecto estoy utilizando un preprocesador de css como “Stylus”, y utilizo DevTools como IDE, puedo seguir trabajando desde ahí con Stylus?

	- ✅ Claro, DevTools, te dejará trabajar con todos los preprocesadores de CSS.

7. ¿Qué es el JS Path que obtenemos de cada elemento de HTML?

	- ✅ Es la selección que hacemos a un nodo o elemento del DOM específico con JS

8. ¿Dónde puedo ver si mis elementos de HTML tienen algún estado de CSS?

	- ✅ mal No se puede, porque tienen primero que activar el estado.
	-  Eso es algo que solo se puede ver en Firefox.
	- ✅ mal Desde la sección de estilos, en el icono de :hov
	- Seleccionando ese elemento y viendo sus estilos.

9. ¿Para qué utilizamos “Network” en DevTools?

	- ✅ Esto nos sirve para poder ver ¿qué archivos y assets se están descargando, el estatus, el peso y tiempo de descarga de los mismos?

10. ¿Cómo podría cargar mi proyecto desde local, para comenzar a guardar los cambios desde DevTools?

	- ✅ Directamente desde la sección de sources seleccionamos “Filesystem” y “agregar un folder a mi espacio de trabajo”

11. ¿Cuál es la sección en la que puedo tener visibilidad del todo el código que no estoy utilizando en un proyecto?

	- ✅ Desde la sección de “Coverage” yo puedo tener visibilidad del código que está en mi proyecto, pero no es necesario porque no lo utilizo.

12. ¿De qué forma puedo buscar palabras específicas en mi documento html, desde el inspector de elementos?

	- ✅ Presionando “comand/ctrl + F” desde la casilla de Elements

13. ¿Para qué puedo utilizar el `$0` en la consola de DevTools?

	- ✅ Me sirve para ver cual es el elemento de HTML que estoy seleccionando.

14. ¿Cuál es la forma más rápida de generar sombras a mis elementos de html?

	- ✅ Desde la sección de estilos, al momento de estar modificando los estilos de algún elemento, tendremos un icono de 3 puntos que hace referencia a un menú, ahí encontraremos la opción para poder agregar sombras a elementos y texto.

15. ¿Cuáles son las estrategias que existen para poder trabajar proyectos responsive?

	- ✅ Por viewport de dispositivo, o por diseño.

</details>

👈👀
👇
📌
✅