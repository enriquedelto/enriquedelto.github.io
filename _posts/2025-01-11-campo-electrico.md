---
layout: post
title: "Campo Eléctrico"
description: "Introducción al estudio del campo eléctrico y sus aplicaciones en ingeniería"
tags: [Electromagnetismo, Ingeniería, Fuerza de Lorentz, Biot-Savart, Ampère]
date: 2025-01-11
featured: false
tabs: true
giscus_comments: true
thumbnail: assets/img/ffi/pexels-photo-414860.webp

images:
  compare: true
  slider: true

mermaid:
  enabled: true
  zoomable: true

code_diff: true
map: true

chart:
  chartjs: true
  echarts: true
  vega_lite: true

tikzjax: true
typograms: true

authors:
  - name: "Enrique M. Delgado Torres"
    url: "https://enriquedelto.github.io/"
    affiliations:
      name: "none"

bibliography: "papers.bib"
---

# Introducción y objetivos

En esta sección se busca establecer el propósito fundamental del estudio del campo eléctrico y sus aplicaciones en la ingeniería. El objetivo principal es comprender cómo las cargas eléctricas generan fuerzas e interacciones en distintos medios, y de qué manera dichos fenómenos se aplican al diseño y análisis de dispositivos y sistemas ingenieriles.

# Concepto de carga y fuerza ejercida por la presencia de cargas

**Carga eléctrica:**  
La carga eléctrica es una propiedad fundamental de la materia que se conserva en cualquier interacción electromagnética, al igual que la masa y la energía. La unidad elemental de carga corresponde a la carga del electrón (negativa) o del protón (positiva), siendo su magnitud idéntica, pero de signo opuesto:

$$e = 1.6 \times 10^{-19} \, \text{C}$$

La carga eléctrica se mide en *coulombs (C)* y puede ser positiva o negativa. Los materiales pueden ganar o perder electrones, dando lugar a cargas netas que determinan su comportamiento electromagnético.

### Fuerza eléctrica  
La fuerza entre dos cargas eléctricas se describe mediante la **Ley de Coulomb**, que establece que la magnitud de la fuerza entre dos cargas puntuales es directamente proporcional al producto de sus cargas e inversamente proporcional al cuadrado de la distancia que las separa. Matemáticamente:

$$\vec{F} = k \frac{q_1 q_2}{r^2} \hat{r}$$

Donde:  
- $$\vec{F}$$ es la fuerza eléctrica (en *newtons*).  
- $$k$$ es la constante de Coulomb:  
  $$k = 9 \times 10^9 \, \text{N} \cdot \text{m}^2/\text{C}^2$$
- $$q_1$$ y $$q_2$$ son las cargas de los objetos en coulombs.  
- $$r$$ es la distancia entre las cargas en metros.  
- $$\hat{r}$$ es un vector unitario que apunta desde una carga hacia la otra.  

### Naturaleza de la interacción:  
- Si $$q_1$$ y $$q_2$$ tienen el mismo signo ($$q_1 q_2 > 0$$) $$\vec{F}$$ tendrá valor positivo lo que implica que la fuerza es **repulsiva**.  
- Si $$q_1$$ y $$q_2$$ tienen signos opuestos ($$q_1 q_2 < 0$$)$$\vec{F}$$ tendrá valor negativo lo que implica que la fuerza es **atractiva**.  

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/EnriquedeltoPlaceholder.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>

{% tabs prompts_carga_y_fuerza %}

{% tab prompts_carga_y_fuerza prompt-1 %}

Eres un profesor de física que desea crear problemas para estudiantes de nivel introductorio al electromagnetismo. Genera un ejercicio paso a paso en el que:
1. Se presenten **dos cargas puntuales** con valores al azar (en coulombs).
2. Se especifique la **distancia** entre ellas (en metros).
3. Se pregunte por la **magnitud** de la fuerza y si la fuerza es **atractiva** o **repulsiva**.
4. Se pida analizar qué ocurre si se **duplica** la distancia entre las cargas o si se **duplica** alguna de las cargas.

{% endtab %}

{% tab prompts_carga_y_fuerza prompt-2 %}

