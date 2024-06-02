# goldmark-figures FORK

[Original](https://github.com/mdigger/goldmark-figures)

Este repositorio es un sencillo fork de una extensión de Goldmark para renderizar
imágenes con el elemento HTML `<figure>` con un `<figcaption>` de la descripción,
en lugar del comportamiento habitual de Goldmark, que es ponerlo como `alt` en la
`<image>`

Tomemos por ejemplo el siguiente código Markdown:

```markdown
![Un texto alternativo](/image.png)
```

Normalmente se mostraría en HTML como:

```html
<img src="image.png" alt="Un texto alternativo">
```

Pero con esta extensión se renderiza tal que:

```html
<figure>
	<img src="image.png" alt="Un texto alternativo" title="Un texto alternativo">
	<figcaption>Un texto alternativo</figcaption>
</figure>
```

## Instalación

```bash
go get github.com/arielcostas/goldmark-figures
```

## Uso

Al instanciar Goldmark, añadir la extensión:

```go
package main

import (
	gmf "github.com/arielcostas/goldmark-figures"
	"github.com/yuin/goldmark"
)

var parser goldmark.Markdown = goldmark.New(
	goldmark.WithExtensions(gmf.Extension),
)
```

## Licencia

El código original de [mdigger](https://github.com/mdigger/goldmark-figures) está
bajo la licencia MIT. Este fork también lo está.