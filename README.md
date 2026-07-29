# Inteligente-Ahorro-IA-

## The core idea
Inteligente Ahorro IA es un proyecto cuyo objetivo es construir un asistente financiero personal capaz de aprender de forma continua sobre la situación económica del usuario y ofrecer recomendaciones de ahorro cada vez más precisas.

A diferencia de los asistentes tradicionales, que necesitan recibir el mismo contexto en cada conversación, este proyecto implementa una arquitectura de conocimiento persistente. La IA transforma documentos, datos y registros financieros en una base de conocimiento estructurada que evoluciona constantemente.

El resultado es un sistema que no solo responde preguntas, sino que construye un conocimiento financiero propio, permitiendo realizar análisis complejos, detectar oportunidades de ahorro y proponer estrategias personalizadas.

## Objetivos
Como se menciona en el peper el uso habitual que se le da a la IA es darle una colección de archivos o distintos documentos. Esto funciona pero cada vez tienes que volver a empezar desde cero dándole el mismo contexto gastando Token, con esta arquitectura el contexto se va construyendo mediante el uso, creando unos índices que ahorran token y mantiene la información sin modificaciones.

La propuesta que introduce Karpathy es crear una arquitectura que constantemente construya encima de esta y vaya actualizando páginas, revisando los temas, buscar datos que se contradice para solucionarlo o incluso ir mejorando el sistema.

## Funcionalidades

- Analizar gastos e ingresos
- Recomendar Estrategias de ahorro adaptadas a cada perfil
- Detectar oportunidades de mejoras financieras
- Encontrar patones de consumo
- Evaluar la evolución económica a corto, medio y largo plazo
- Mantener un conocimiento financiero permanente que mejora con el uso

## Arquitectura

El proyecto sigue una arquitectura de tres capas.

                 ┌──────────────────────┐
                 │     Claude.md        │
                 │ Reglas del sistema   │
                 └──────────▲───────────┘
                            │
                    CAPA 1 - Esquema
                            │
                            ▼
                 ┌──────────────────────┐
                 │       Wiki IA        │
                 │ conocimiento vivo    │
                 └──────────▲───────────┘
                            │
                    CAPA 2 - Wiki
                            │
                            ▼
                 ┌──────────────────────┐
                 │   Documentos Raw     │
                 │ datos originales     │
                 └──────────────────────┘
                    CAPA 3 - Fuentes

### CAPA 3: Fuentes Raw
Esta capa esta formada por los archivos brutos que nunca se modifican

### CAPA 2: La Wiki
Esta carpeta la creara la IA, actualizara y mantiene.

Cada archivo de la capa 3 lo sintetizara y crear paginas que le permitan tener esa información siempre a su disposición y relacionara la información entre si.

Tendrá un *Index.md* y un *log.md*

- *Index.md* será como un índice de un libro, le dirá a la IA todo lo que hay en esta capa 2 y lo ordena. Cada página listada, resumen rápido de lo que muestra cada página, distintos conceptos, las fuentes...

Primero la IA leerá el Índice y luego vera los elementos importantes

- *log.md* es el archivo donde guarda todo lo que ha ido haciendo todos lo que ha ido cambiando dentro de este cerebro teniendo un histórico de todo lo que se a realizado

### CAPA 1: El Esquema
mediante un Claude.md se le dirá a la IA como debe de trabajar

Claud.md tendrá el prom de:

- Conocer tus gustos a la hora de plasmar la información
- Conocer tu forma de trabajo
- Como utilizar la información
- Las reglas que debe de seguir

# Estado del proyecto

*🚧 Proyecto en desarrollo.*

Actualmente se está diseñando la arquitectura de conocimiento y el sistema de mantenimiento automático de la wiki.

Las siguientes fases incluirán:

ingestión automática de documentos;
generación de la wiki;
actualización inteligente;
análisis financiero;
recomendaciones de ahorro;
integración con modelos de IA.

## Referencia

El diseño de esta arquitectura está inspirado en el trabajo de Andrej Karpathy sobre sistemas de conocimiento persistente para modelos de lenguaje.

Paper original:

https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