Inventa un problema con **dos cargas puntuales**, donde una tenga un valor positivo y la otra negativo, ambas generadas aleatoriamente. Plantea preguntas como:
- Calcular la fuerza electrostática entre ellas a una distancia específica.
- Determinar la nueva fuerza cuando se varía la distancia a la mitad o al triple de la original.
- Discutir la implicación de cambiar el signo de una de las cargas.

{% endtab %}

{% tab prompts_carga_y_fuerza prompt-3 %}

Crea un ejercicio de **tres cargas puntuales** dispuestas sobre una **misma línea** (eje x). Cada una tendrá un valor aleatorio (positivo o negativo) y se indicarán sus posiciones (aleatoriamente dentro de un rango, por ejemplo, entre 0 y 5 metros).
1. Solicita al estudiante **dibujar** un diagrama con las tres cargas.
2. Pregunta por la **fuerza resultante** sobre una de las cargas (la del centro, por ejemplo).
3. Pide un breve análisis conceptual sobre **cómo se combinaron** las fuerzas parciales para hallar la **fuerza neta**.

{% endtab %}

{% tab prompts_carga_y_fuerza prompt-4 %}

Eres un profesor que desea comparar distintos casos rápidamente. Genera un ejercicio donde:
- Propones **cuatro escenarios** distintos, cada uno con **valores diferentes de cargas** y **distancias**.
- Pides que el estudiante **ordene** las magnitudes de las fuerzas de mayor a menor, y explique **por qué**.
- Incluye al menos un caso en que las fuerzas sean **atractivas** y otro en que sean **repulsivas**.

{% endtab %}

{% tab prompts_carga_y_fuerza prompt-5 %}

Inventa un problema enfocado más en la **explicación conceptual** que en el cálculo numérico. Por ejemplo:
- Se dan dos cargas con valores distintos (aleatorios).
- Se pide al estudiante describir **por qué** la interacción es de repulsión o atracción basándose en los **signos** de las cargas.
- Se pregunta de qué modo se vería afectada la interacción si se **introduce un medio dieléctrico** entre las cargas (por ejemplo, agua o aire con constante dieléctrica diferente).

{% endtab %}

{% endtabs %}

# Campo eléctrico debido a cargas discretas

**Campo eléctrico**: es una propiedad del espacio originada por la presencia de cargas eléctricas y representa la fuerza eléctrica que una carga de prueba positiva ($$q_0$$) experimentaría si estuviera en ese punto. Puede interpretarse como el mecanismo mediante el cual la influencia de una carga eléctrica se transmite por el espacio.

Matemáticamente, el campo eléctrico $$\vec{E}$$ se define como:

$$\vec{E} = \frac{\vec{F}}{q_0}$$

Donde:
- $$\vec{F}$$ es la fuerza ejercida sobre la carga de prueba $$q_0$$
- $$\vec{E}$$ se mide en **newtons por coulomb (N/C)**.

Cuando se tiene un sistema de cargas puntuales, el campo eléctrico resultante en un punto es la suma vectorial de los campos generados por cada carga:

$$\vec{E}_{\text{total}} = \sum_{i} k_e \frac{q_i}{r_i^2} \hat{r}_i$$

Donde:
- $$q_i$$ es la carga puntual $$i$$-ésima.  
- $$r_i$$ es la distancia desde la carga $$q_i$$ al punto de interés.  
- $$\hat{r}_i$$ es el vector unitario que indica la dirección del campo eléctrico.

### **Conceptos de Vector Unitario, Vector Posición y su Módulo**

Para comprender completamente la expresión del campo eléctrico, es esencial entender tres conceptos clave: el **vector unitario**, el **vector posición** y el **módulo del vector posición**. A continuación, se detallan cada uno de estos términos:

#### **Vector Posición ($$\vec{r}$$)**

El **vector posición** es un vector que señala desde una referencia fija (generalmente el origen de coordenadas) hasta la ubicación de un punto específico en el espacio. En el contexto del campo eléctrico, si consideramos una carga $$q_i$$ y un punto de observación, el vector posición $$\vec{r}_i$$ se define como el vector que apunta desde la carga $$q_i$$ hacia el punto de interés.

- **Representación Matemática:**

  Si la carga $$q_i$$ está en el punto $$(x_i, y_i, z_i)$$ y el punto de observación está en $$(x_0, y_0, z_0)$$, entonces:

  $$
  \vec{r}_i = \langle x_0 - x_i, \ y_0 - y_i, \ z_0 - z_i \rangle
  $$

