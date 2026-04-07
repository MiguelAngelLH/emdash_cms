# Plantillas EmDash: explicacion, utilidad y alcance

## Que son las plantillas EmDash

Las plantillas EmDash son proyectos base ya preparados para crear sitios web usando EmDash CMS.

No son solamente ejemplos visuales. Tambien funcionan como bases de arranque que ya incluyen:

- estructura del proyecto
- configuracion de Astro y EmDash
- paginas iniciales
- componentes reutilizables
- contenido de demostracion
- scripts para desarrollo y compilacion

Su objetivo es permitir que una persona pueda copiar una plantilla, instalar dependencias, inicializar el contenido y comenzar a trabajar sobre una base funcional desde el primer momento.

## Para que sirven

Las plantillas EmDash sirven para:

1. Crear un sitio nuevo mas rapido.
2. Aprender como se integra EmDash dentro de Astro.
3. Tener una base funcional con contenido de ejemplo.
4. Evitar comenzar un proyecto desde cero.
5. Reutilizar una estructura ya pensada para un tipo especifico de sitio.

En vez de construir manualmente todas las paginas, estilos, seeds y configuraciones, las plantillas entregan una base lista para adaptarse.

## Que incluyen

Cada plantilla suele incluir estos elementos:

- archivos de paginas en `src/pages`
- componentes en `src/components`
- layouts en `src/layouts`
- configuracion de carga de contenido en `src/live.config.ts`
- un archivo seed con contenido demo en `seed/seed.json`
- configuracion general del proyecto en `astro.config.mjs`
- dependencias y scripts en `package.json`
- configuracion TypeScript en `tsconfig.json`

Esto permite que, al iniciar la plantilla, el sitio no este vacio, sino que tenga contenido real para probar vistas, rutas y panel admin.

## Plantillas disponibles

### Blog

La plantilla Blog esta pensada para sitios editoriales.

Sirve para:

- blogs personales
- revistas digitales
- sitios de articulos
- paginas con categorias y etiquetas

Caracteristicas principales:

- articulo destacado en la pagina principal
- cuadricula de publicaciones
- categorias y etiquetas
- buscador de texto completo
- RSS
- SEO y JSON-LD
- modo oscuro y claro

### Marketing

La plantilla Marketing esta pensada para sitios de promocion de productos o servicios.

Sirve para:

- landing pages
- sitios corporativos pequenos
- promocion de servicios
- captacion de clientes potenciales

Caracteristicas principales:

- bloque hero
- secciones de caracteristicas
- testimonios
- precios
- preguntas frecuentes
- formulario de contacto con validacion
- SEO y JSON-LD
- modo oscuro y claro

### Cartera o Portfolio

La plantilla Portfolio esta pensada para mostrar trabajos creativos o proyectos.

Sirve para:

- portafolios de diseno
- estudios creativos
- desarrolladores freelance
- fotografos
- showcases de proyectos

Caracteristicas principales:

- cuadricula de proyectos
- efectos hover
- filtrado por etiquetas
- pagina individual por proyecto
- galeria
- pagina de contacto
- RSS
- SEO y JSON-LD
- modo oscuro y claro

## Que papel cumple el archivo seed

Cada plantilla incluye un archivo seed con contenido de demostracion.

Ese archivo sirve para poblar automaticamente la base de datos con informacion inicial, por ejemplo:

- paginas
- entradas o proyectos
- categorias
- etiquetas
- menus
- configuracion del sitio
- imagenes o referencias a medios

Gracias a esto, cuando se inicializa la plantilla, el sitio ya muestra contenido real y no aparece vacio.

## Alcance de las plantillas EmDash

El alcance de estas plantillas es mayor que el de una simple maqueta visual.

Las plantillas sirven como:

- base de desarrollo
- ejemplo funcional de integracion con EmDash
- punto de partida para proyectos reales
- referencia tecnica dentro del repositorio
- base de pruebas para comprobar que el CMS funciona

Esto significa que una plantilla puede usarse tanto para aprender como para construir encima de ella un sitio real.

## Variantes disponibles

Cada plantilla tiene dos variantes principales.

### 1. Variante Node.js

Ubicaciones como:

- `templates/blog`
- `templates/marketing`
- `templates/portfolio`

Estas usan:

- SQLite
- almacenamiento local de archivos

Son la opcion mas simple para desarrollo local y pruebas rapidas.

### 2. Variante Cloudflare

Ubicaciones como:

- `templates/blog-cloudflare`
- `templates/marketing-cloudflare`
- `templates/portfolio-cloudflare`

Estas usan:

- D1
- R2
- configuracion para Cloudflare

Son utiles cuando el sitio se quiere ejecutar o desplegar sobre infraestructura de Cloudflare.

## Como se usan

El flujo general de uso de una plantilla es:

1. Copiar la plantilla elegida.
2. Entrar a la carpeta copiada.
3. Instalar dependencias.
4. Inicializar la base de datos y cargar contenido demo.
5. Arrancar el servidor de desarrollo.

Ejemplo conceptual:

```powershell
cp -r templates/blog my-site
cd my-site
corepack pnpm install
corepack pnpm bootstrap
corepack pnpm dev
```

Con eso se obtiene:

- el sitio funcionando localmente
- el contenido inicial cargado
- el panel admin disponible

## Que significa la parte de sincronizacion

En el repositorio, algunas plantillas y demos comparten gran parte de su codigo.

Por eso existen scripts de sincronizacion como:

- `scripts/sync-cloudflare-templates.sh`
- `scripts/sync-blog-demos.sh`

Estos scripts sirven para copiar cambios desde una plantilla base hacia otras variantes o demos relacionados.

Su utilidad es evitar duplicar trabajo y mantener consistencia entre versiones parecidas del mismo sitio.

## Que significa la parte de capturas de pantalla

Las plantillas tambien tienen un sistema automatizado para generar screenshots.

Eso sirve para:

- actualizar las imagenes del README
- documentar el aspecto visual de cada plantilla
- mantener una galeria visual consistente

El script levanta cada plantilla, toma capturas en escritorio y movil, en modo claro y oscuro, y actualiza la carpeta `latest`.

## Que significa agregar una nueva plantilla

La seccion de agregar una nueva plantilla esta pensada para personas que contribuyen al repositorio.

Explica como:

- crear una nueva plantilla base
- incluir un seed
- agregar scripts y configuracion
- crear su variante Cloudflare
- registrarla en los scripts de sincronizacion
- agregarla al sistema de screenshots

Esto no es parte del uso normal de un usuario final, sino del mantenimiento y extension del proyecto.

## Como se prueban las plantillas

Las plantillas no solo se revisan visualmente, tambien se someten a pruebas de humo.

Estas pruebas verifican que:

- el seed se lea correctamente
- el seed se aplique sin errores
- la base de datos resultante quede sana tras la inicializacion

Eso es importante porque confirma que la plantilla realmente funciona y no es solo una maqueta incompleta.

## Conclusion

Las plantillas EmDash son proyectos base listos para usar que permiten crear sitios web administrables de forma mucho mas rapida.

Su principal utilidad es ofrecer una base funcional con:

- frontend inicial
- contenido demo
- integracion CMS
- panel admin
- configuracion lista para desarrollo

En resumen, las plantillas EmDash sirven para arrancar rapido, aprender la herramienta, reutilizar estructuras funcionales y reducir el trabajo inicial al construir un sitio con EmDash.