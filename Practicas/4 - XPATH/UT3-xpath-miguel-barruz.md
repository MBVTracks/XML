1. Todos los autores del documento.

**Solución:**
```
libreria/libro/autor
```
**Resultado:**
```xml
<autor>Karlos Arguiñano</autor>
<autor>Carlos Montero</autor>
<autor>James McGovern</autor>
<autor>Per Bothner</autor>
<autor>Kurt Cagle</autor>
<autor>James Linn</autor>
<autor>Vaidyanathan Nagarajan</autor>
<autor>Erik T. Ray</autor>
```
2. Todos los títulos del documento.

**Solución:**
```
/libreria//(libro/titulo|seccion/capitulo/titulo)|//libro/capitulo/titulo
```
**Resultado:**
```xml
<titulo idioma="es">1000 recetas de oro</titulo>
<titulo idioma="es">El desorden que dejas</titulo>
<titulo idioma="en">XQuery Kick Start</titulo>
<titulo>XML The foundation of XQuery</titulo>
<titulo>Understanding the XPath specification</titulo>
<titulo idioma="en">Learning XML</titulo>
<titulo>Introduction</titulo>
<titulo>Markup and Core Concepts</titulo>
```
3. Todos los títulos de un capítulo del documento.

**Solución:**
```
/libreria//(seccion/capitulo/titulo|libro/capitulo/titulo)
```
**Resultado:**
```xml
<titulo>XML The foundation of XQuery</titulo>
<titulo>Understanding the XPath specification</titulo>
<titulo>Introduction</titulo>
<titulo>Markup and Core Concepts</titulo>
```
4. Todos los títulos de un libro del documento.

**Solución:**
```
/libreria/libro/titulo
```
**Resultado:**
```xml
<titulo idioma="es">1000 recetas de oro</titulo>
<titulo idioma="es">El desorden que dejas</titulo>
<titulo idioma="en">XQuery Kick Start</titulo>
<titulo idioma="en">Learning XML</titulo>
```
5. Todos los elementos de un capítulo.

**Solución:**
```
/libreria/libro/seccion/capitulo|//libro/capitulo
```
**Resultado:**
```xml
<titulo>XML The foundation of XQuery</titulo>
<paginas>14</paginas>
<titulo>Understanding the XPath specification</titulo>
<paginas>35</paginas>
<titulo>Introduction</titulo>
<paginas>24</paginas>
<titulo>Markup and Core Concepts</titulo>
<paginas>34</paginas>
```
6. Todos los elementos de un capítulo en una sección.

**Solución:**
```
/libreria/libro/seccion/capitulo
```
**Resultado:**
```xml
<titulo>XML The foundation of XQuery</titulo>
<paginas>14</paginas>
<titulo>Understanding the XPath specification</titulo>
<paginas>35</paginas>
```
7. Todos los elementos de un capítulo que no están en una sección.

**Solución:**
```
/libreria/libro/capitulo
```
**Resultado:**
```xml
<capitulo num="1">
  <titulo>Introduction</titulo>
  <paginas>24</paginas>
</capitulo>
<capitulo num="2">
  <titulo>Markup and Core Concepts</titulo>
  <paginas>34</paginas>
</capitulo>
```
8.   Títulos de libros que tienen un capítulo 1.


**Solución:**
```
/libreria/libro/seccion/capitulo/../../titulo|//libro/capitulo/../titulo
```
**Resultado:**
```xml
XQuery Kick Start
Learning XML
```

9.  Todos los atributos del hijo del último libro.


**Solución:**
```
/libreria/libro/capitulo/@num|//libro[last()]/titulo/@idioma
```
**Resultado:**
```xml
idioma="en"
num="1"
num="2
```
10. El primer autor de cada libro.


**Solución:**
```
/libreria/libro/autor[position()=1]
```
**Resultado:**
```xml
<autor>Karlos Arguiñano</autor>
<autor>Carlos Montero</autor>
<autor>James McGovern</autor>
<autor>Erik T. Ray</autor>
```
11. El tercer libro con toda su información.


**Solución:**
```
/libreria/libro[position()=3]
```
**Resultado:**
```xml
<libro categoria="tecnología">
  <titulo idioma="en">XQuery Kick Start</titulo>
  <autor>James McGovern</autor>
  <autor>Per Bothner</autor>
  <autor>Kurt Cagle</autor>
  <autor>James Linn</autor>
  <autor>Vaidyanathan Nagarajan</autor>
  <seccion par="1">
    <capitulo num="1">
      <titulo>XML The foundation of XQuery</titulo>
      <paginas>14</paginas>
    </capitulo>
    <capitulo num="2">
      <titulo>Understanding the XPath specification</titulo>
      <paginas>35</paginas>
    </capitulo>
  </seccion>
  <anyo>2003</anyo>
  <precio>49.99</precio>
</libro>
```
12. Todos los elementos con atributos.


**Solución:**
```

```
**Resultado:**
```xml
<libro categoria="cocina">
  <titulo idioma="es">1000 recetas de oro</titulo>
  <autor>Karlos Arguiñano</autor>
  <anyo>2018</anyo>
  <precio>30.00</precio>
</libro>
<titulo idioma="es">1000 recetas de oro</titulo>
<libro categoria="novela">
  <titulo idioma="es">El desorden que dejas</titulo>
  <autor>Carlos Montero</autor>
  <anyo>2016</anyo>
  <precio>18.95</precio>
</libro>
<titulo idioma="es">El desorden que dejas</titulo>
<libro categoria="tecnología">
  <titulo idioma="en">XQuery Kick Start</titulo>
  <autor>James McGovern</autor>
  <autor>Per Bothner</autor>
  <autor>Kurt Cagle</autor>
  <autor>James Linn</autor>
  <autor>Vaidyanathan Nagarajan</autor>
  <seccion par="1">
    <capitulo num="1">
      <titulo>XML The foundation of XQuery</titulo>
      <paginas>14</paginas>
    </capitulo>
    <capitulo num="2">
      <titulo>Understanding the XPath specification</titulo>
      <paginas>35</paginas>
    </capitulo>
  </seccion>
  <anyo>2003</anyo>
  <precio>49.99</precio>
</libro>
<titulo idioma="en">XQuery Kick Start</titulo>
<seccion par="1">
  <capitulo num="1">
    <titulo>XML The foundation of XQuery</titulo>
    <paginas>14</paginas>
  </capitulo>
  <capitulo num="2">
    <titulo>Understanding the XPath specification</titulo>
    <paginas>35</paginas>
  </capitulo>
</seccion>
<capitulo num="1">
  <titulo>XML The foundation of XQuery</titulo>
  <paginas>14</paginas>
</capitulo>
<capitulo num="2">
  <titulo>Understanding the XPath specification</titulo>
  <paginas>35</paginas>
</capitulo>
<libro categoria="web" cubierta="tapa blanda">
  <titulo idioma="en">Learning XML</titulo>
  <autor>Erik T. Ray</autor>
  <capitulo num="1">
    <titulo>Introduction</titulo>
    <paginas>24</paginas>
  </capitulo>
  <capitulo num="2">
    <titulo>Markup and Core Concepts</titulo>
    <paginas>34</paginas>
  </capitulo>
  <anyo>2003</anyo>
  <precio>39.95</precio>
</libro>
<titulo idioma="en">Learning XML</titulo>
<capitulo num="1">
  <titulo>Introduction</titulo>
  <paginas>24</paginas>
</capitulo>
<capitulo num="2">
  <titulo>Markup and Core Concepts</titulo>
  <paginas>34</paginas>
</capitulo>
```