#### **Módulo del Vector Posición ($$|\vec{r}_i|$$)**

El **módulo** o **longitud** del vector posición $$\lvert \vec{r}_i \rvert$$ es la distancia euclidiana entre la carga $$q_i$$ y el punto de interés. Este valor es crucial en la fórmula del campo eléctrico, ya que el campo es inversamente proporcional al cuadrado de esta distancia.

- **Fórmula del Módulo:**

  $$
  |\vec{r}_i| = \sqrt{(x_0 - x_i)^2 + (y_0 - y_i)^2 + (z_0 - z_i)^2}
  $$

#### **Vector Unitario ($$\hat{r}_i$$)**

El **vector unitario** $$\hat{r}_i$$ es un vector con magnitud igual a uno que indica la dirección del vector posición $$\vec{r}_i$$. Se obtiene al normalizar el vector posición, es decir, dividiendo cada componente del vector posición por su módulo. Este vector es fundamental para definir la dirección del campo eléctrico generado por cada carga.

- **Cálculo del Vector Unitario:**

  $$
  \hat{r}_i = \frac{\vec{r}_i}{|\vec{r}_i|} = \left\langle \frac{x_0 - x_i}{|\vec{r}_i|}, \ \frac{y_0 - y_i}{|\vec{r}_i|}, \ \frac{z_0 - z_i}{|\vec{r}_i|} \right\rangle
  $$

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/EnriquedeltoPlaceholder.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>

{% tabs prompts_cargas_discretas %}

{% tab prompts_cargas_discretas prompt-1 %}
Eres un profesor de física que quiere reforzar el uso de **sumas vectoriales** del campo eléctrico. Genera un ejercicio donde:
1. Se indican **dos cargas puntuales** en un plano (con coordenadas (x_1, y_1) y (x_2, y_2)), cada una con valores aleatorios de carga (positivos o negativos).  
2. Se pide al estudiante **calcular** el vector campo eléctrico neto en un **punto de observación** específico (por ejemplo, (x_0, y_0)) mostrando paso a paso la **suma vectorial**.  
3. Se solicita explicar **cómo** se determinan la **dirección** y la **magnitud** resultante.
{% endtab %}

{% tab prompts_cargas_discretas prompt-2 %}
Crea un problema con **tres cargas puntuales** ubicadas en puntos aleatorios del plano (por ejemplo, dentro de un cuadrado de lado 10 metros). Cada carga tendrá magnitud y signo aleatorios. 
- Pide calcular el **campo eléctrico total** en un punto de interés (por ejemplo, el **centro** del cuadrado).  
- Solicita al estudiante **trazar** un diagrama vectorial esquemático que muestre las contribuciones individuales de cada carga.
- Incluye un **análisis** sobre qué ocurriría si una de las cargas **cambiara** de signo.
{% endtab %}

{% tab prompts_cargas_discretas prompt-3 %}
Genera un ejercicio en el que existan **cuatro cargas puntuales**, dispuestas a los **vértices de un rectángulo** con dimensiones al azar (por ejemplo, ancho 2 a 6 m, alto 1 a 4 m). Cada carga tendrá un valor de carga aleatorio (positivo o negativo).  
1. Indica la **posición** de cada carga.  
2. Pide que el alumno calcule el **campo eléctrico resultante** en el **centro** del rectángulo.  
3. Solicita un breve **comentario** sobre si existe alguna **simetría** que facilite o complejice el cálculo.
{% endtab %}

{% endtabs %}

# **Campo eléctrico debido a cargas continuas**

Cuando la distribución de carga no es puntual, sino que está distribuida de manera continua en una línea, superficie o volumen, el cálculo del campo eléctrico requiere realizar una **suma continua** (integral) de los campos generados por cada elemento diferencial de carga.

La expresión general para calcular el campo eléctrico en un punto del espacio es:

$$\vec{E} = k_e \int \frac{dq}{r^2} \hat{r}$$

donde:
- $$k_e = \frac{1}{4\pi \epsilon_0}$$ es la constante de Coulomb.
- $$dq$$ es un elemento diferencial de carga.
- $$r$$ es la distancia desde $$dq$$ al punto donde se evalúa el campo.
- $$\hat{r}$$ es el vector unitario que apunta desde el elemento de carga hacia el punto de observación.

