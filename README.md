# Auditoria ASG y Refactorización Sostenible

# Indice
1. [Fase 1: Inventario y Dimension Ambiental (A)](#fase-1-inventario-y-dimension-ambiental-a)
2. [Fase 2: Dimension Social y Equidad (S)](#fase-2-dimension-social-y-equidad-s)
3. [Fase 3: Dimension de Gobernanza y Ética (G)](#fase-3-dimension-de-gobernanza-y-etica-g)
4. [Fase 4: Propuesta de Refactorizacion (Green Coding)](#fase-4-propuesta-de-refactorizacion-green-coding)

# INTRODUCCION
La empresa seleccionada para esta auditoría ha sido la página web de Neoterra Service, una compañía especializada en el desarrollo de granjas verticales automatizadas e inteligentes ubicadas en entornos urbanos. 

El enlace a la web es el siguiente:
https://www.neoterraservice.com/neoterra---soluciones.html 

El objetivo de esta auditoría ASG (Ambiental, Social y Gobernanza) es evaluar el impacto sostenible de la página web, detectando problemas relacionados con el rendimiento, accesibilidad y ética digital. Además, se plantearán propuestas de refactorización basadas en principios de Green Coding y desarrollo sostenible. 


# Fase 1: Inventario y Dimension AMbiental (A)

1. La huella de carbono estimada por vista de PageSpeed Insights es de un 81% de Rendimiento, 74% de Accesibilidad, 92% Prácticas recomendadas y 91% de SEO.

2. He entrado en un navegador de google y le he dado al F12 para ver el Network una vez allí he seleccionado desactivar el caché 
Luego le he dado al F5 y en la columna size le he dado click para que se ordene de mayor a menor.En las imagenes se puede ver como esta de menor a mayor y de mayor a menor ,ademas el tiempo,el tamaño,etc.

1. shared.rollup.js (523kB): libreria de JavaScript de dependencia
2. p_2x_d075c781870b.png (176kB): imagen de iconos sin optimizar
3. new_tab_page.js (277kB): libreria de JavaScript de dependencia

3. Sí, existe un consenso generalizado entre desarrolladores y expertos en tecnología de que la web sufre de inflación de software, un fenómeno donde las aplicaciones web son cada vez más pesadas, complejas y consumidoras de recursos, sin que esto se traduzca necesariamente en una mejor experiencia para el usuario fina

# Fase 2: Dimension Social y Equidad (S)

1. Para evaluar la accesibilidad se utiliza Lighthouse Accessibility y una revision manual basada en las pautas WCAG 2.2.
La puntuacion obtenida fue de un 74%, lo que indica que existen barreras importantes para determinados usuarios.
2. En el lighthouse ha detectado 3 errores de accesibilidad:

Problema 1: Las imagenes no tienen texto alternativo, por lo que un lector de pantalla no puede describirlas a personas con discapacidad visual.

Problema 2: El color de texto no tiene suficiente contraste con el fondo dificultando la lectura a personas con baja vision o daltonismo.

Problema 3: Los campos de formularios no tiene etiquetas asociadas, por lo que los lectores de pantalla no anuncian para que sirve cada campo.

# Fase 3: Dimension de Gobernanza y Ética (G)

# 3.1 Transparencia en las cookies
La pagina web muestra un aviso de cookies, aunque el sistema de acpetacion no resulta completamente transparente.
El usuario puede sentirse presionado a aceptar todas las cookies rápidamente, lo que se considera un posible “dark pattern” o patrón oscuro.

Una práctica más ética sería:

Permitir rechazar cookies con la misma facilidad que aceptarlas.
Explicar claramente qué datos se recopilan.
Diferenciar cookies esenciales y no esenciales.

# 3.2 Solicitud de datos

EL formulario de contacto solicita básicos como nombre y correo electrónico.

No se detectó una recopilación excesiva de información, aunque sería recomendable:

Solicitar únicamente datos estrictamente necesarios.
Informar claramente del tratamiento de datos.
Añadir políticas de privacidad más visibles y comprensibles.

# Fase 4: Propuesta de Refactorizacion (Green Coding)

4.1. Optimizacion de activos.

-Las imagenes actuales podrian convertirse a formatos como WebP o AVIF, que reducen significativamente el tamaño sin perder calidad visual.
Esto reduciría el tráfico de datos y el consumo energético.

- Actualmente muchos recursos se cargan desde el inicio aunque el usuario no los visualice
Se propone usar carga diferida:
<img src="imagen.webp" loading="lazy" alt="Cultivo vertical">

Ventajas:
- Menor tiempo de carga inicial
- Menor uso de ancho de banda
- Reduccion del consumo energetico

4.2. Reduccion de peticiones HTTP
Se recomienda:
- Eliminar scripts y librerias no utilizadas
- Minificar archivos CSS y JavaScript.
- Combinar archivos pequeños para reducir solicitudes.
- Aplazar scripts no críticos usando defer

Ejemplo:
<script src="app.js" defer></script>

4.3. Mejora de accesibilidad

Uso de HTML semantico
Se recomienda utilizar etiquetas semanticas:
<header>
<nav>
<main>
<section>
<footer>

Esto mejora:
- Accesibilidad.
- SEO.
- Compatibilidad con lectores de pantalla.

Mejora de formularios

Todos los campos deberían tener etiquetas asociadas:

<label for="email">Correo electrónico</label>
<input type="email" id="email">

# 4.4 Mejora ética y de gobernanza
Consentimiento transparente de cookies

Se propone implementar un sistema donde:

Rechazar cookies sea tan sencillo como aceptarlas.
Exista una explicación clara del uso de datos.
Se respeten las preferencias del usuario.

Simplificación de textos legales

Las políticas legales deberían redactarse de forma más clara y comprensible para cualquier usuario.

Esto mejora:

- La transparencia.
- La confianza.
- La sostenibilidad social.

# 4.5 Reflexion sobre la paradoja de Jevons

La paradoja de Jevons explica que una mejora de eficiencia puede provocar un aumento del consumo total.

Si la web se vuelve más rápida y eficiente, podría atraer a muchos más usuarios y aumentar nuevamente el consumo energético.

Para evitar este efecto se recomienda:

- Utilizar servidores alimentados con energías renovables.
- Mantener una optimización continua.
- Reducir recursos innecesarios incluso si aumenta el tráfico.
- Aplicar estrategias de caché eficientes.
- Monitorizar periódicamente el consumo digital.

# 5.Herramientas utilizadas
|Herramientas|Uso|
|:-----------|:-------|
|Lighthouuse|Rendimiento y accesibilidad|
|Chrome DevTools|Analisis de red y resursos|
|WCAG 2.2|Evaluacion de accesibilidad|
|Google Chrome|Inspeccion tecnica|

# 6.Conclusiones
La web analizada presenta un rendimiento aceptable, aunque todavía existen problemas relacionados con la sostenibilidad digital, como imágenes pesadas, falta de optimización y algunos errores de accesibilidad.

Las mejoras propuestas mediante técnicas de Green Coding permitirían reducir la huella de carbono digital, mejorar la experiencia de usuario y aumentar la accesibilidad y transparencia de la web.

Aplicar prácticas sostenibles en el desarrollo web ayuda a crear páginas más eficientes, accesibles y responsables con el medio ambiente.

