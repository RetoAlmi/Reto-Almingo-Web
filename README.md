
# ALMINGO Web

**ALMINGO** es la página web corporativa de la empresa, especializada en el desarrollo de software y aplicaciones. El sitio está diseñado para transmitir una imagen moderna, profesional y tecnológica mediante una estética oscura, una paleta de colores basada en tonos morados y tarjetas interactivas con efectos de iluminación y transiciones suaves.


## Tabla de Contenidos

  

* [Características y Diseño](#características-y-diseño)

* [Estructura del Sitio Web](#estructura-del-sitio-web)

* [Cabecera y Navegación](#cabecera-y-navegación)

* [Tecnologías Utilizadas](#tecnologías-utilizadas)

* [Instalación y Uso](#instalación-y-uso)

---


## Características y Diseño

*  **Identidad Visual Cohesiva:** Uso de fondos oscuros combinados con degradados en tonos morados (`linear-gradient(#43026e, #1b0127)`) y efectos de luz para resaltar los elementos clave.

*  **Arquitectura Basada en Tarjetas:** La información se organiza en tarjetas independientes para facilitar la lectura rápida y estructurada.

*  **Pequeñas interacciones en el CSS:** Animaciones fluidas al pasar el ratón (`:hover`), como elevación de tarjetas (`translateY`), efectos de zoom (`scale`) y enfoque selectivo mediante el selector `:has()`.

---
  

## Estructura del Sitio Web

### Cabecera y Navegación

Presente en la parte superior de todas las páginas para garantizar una navegación intuitiva. Incluye el logotipo, el nombre **ALMINGO**, el lema de la empresa (*"Desarrollo de software y aplicaciones"*) y el menú principal con acceso a:

*  **Home:** Página principal.

*  **Projects:** Catálogo de trabajos con menú desplegable hacia `#apps` y `#software`.

*  **Recommendations:** Reseñas de clientes.

*  **Trust us:** Prueba social y empresas colaboradoras.

*  **Login / Register:** Acceso y creación de cuentas de usuario.

  

---

  

### Inicio (`index.html`)

Funciona como la carta de presentación de la empresa. Permite al visitante comprender de un vistazo quiénes somos, nuestra misión, por qué elegirnos y nuestro stack tecnológico.

**Detalles técnicos:** 
 * Uso de listas desordenadas (`<ul>`) con iconos para mostrar las tecnologías (Java, Python, JavaScript, etc.).
 *  **Animación de tarjetas:** Elevación suave al pasar el cursor mediante `transition: transform 0.6s;` y `transform: translateY(-15px);`.
 *  **Botón "More projects":** Efecto de aumento con `transform: scale(1.1);`.

  

### Proyectos (`projects.html`)

Muestra trabajos reales para generar confianza y demostrar capacidades técnicas.

**Detalles técnicos:**
*  **Navegación interna:** Menú desplegable en la cabecera que dirige directamente a las secciones `#apps` o `#software` mediante anclas (`id`).
*  **Acciones por proyecto:**
* *  *Source Code:* Enlace externo (`target="_blank"`) hacia el repositorio en GitHub.
* *  *Website:* Acceso directo a la web del proyecto.
* *  *Download:* Descarga directa de ejecutables/instaladores (ej. `.exe` desde GitHub Releases).

  

### Recomendaciones (`recommendations.html`)

Sección de prueba social con valoraciones y opiniones de clientes satisfechos.

**Detalles técnicos:**

* Mantiene la estructura de tarjetas animadas.

* Cada tarjeta integra una fotografía de perfil circular (`border-radius: 50%`), una fila de imágenes de 5 estrellas y el testimonio del cliente.



### Confía en Nosotros (`trust-us.html`)

Diseñada para causar un alto impacto visual y respaldar la fiabilidad de la empresa, destacando que más de **50.000 empresas y usuarios** ya confían en ALMINGO.

**Detalles técnicos:**

*  **Efecto de enfoque en tarjetas:** Al pasar el cursor sobre una tarjeta, esta aumenta su tamaño y pasa al frente, mientras que el resto se oscurecen automáticamente usando CSS moderno (`:has()`):

```css
.compañia:hover {
transition:  0.1s;
transform:  scale(1.08);
z-index:  2;
}

.tarjetas:has(.compañia:hover) .compañia:not(:hover) {
filter:  brightness(0.7);
}
```

*  **Logotipos:** Contenedor inferior (`div.contenedorEmpresas`) con las marcas colaboradoras.



### Inicio de Sesión y Registro (`login.html` / `register.html`)

Páginas dedicadas a la autenticación y alta de nuevos usuarios en la plataforma.

**Detalles técnicos:**

*  **Estilos compartidos:** Ambas vistas reutilizan gran parte de las hojas de estilo CSS para mantener la coherencia visual (tonos morados, efectos de luz y formularios centrados).

*  **Accesibilidad y Usabilidad:** Formularios semánticos con asociación estricta entre etiquetas (`<label for="...">`) y campos de entrada (`<input id="...">`), además de opción para recordar sesión en el login.

---


## Tecnologías Utilizadas

*  **HTML5:** Estructura semántica de las páginas, formularios y navegación por anclas.
*  **CSS3:** Diseño responsivo, degradados lineales, transiciones y selectores avanzados (`:hover`, `:not()`, `:has()`).

---


## Instalación y Uso

Al tratarse de un proyecto web estático basado en HTML y CSS, no requiere compilación ni instalación de dependencias complejas:


1.  **Clona este repositorio:**

```bash
git clone https://github.com/tu-usuario/almingo-web.git
```

2.  **Accede a la carpeta del proyecto:**

```bash
cd almingo-web
```

3.  **Ejecuta la web:**

Abre el archivo `index.html` directamente en tu navegador web favorito (o utiliza una extensión como *Live Server* en VS Code).