## **Distribuciones comunes de carga continua:**

**1. Planos infinitos**  
- **Tipo de distribución:** **Superficial** ($$\sigma$$).  
  - En este caso, la carga se distribuye uniformemente sobre una superficie plana e infinita. Esto significa que para cada elemento diferencial de área $$dA$$, existe una pequeña cantidad de carga $$dq = \sigma dA$$.  
  - La simetría del plano infinito permite calcular el campo eléctrico directamente:
    
    $$E = \frac{\sigma}{2 \epsilon_0}$$

  - El campo eléctrico es constante y perpendicular al plano, independiente de la distancia al plano.

**2. Eje de un disco**  
- **Tipo de distribución:** **Superficial** ($$\sigma$$).  
  - El disco cargado es una superficie plana circular con densidad superficial de carga $$\sigma$$. A diferencia del plano infinito, tiene un radio finito $$R$$.  
  - El campo eléctrico en el eje del disco se obtiene sumando las contribuciones diferenciales $$dq = \sigma dA$$ de todos los anillos concéntricos del disco:
    
    $$E_z = \frac{\sigma}{2 \epsilon_0} \left( 1 - \frac{z}{\sqrt{z^2 + R^2}} \right)$$

**3. Eje de un anillo**  
- **Tipo de distribución:** **Lineal** ($$\lambda$$).  
  - En este caso, la carga se distribuye a lo largo de un anillo circular, formando una línea cerrada con densidad lineal $$\lambda$$.  
  - La carga total del anillo es $$q = \lambda \cdot 2\pi R$$, donde $$R$$ es el radio del anillo.  
  - El campo eléctrico en el eje del anillo es:
    
    $$E_z = \frac{k_e q z}{(z^2 + R^2)^{3/2}}$$

**4. Segmento cargado**  
- **Tipo de distribución:** **Lineal** ($$\lambda$$).  
  - La carga se distribuye uniformemente a lo largo de un segmento de longitud $$L$$ con densidad lineal de carga $$\lambda$$.  
  - Cada elemento diferencial de longitud $$dl$$ aporta una pequeña carga $$dq = \lambda dl$$.  
  - El cálculo del campo eléctrico implica integrar los aportes de todos los elementos $$dl$$, considerando la dirección y la simetría del segmento.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/EnriquedeltoPlaceholder.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>

{% tabs prompts_campo_electrico %}

{% tab prompts_campo_electrico prompt-1 %}

Eres un profesor de física que desea reforzar el cálculo del **campo eléctrico generado por un plano infinito cargado**. Genera un ejercicio donde:
1. Se indique una **densidad superficial de carga** \sigma (en C/m²) sobre un plano infinito.
2. Se pida al estudiante **calcular** el campo eléctrico en un punto cercano al plano, especificando que debe considerar la dirección y magnitud del campo.
3. Solicita al estudiante **analizar** qué ocurriría si la densidad superficial de carga se duplica y cómo afecta esto al campo eléctrico.

{% endtab %}

{% tab prompts_campo_electrico prompt-2 %}

Crea un problema sobre el **campo eléctrico en el eje de un disco cargado**. El ejercicio debe:
- Especificar un **disco circular** con radio R y **densidad superficial de carga** \sigma.
- Pedir al estudiante que **calcule** el campo eléctrico en un punto a una distancia z sobre el eje del disco, utilizando la fórmula:
  
  E_z = \frac{\sigma}{2 \epsilon_0} \left( 1 - \frac{z}{\sqrt{z^2 + R^2}} \right)
  
- Solicitar al estudiante que **interprete** el comportamiento del campo eléctrico cuando z tiende a cero y cuando z tiende a infinito.

{% endtab %}

{% tab prompts_campo_electrico prompt-3 %}

Genera un ejercicio sobre el **campo eléctrico generado por un anillo cargado**. El problema debe:
1. Indicar un **anillo circular** de radio R con **densidad lineal de carga** \lambda.
2. Pedir al estudiante que **calcule** el campo eléctrico en un punto a una distancia z sobre el eje del anillo, utilizando la fórmula:
   
   E_z = \frac{k_e q z}{(z^2 + R^2)^{3/2}}
   
   donde q = \lambda \cdot 2\pi R.
