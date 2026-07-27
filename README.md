# Inteligente-Ahorro-IA-

## The core idea
Crear un cerebro digital que almacene almacena las formas de estrategia de ahorro más eficaces y te recomienda mediante un estudio personalizado propio tu propia estrategia financiera, teniendo asi toda la información para hacerle preguntas concretas financieras de los gastos e ingresos de soluciones a problemas así como análisis a posibles mejoras

## Esta idea surge a partir del Paper de Adrej Karpathy, trabajador de Anthrop\c y coofundador de OpenIA:

https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f

## Utilización
Como se menciona en el peper el uso habitual que se le da a la IA es darle una colección de archivos o distintos documentos. Esto funciona pero cada vez tienes que volver a empezar desde cero dándole el mismo contexto gastando Token, con este método nada se esta construyendo.

La propuesta que introduce Karpathy es crear una arquitectura que constantemente construya encima de esta y vaya actualizando páginas, revisando los temas, buscar datos que se contradice para solucionarlo o incluso ir mejorando el sistema.

Este nueva forma de trabajo hace que en lugar de que la IA relea tus documentos en cada pregunta, construye una wiki persistente una vez y la mantiene para siempre.

## Arquitectura de 3 capas
Esta arquitectura consta de 3 capas.

### CAPA 3: Fuentes Raw
Esta capa esta formada por los archivos brutos que nunca se modifican

### CAPA 2: La Wiki
Esta carpeta la creara la IA, actualizara y mantiene.

Cada archivo de la capa 3 lo sintetizara y crear paginas que le permitan tener esa información siempre a su disposición y relacionara la información entre si.

Tendrá un *Index.md* y un *log.md*

*Index.md* será como un índice de un libro, le dirá a la IA todo lo que hay en esta capa 2 y lo ordena. Cada página listada, resumen rápido de lo que muestra cada página, distintos conceptos, las fuentes...

Primero la IA leerá el Índice y luego vera los elementos importantes

*log.md* es el archivo donde guarda todo lo que ha ido haciendo todos lo que ha ido cambiando dentro de este cerebro teniendo un histórico de todo lo que se a realizado

### CAPA 1: El Esquema
mediante un Claude.md se le dirá a la IA como debe de trabajar

Claud.md tendrá el prom de:

- Conocer tus gustos a la hora de plasmar la información
- Conocer tu forma de trabajo
- Como utilizar la información
- Las reglas que debe de seguir
