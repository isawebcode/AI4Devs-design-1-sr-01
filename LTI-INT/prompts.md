# Prompts

Modelo asistente: GPT-4o
Los prompts utilizados aparaecerán en los recuadros grises
Las respuestas a los prompts están en el archivo LTI-INT

## Descripción breve del software LTI, valor añadido y ventajas competitivas.

```
Eres experto en producto, con experiencia en sistemas ATS, la startup LTI te pide que
describas brevemente el software que desarrollas, su valor añadido y ventajas competitivas.

Con el objetivo de brillar por encima de sus competidores, aumentar la eficiencia para los
departamentos de HR, mejorar la colaboración en tiempo real entre reclutadores y managers,
automatizaciones, asistencia de IA en diversas tareas...
```

## Explicación de las funciones principales.

```
¿Qué funcionalidades básicas tiene el sistema ATS que me has propuesto antes?
Descríbemelas en un listado, ordenado de mayor a menor prioridad.
Dame la respuesta en formato markdown.
```

## Añadir un diagrama Lean Canvas para entender el modelo de negocio.

```
Me puedes dar un diagrama Lean Canvas para entender el modelo de negocio,
dámelo en formato markdown y conviértelo después en un diagrama visual en formato .PNG
```

Al darme la imagen, se solapan los textos, por lo que le mando el siguiente prompt

```
Hay secciones que se salen en el png del lean canvas, lo puedes generar para que esto no suceda?
```

## Descripción de los 3 casos de uso principales, con el diagrama asociado a cada uno.

```
Eres un analista de software experto.
Enumera y describe brevemente los 3 casos de uso principales y representa
cada uno de estos casos de uso con el tipo de diagrama más adecuado usando el formato plantUML.
Aplica buenas prácticas UML, define y describe lo que sea necesario.
La salida de texto la quiero en formato markdown.
```

Le pido también que me los genere en mermaid.

```
Me los puedes dar en formato mermaid los diagramas?
```

## Modelo de datos que cubra entidades, atributos (nombre y tipo) y relaciones.

```
Eres un experto en modelos de datos. Dime brevemente el modelo
de datos que cubre entidades, atributos (nombre y tipo) y relaciones.
La salida de texto la quiero en formato markdown.
```

Le pedimos que lo complete con un diagrama ER en formato mermaid.

```
Prepara el diagrama ER en formato mermaid
```

## Diseño del sistema a alto nivel, tanto explicado como diagrama adjunto.

```
Eres un brillante arquitecto de software. Eres capaz de diseñar, explicar y
diagramar los diferentes aspectos de un sistema de software.Dime el diseño del
sistema a alto nivel, tanto explicado como diagrama adjunto. La salida de texto
la quiero en formato markdown para que pueda copiar y pegar. Y el diagrama en
formato mermaid.
```

## Diagrama C4 que llegue en profundidad a uno de los componentes del sistema, el que prefieras.

```
Eres un experto en diagramas C4. Dime el diagrama C4 que llegue en profundidad
a uno de los componentes del sistema, el que prefieras. La salida de texto la
quiero en formato markdown para que pueda copiar y pegar. Y el diagrama en
formato mermaid.
```

Este último paso no ha cumplido con las expectativas, por lo que mediante meta-prompting consigo un mejor prompt para resolver este paso

```
Eres un arquitecto de software experto en documentación técnica y visualización de arquitectura. Necesito que generes un conjunto de diagramas C4 usando la sintaxis de Mermaid, basados en el sistema que ya te he descrito anteriormente.

Por favor, entrega los cuatro niveles del modelo C4, manteniendo la coherencia entre ellos, con el siguiente formato:

1. Diagrama de Contexto:
Muestra cómo el sistema se relaciona con usuarios y sistemas externos. Identifica claramente los actores principales (usuarios humanos) y servicios externos (APIs, herramientas, otras plataformas). Usa Mermaid con sintaxis graph TB.

2. Diagrama de Contenedores:
Divide el sistema en sus principales contenedores (por ejemplo: frontend, backend, base de datos, servicios externos, motores, etc.). Explica cómo se comunican entre ellos y qué tecnologías usan. Usa graph TB o graph LR según convenga la distribución visual.

3. Diagrama de Componentes (de un contenedor específico):
Profundiza en un único contenedor (por ejemplo, el backend o un módulo funcional importante), mostrando sus componentes internos y cómo interactúan. Representa servicios, repositorios, controladores, integraciones, etc.

4. Diagrama de Código (opcional con classDiagram):
Usa la sintaxis classDiagram de Mermaid para mostrar el diseño interno de uno de los componentes, incluyendo clases, atributos, métodos, y relaciones básicas. Usa un estilo orientado a objetos (puede estar inspirado en TypeScript, Java o Python).

Requisitos adicionales:

Usa sintaxis Mermaid para todos los diagramas.

No incluyas ningún texto fuera del bloque de código Mermaid.

Añade comentarios Mermaid (%%) para indicar claramente el nivel del diagrama.

Sé visualmente claro, mantén la consistencia entre niveles, y representa relaciones lógicas (-->, -.->, etc.).

Utiliza nombres representativos, pero evita detalles de negocio si no están presentes en el contexto.
```

Con el diagrama de contexto nos aparece un error, le pasamos el error para que lo solucione.

```
En el diagrama de contexto me sale el siguiente error Error: Parse error on line 3:
...Recruiter[Recruiter (Usuario)]        M
-----------------------^
Expecting 'SQE', 'DOUBLECIRCLEEND', 'PE', '-)', 'STADIUMEND', 'SUBROUTINEEND', 'PIPE', 'CYLINDEREND', 'DIAMOND_STOP', 'TAGEND', 'TRAPEND', 'INVTRAPEND', 'UNICODE_TEXT', 'TEXT', 'TAGSTART', got 'PS'
```

Con el diagrama de contenedores nos aparece otro error diferente, se lo pasamos también para que lo corrija.

```
El diagrama de contenedores me da el siguiente error, soluciónalo: Error: Parse error on line 8:
...        FE[Frontend (React/Next.js)]
-----------------------^
Expecting 'SQE', 'DOUBLECIRCLEEND', 'PE', '-)', 'STADIUMEND', 'SUBROUTINEEND', 'PIPE', 'CYLINDEREND', 'DIAMOND_STOP', 'TAGEND', 'TRAPEND', 'INVTRAPEND', 'UNICODE_TEXT', 'TEXT', 'TAGSTART', got 'PS'
```

Lo mismo ocurre con el de componentes

```
Error en el de componetes, soluciónalo:
Error: Parse error on line 3:
...[Controladores REST (Candidatos, Vacante
-----------------------^
Expecting 'SQE', 'DOUBLECIRCLEEND', 'PE', '-)', 'STADIUMEND', 'SUBROUTINEEND', 'PIPE', 'CYLINDEREND', 'DIAMOND_STOP', 'TAGEND', 'TRAPEND', 'INVTRAPEND', 'UNICODE_TEXT', 'TEXT', 'TAGSTART', got 'PS'
```