3. Solicitar al estudiante que **explique** cómo varía el campo eléctrico cuando:
   - El radio del anillo se duplica.
   - La densidad lineal de carga se reduce a la mitad.

{% endtab %}

{% tab prompts_campo_electrico prompt-4 %}

Crea un problema que involucre el cálculo del **campo eléctrico producido por un segmento cargado rectilíneo**. El ejercicio debe:
- Especificar un **segmento de longitud** L con **densidad lineal de carga** \lambda, ubicado a lo largo del eje x desde x = -\frac{L}{2} hasta x = \frac{L}{2}.
- Pedir al estudiante que **calcule** el campo eléctrico en un punto ubicado a una distancia y sobre el eje y.
- Solicitar un **análisis** sobre cómo el campo eléctrico cambia si:
  - La longitud del segmento se incrementa.
  - La densidad lineal de carga se invierte en signo.

{% endtab %}

{% tab prompts_campo_electrico prompt-5 %}

Diseña un ejercicio sobre el **campo eléctrico en el centro geométrico de un polígono regular cargado**. El problema debe:
1. Indicar un **polígono regular** (por ejemplo, un **triángulo equilátero** o un **cuadrado**) con **cargas** q_i ubicadas en cada vértice.
2. Pedir al estudiante que **calcule** el campo eléctrico resultante en el **centro geométrico** del polígono, considerando que las cargas pueden ser positivas o negativas.
3. Solicitar al estudiante que **discuta** bajo qué condiciones el campo eléctrico en el centro sería **nulo**, y **por qué**, basándose en la simetría y los valores de las cargas.

{% endtab %}

{% endtabs %}

# Ley de Gauss

**Ley de Gauss**:  
La Ley de Gauss establece la relación entre el flujo eléctrico que atraviesa una superficie cerrada y la carga eléctrica encerrada en su interior. Es una de las ecuaciones fundamentales del electromagnetismo y puede enunciarse matemáticamente en su forma integral como:

$$
\oint_{\text{Superficie cerrada}} \vec{E} \cdot d\vec{A} = \frac{Q_{\text{enc}}}{\epsilon_0}
$$

Donde:
- $$\vec{E}$$ es el campo eléctrico.
- $$d\vec{A}$$ es el vector área diferencial de la superficie.
- $$Q_{\text{enc}}$$ es la carga total encerrada por la superficie.
- $$\epsilon_0$$ es la permitividad eléctrica del vacío.

La utilidad principal de la Ley de Gauss radica en su capacidad para simplificar el cálculo del campo eléctrico en sistemas con **alto grado de simetría** (esférica, cilíndrica o planar). Si la distribución de carga y la geometría del problema permiten suponer que el campo es constante en magnitud sobre la superficie elegida y que es perpendicular (o paralelo) a ciertas partes de esa superficie, la evaluación de la integral se vuelve directa.

### Procedimiento de aplicación

1. **Seleccionar una superficie gaussiana** (cerrada) que aproveche la **simetría** del problema (esfera, cilindro, plano, etc.).
2. **Expresar el flujo eléctrico** $$\Phi_E = \oint \vec{E} \cdot d\vec{A}$$ a través de dicha superficie.  
3. **Calcular la carga encerrada** $$Q_{\text{enc}}$$ por la superficie.
4. **Aplicar la Ley de Gauss**:  
   
   $$\oint \vec{E} \cdot d\vec{A} = \frac{Q_{\text{enc}}}{\epsilon_0}$$

5. **Despejar $$\vec{E}$$** o la magnitud del campo si la simetría lo permite.

### Ejemplos comunes de aplicación

- **Esfera cargada**: Dentro y fuera de la esfera se aprovecha la simetría esférica.
- **Cilindro cargado**: En el cálculo del campo en el interior y exterior de un cable o un alambre de sección cilíndrica.
- **Placa plana infinita**: Para obtener un campo constante (como en un condensador).

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/EnriquedeltoPlaceholder.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>

{% tabs prompts_gauss %}

{% tab prompts_gauss prompt-1 %}

