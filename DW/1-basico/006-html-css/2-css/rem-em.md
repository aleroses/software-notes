# REM y EM

- REM y EM son medidas relativas.
- REM es relativa a la etiqueta `<html>` y de la propiedad `font-size`
- EM es relativa a su `<etiqueta> <contenedora> <body> <html>`

```html
<div class="contenedora">
  <a class="rem">REM</a>
  <a class="em">EM</a>
</div>
```

```css
html {
  /* Son lo mismo y vienen por defecto */
	font-size: 16px;
	font-size: 100%;
}

body {
  /* Son lo mismo y vienen por defecto */
	font-size: 16px;
	font-size: 100%;
}
```

```
```

* REM: Box Model
* EM: Font size

Extensión: Pixel to REM 
Alt + z convierte a rem