Eres un profesor de física que desea reforzar la **aplicación de la Ley de Gauss para una esfera cargada**. Genera un ejercicio donde:
1. Se indique una **esfera de radio** R con **carga total** Q distribuida uniformemente.
2. Se pida al estudiante **calcular** el campo eléctrico en un punto **dentro** de la esfera (r < R) y en un punto **fuera** de la esfera (r > R), utilizando la Ley de Gauss.
3. Solicita al estudiante **explicar** por qué el campo eléctrico dentro de la esfera varía con la distancia mientras que fuera es equivalente al de una carga puntual.

{% endtab %}

{% tab prompts_gauss prompt-2 %}

Crea un problema sobre el **campo eléctrico alrededor de un cilindro infinito cargado**. El ejercicio debe:
- Especificar un **cilindro de radio** R con **densidad lineal de carga** \lambda.
- Pedir al estudiante que **calcule** el campo eléctrico a una distancia r del eje del cilindro, considerando los casos:
  - r < R (dentro del cilindro).
  - r > R (fuera del cilindro).
- Solicitar al estudiante que **analice** cómo el campo eléctrico cambia si la densidad lineal de carga se duplica.

{% endtab %}

{% tab prompts_gauss prompt-3 %}

Genera un ejercicio sobre el **campo eléctrico generado por una placa plana infinita cargada**. El problema debe:
1. Indicar una **placa infinita** con **densidad superficial de carga** \sigma.
2. Pedir al estudiante que **calcule** el campo eléctrico a una distancia d de la placa, utilizando la Ley de Gauss.
3. Solicitar al estudiante que **explique** por qué el campo eléctrico es **constante** y **perpendicular** a la placa, independientemente de la distancia d.

{% endtab %}

{% tab prompts_gauss prompt-4 %}

Crea un problema que involucre la **selección de una superficie gaussiana adecuada**. El ejercicio debe:
- Presentar una **configuración** con una **esfera cargada** y un **cilindro cargado**.
- Pedir al estudiante que **seleccione** la superficie gaussiana apropiada para calcular el campo eléctrico en diferentes regiones de la configuración.
- Solicitar que el estudiante **justifique** su elección de superficie gaussiana basada en la simetría del problema.

{% endtab %}

{% tab prompts_gauss prompt-5 %}

Diseña un ejercicio que combine **Ley de Gauss y superposición de campos eléctricos**. El problema debe:
1. Indicar una **combinación** de una **esfera cargada** y un **cilindro cargado** con diferentes densidades de carga.
2. Pedir al estudiante que **calcule** el campo eléctrico en un punto específico fuera de ambas distribuciones de carga, aplicando la Ley de Gauss a cada una por separado y luego **sumando** los campos resultantes.
3. Solicitar al estudiante que **explique** cómo la superposición de campos afecta el campo eléctrico total en ese punto.

{% endtab %}

{% endtabs %}

# Conductores y aislantes

**Conductores**:  
Los conductores son materiales que permiten el libre movimiento de cargas eléctricas (electrones) a través de ellos. En el **equilibrio electrostático**, las cargas en un conductor se distribuyen en la **superficie** con el fin de anular el campo eléctrico dentro del material. Algunas propiedades fundamentales de los conductores:

- **Movimiento libre de cargas**: Los electrones pueden desplazarse sin demasiada oposición.  
- **Campo interno nulo**: En estado estacionario, el campo eléctrico dentro de un conductor es cero.  
- **Distribución de carga en la superficie**: La repulsión electrostática hace que las cargas se sitúen en la región más externa posible.  
- **Superficies equipotenciales**: Todo el volumen del conductor y su superficie se encuentran al mismo potencial.

**Aislantes** (dieléctricos):  
Los aislantes, en contraste, no permiten el libre movimiento de cargas en su interior. Las cargas permanecen ligadas a sus átomos o moléculas, dificultando la conducción eléctrica. Algunas características:

- **Elevada resistencia eléctrica**: Muy pocas cargas libres disponibles para su movimiento.  
- **Polarización**: Bajo la influencia de un campo eléctrico externo, los dipolos atómicos o moleculares pueden alinearse, creando un campo interno que reduce parcialmente el campo aplicado.  
- **Uso en condensadores**: Los aislamientos eléctricos son esenciales en equipos electrónicos para evitar corrientes no deseadas y para almacenar energía eléctrica.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/EnriquedeltoPlaceholder.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>

{% tabs prompts_conductores_y_aislantes %}

{% tab prompts_conductores_y_aislantes prompt-1 %}

Eres un profesor de física que desea reforzar la comprensión de las **propiedades de los conductores en equilibrio electrostático**. Genera un ejercicio donde:
1. Se presente un **conductor esférico** cargado con una carga total Q.
2. Se pida al estudiante que **determinar**:
   - La **distribución de carga** en el conductor.
   - El **campo eléctrico** tanto **dentro** como **fuera** del conductor.
3. Solicita al estudiante que **explique** por qué el campo eléctrico dentro del conductor es nulo y cómo se distribuyen las cargas en la superficie.

{% endtab %}

{% tab prompts_conductores_y_aislantes prompt-2 %}

Crea un problema que compare **conductores y aislantes** en presencia de un campo eléctrico externo. El ejercicio debe:
1. Presentar una **varilla conductora** y una **varilla aislante** de la misma forma y tamaño, colocadas en un campo eléctrico uniforme.
2. Pedir al estudiante que **describa** cómo se distribuyen las cargas en cada varilla.
3. Solicitar que el estudiante **explique** las diferencias observadas en la distribución de cargas y los campos eléctricos internos para ambos materiales.
4. Preguntar sobre las **implicaciones prácticas** de estas diferencias en aplicaciones electrónicas.

{% endtab %}

{% tab prompts_conductores_y_aislantes prompt-3 %}

Genera un ejercicio sobre la **polarización de un aislante**. El problema debe:
1. Indicar un **material aislante** colocado en un campo eléctrico externo \vec{E}.
2. Pedir al estudiante que **explique** el proceso de **polarización** molecular en el aislante.
3. Solicitar que el estudiante **calcule** el campo eléctrico resultante dentro del aislante, considerando la constante dieléctrica \epsilon del material.
4. Pedir al estudiante que **discuta** cómo la polarización afecta la interacción del material con cargas externas.

{% endtab %}

{% tab prompts_conductores_y_aislantes prompt-4 %}

Diseña un ejercicio que involucre el uso de un **condensador con dieléctrico**. El problema debe:
1. Presentar un **condensador de placas paralelas** con área A y separación d, insertando un **material aislante** con constante dieléctrica \kappa entre las placas.
2. Pedir al estudiante que **calcule** la **capacitancia** del condensador antes y después de insertar el dieléctrico.
3. Solicitar que el estudiante **explique** cómo el dieléctrico afecta el campo eléctrico entre las placas y la **energía almacenada** en el condensador.
4. Preguntar sobre las **aplicaciones prácticas** de los dieléctricos en dispositivos electrónicos.

{% endtab %}

{% tab prompts_conductores_y_aislantes prompt-5 %}

Crea un problema que explore la **distribución de cargas en un conductor en presencia de cargas externas**. El ejercicio debe:
1. Indicar una **concha conductora hueca** con radio externo R, colocada en un campo eléctrico externo uniforme \vec{E}.
2. Colocar una **carga puntual** q en el interior hueco de la concha.
3. Pedir al estudiante que **determine**:
   - La **distribución de carga** en la superficie interna y externa de la concha.
   - El **campo eléctrico** dentro y fuera de la concha.
4. Solicitar al estudiante que **explique** cómo la presencia de la carga interna q influye en la distribución de las cargas en la concha y en el campo eléctrico resultante.

{% endtab %}

{% tab prompts_conductores_y_aislantes prompt-6 %}

Genera un ejercicio que contraste el comportamiento de **conductores y aislantes en un circuito eléctrico**. El problema debe:
1. Presentar un **circuito simple** que incluya tanto **componentes conductores** (como alambres) como **componentes aislantes** (como plásticos o cerámicas).
2. Pedir al estudiante que **identifique** qué partes del circuito permiten el flujo de corriente y cuáles lo impiden.
3. Solicitar que el estudiante **explique** el papel de los conductores y aislantes en la **eficiencia** y **seguridad** del circuito.
4. Pedir al estudiante que **proponga** mejoras en el diseño del circuito para optimizar el flujo de corriente y minimizar riesgos eléctricos, justificando el uso de materiales conductores y aislantes en cada caso.

{% endtab %}

{% endtabs %}
