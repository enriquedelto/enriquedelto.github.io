---
layout: post
title: "Potencial eléctrico"
description: "Introducción al estudio del potencial eléctrico y sus aplicaciones en ingeniería"
tags: [Electromagnetismo, Ingeniería, Fuerza de Lorentz, Biot-Savart, Ampère]
date: 2025-01-13
featured: false
tabs: true
giscus_comments: true
thumbnail: assets/img/ffi/pexels-philippedonn-1114688.jpg

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

En esta sección, exploraremos el concepto de **potencial eléctrico** y su importancia en el estudio del electromagnetismo y la ingeniería. A diferencia del **campo eléctrico**, que describe la **fuerza** por unidad de **carga** en un punto del espacio, el **potencial eléctrico** se asocia a la **energía** por unidad de carga. Esta perspectiva basada en la energía resulta de gran utilidad para analizar y diseñar dispositivos y sistemas eléctricos y electrónicos, ya que:

- Permite describir el **trabajo** (medido en **julios**($$J$$)) necesario para mover **cargas** de un punto a otro dentro de un **campo** eléctrico.  
- Facilita el estudio y la **simulación** de campos eléctricos en sistemas complejos, gracias a la superposición de potenciales.  
- Constituye la base de muchos cálculos en componentes como **condensadores**, **baterías** y otros sistemas de almacenamiento y distribución de energía.

El objetivo principal de esta sección es comprender la definición y el cálculo del potencial eléctrico en diferentes configuraciones de cargas, tanto puntuales como continuas, y relacionarlo con el campo eléctrico de manera coherente.

---

## Relación entre Fuerza, Energía y Trabajo en Electromagnetismo

Para entender el papel del potencial eléctrico, es útil recordar la conexión con la **mecánica clásica**:

- **En mecánica**, el **trabajo** ($$W$$) realizado por una fuerza $$\vec{F}$$ al mover un objeto en la dirección del desplazamiento $$d\vec{r}$$ es:

  $$
  W \;=\; \int \vec{F} \cdot d\vec{r}.
  $$

- **En electromagnetismo**, la fuerza que actúa sobre una carga $$q$$ en un **campo eléctrico** $$\vec{E}$$ es $$\vec{F} = q\,\vec{E}$$. El trabajo por unidad de carga (es decir, el trabajo dividido entre $$q$$) equivale precisamente al **cambio de energía potencial eléctrica** por unidad de carga, lo que definimos como cambio de **potencial eléctrico**.

Esta analogía se extiende también a la **potencia** en mecánica (energía por unidad de tiempo) y el **potencial** en electromagnetismo (energía por unidad de carga). Si bien son conceptos diferentes, ambos giran en torno a la idea de **energía**: en mecánica, la rapidez con la que se transfiere; en electromagnetismo, la diferencia de energía por carga al desplazarnos en un campo eléctrico.

---

## Energía Potencial Gravitatoria

La **energía potencial gravitatoria** es la energía que posee un objeto debido a su posición en un campo gravitatorio. Se define como el trabajo realizado contra la fuerza de gravedad para mover el objeto desde una posición de referencia (generalmente el suelo) hasta una altura $$h$$.

- **Fórmula de la Energía Potencial Gravitatoria ($$U_g$$):**

  $$
  U_g \;=\; m \cdot g \cdot h
  $$

  donde:
  
  - $$m$$ es la masa del objeto.
  - $$g$$ es la aceleración debida a la gravedad (≈ $$9.81 \, \text{m/s}^2$$ en la superficie terrestre).
  - $$h$$ es la altura a la que se eleva el objeto.

- **Explicación:**

  Al elevar un objeto de masa $$m$$ una altura $$h$$, se realiza un trabajo $$W$$ contra la fuerza gravitatoria. Este trabajo se almacena como energía potencial gravitatoria en el objeto. Matemáticamente:

  $$
  W \;=\; m \cdot g \cdot h \;=\; U_g
  $$

  Si se libera el objeto, la energía potencial gravitatoria se convierte en energía cinética a medida que el objeto cae, demostrando la conversión de energía almacenada en movimiento.

---

## Energía Potencial Eléctrica

La **energía potencial eléctrica** es la energía que posee una carga eléctrica debido a su posición en un campo eléctrico. Se define como el trabajo realizado contra la fuerza eléctrica para mover la carga desde un punto de referencia hasta una posición específica en el campo.

- **Fórmula de la Energía Potencial Eléctrica ($$U_e$$):**

  $$
  U_e \;=\; q \cdot V
  $$

  donde:
  
  - $$q$$ es la carga eléctrica.
  - $$V$$ es el potencial eléctrico en la posición de la carga.

- **Explicación:**

  Cuando una carga $$q$$ se mueve en un campo eléctrico desde un punto $$A$$ hasta un punto $$B$$, se realiza un trabajo $$W$$ contra la fuerza eléctrica. Este trabajo se almacena como energía potencial eléctrica en la carga. Matemáticamente:

  $$
  W \;=\; q \cdot (V_B - V_A) \;=\; \Delta U_e
  $$

  Si la carga se libera, la energía potencial eléctrica se convierte en energía cinética a medida que la carga se mueve bajo la influencia del campo eléctrico, demostrando la conversión de energía almacenada en movimiento.

---

## Comparación entre Energía Potencial Gravitatoria y Eléctrica

Ambas formas de energía potencial comparten similitudes y presentan diferencias fundamentales debido a la naturaleza de las fuerzas involucradas.

### **Similitudes:**

1. **Almacenamiento de Trabajo Realizado:**
   
   - **Gravitatoria:** El trabajo realizado al elevar un objeto contra la gravedad se almacena como energía potencial gravitatoria.
   - **Eléctrica:** El trabajo realizado al mover una carga contra la fuerza eléctrica se almacena como energía potencial eléctrica.

2. **Dependencia de la Posición en un Campo:**
   
   - **Gravitatoria:** La energía potencial depende de la altura del objeto en el campo gravitatorio.
   - **Eléctrica:** La energía potencial depende de la posición de la carga en el campo eléctrico.

### **Diferencias:**

1. **Naturaleza de las Fuerzas Involucradas:**
   
   - **Gravitatoria:** La fuerza gravitatoria es siempre atractiva y actúa entre masas.
   - **Eléctrica:** La fuerza eléctrica puede ser atractiva o repulsiva, dependiendo de los signos de las cargas involucradas.

2. **Dependencia de las Magnitudes Físicas:**
   
   - **Gravitatoria:** La energía potencial gravitatoria depende de la masa del objeto.
   - **Eléctrica:** La energía potencial eléctrica depende de la carga eléctrica de la partícula.

Estas diferencias reflejan cómo las fuerzas conservativas en diferentes campos (gravitatorio y eléctrico) afectan el almacenamiento y la conversión de energía potencial de manera distinta.

{% tabs prompts_fuerza_energia_trabajo %}
{% tab prompts_fuerza_energia_trabajo prompt-1 %}
**Ejercicio 1: Comparación entre energía potencial gravitatoria y eléctrica**

Eres un profesor que desea crear un ejercicio para evaluar a tus alumnos sobre la comparación entre energía potencial gravitatoria y eléctrica. Formula un ejercicio que incluya los siguientes puntos:

1. Imagina que tienes un objeto de masa  m  y lo elevas una distancia  h  en un campo gravitatorio terrestre. Explica por qué se dice que el trabajo realizado se “almacena” como energía potencial gravitatoria.
2. Compara esa situación con una carga  q  que se mueve desde un punto  A  hasta un punto  B  en un campo eléctrico uniforme.
   - ¿Por qué podemos decir que el trabajo realizado se “almacena” como energía potencial eléctrica?
   - ¿Qué similitudes y diferencias encuentras entre ambos casos?

{% endtab %}

{% tab prompts_fuerza_energia_trabajo prompt-2 %}
**Ejercicio 2: Trabajo por unidad de carga**

Eres un profesor que quiere diseñar un ejercicio para evaluar a tus alumnos sobre el trabajo realizado por un campo eléctrico. Crea un ejercicio que incluya los siguientes aspectos:

1. Se tiene una carga  q  en un campo eléctrico uniforme  \vec{E} . Su posición inicial es el punto  A  y la final es  B , separados por una distancia  d  en la dirección del campo.
2. Pide a los alumnos que:
   - Expresen el trabajo  W  realizado por el campo al mover la carga.
   - Expliquen por qué el trabajo por unidad de carga  \frac{W}{q}  es equivalente a la diferencia de potencial eléctrico  V_B - V_A .

{% endtab %}
{% endtabs %}

---

# Diferencia de potencial

Para mantener la **consistencia en la notación**, definiremos cuidadosamente cada término:

- **Potencial eléctrico** $$(V)$$: energía potencial eléctrica por unidad de carga.  
- **Energía potencial eléctrica** $$(U)$$: energía asociada a la posición de una carga (o conjunto de cargas) en un campo eléctrico.  
- **Campo eléctrico** $$(\vec{E})$$: región del espacio donde una carga experimenta una fuerza.  
- **Densidad de carga** $$(\rho, \sigma, \lambda)$$: magnitud de carga por unidad de volumen, superficie o longitud, respectivamente.

El **potencial eléctrico** en un punto se define como la **energía potencial eléctrica** por unidad de carga necesaria para llevar una carga de prueba desde una posición de referencia (generalmente el infinito) hasta ese punto, **sin** alterar la configuración de las cargas que crean el campo.

**Diferencia de potencial (ddp) entre dos puntos $$A$$ y $$B$$**:  

$$
V_B - V_A \;=\; - \int_{A}^{B} \vec{E} \cdot d\vec{r}.
$$

Donde:  
- $$\vec{E}$$ es el **campo eléctrico**.  
- $$d\vec{r}$$ es el vector infinitesimal de desplazamiento desde $$A$$ hasta $$B$$.  
- La integral se realiza a lo largo de un camino que va de $$A$$ hasta $$B$$.

En muchos casos, se selecciona el potencial igual a cero en el infinito $$\bigl(V(\infty) = 0\bigr)$$, de modo que el **potencial** en un punto $$P$$ puede expresarse como:

$$
V(P) \;=\; - \int_{\infty}^{P} \vec{E} \cdot d\vec{r}.
$$

{% tabs prompts_diferencia_potencial %}
{% tab prompts_diferencia_potencial prompt-1 %}
**Ejercicio 1: Diferencia de potencial y ruta de integración**

1. Muestra, a partir de la definición V_B - V_A = - \int_A^B \vec{E}\cdot d\vec{r}, que en un **campo electrostático** la diferencia de potencial **no** depende de la ruta seguida, sino solo de los puntos inicial y final.  
2. Explica qué implica que \vec{E} sea un **campo conservativo**.

{% endtab %}

{% tab prompts_diferencia_potencial prompt-2 %}
**Ejercicio 2: Cálculo de V_B - V_A en un campo de carga puntual**

1. Considera una carga puntual Q ubicada en el origen y un punto A a distancia r_A de la carga, mientras que B se encuentra a distancia r_B.  
2. Usando la expresión V(r) = k_e \frac{Q}{r}, calcula la diferencia de potencial V_B - V_A.  
3. Interpreta físicamente el resultado obtenido en términos de trabajo por unidad de carga.

{% endtab %}
{% endtabs %}

---

# Potencial debido a cargas puntuales

Cuando se trata de **cargas puntuales**, el **potencial eléctrico** resultante en un punto se obtiene mediante la **suma escalar** de los potenciales debidos a cada carga individual. Para una **carga puntual** $$q$$ situada en el origen, el **potencial** en un punto a distancia $$r$$ de dicha carga es:

$$
V \;=\; k_e \,\frac{q}{r},
$$

donde:

- $$k_e = \frac{1}{4\pi \epsilon_0} \approx 9 \times 10^9 \ \text{N}\cdot\text{m}^2/\text{C}^2$$.  
- $$\epsilon_0$$ es la **permitividad eléctrica** del vacío.

**Superposición de potenciales**  
Si se tienen varias cargas puntuales $$q_1, q_2, \ldots, q_n$$ y se desea calcular el potencial en un punto $$P$$, la **superposición** establece que:

$$
V_{\text{total}}(P) \;=\; \sum_{i=1}^{n} k_e \,\frac{q_i}{r_i},
$$

donde $$r_i$$ es la distancia desde la carga $$q_i$$ al punto $$P$$.  
A diferencia del **campo eléctrico** —que se suma vectorialmente— el potencial es un **escalar**, lo que simplifica en muchos casos el cálculo.

{% tabs prompts_cargas_puntuales %}
{% tab prompts_cargas_puntuales prompt-1 %}
**Ejercicio 1: Potencial de dos cargas puntuales**

1. Se tienen dos cargas q_1 y q_2 ubicadas en posiciones conocidas (por ejemplo, en el eje x).  
2. Determina el potencial total en un punto P arbitrario del plano.  
3. Compara el procedimiento con el cálculo del campo eléctrico (que implica suma vectorial) y discute por qué el potencial es más sencillo de **superponer**.

{% endtab %}

{% tab prompts_cargas_puntuales prompt-2 %}
**Ejercicio 2: Sistema de tres cargas**

1. Coloca tres cargas puntuales q_1, q_2, q_3 en vértices de un triángulo equilátero de lado a.  
2. Calcula el potencial en el **centro** del triángulo.  
3. ¿Qué sucede con el valor del potencial si una de las cargas cambia de signo? Explica la repercusión física.

{% endtab %}
{% endtabs %}

---

# Potencial eléctrico debido a cargas continuas

Para distribuciones **no puntuales** de carga (por ejemplo, líneas, superficies o volúmenes cargados), el **potencial eléctrico** se calcula integrando la contribución de todos los elementos diferenciales de carga $$dq$$. La expresión general es:

$$
V(\vec{r}) \;=\; k_e \int \frac{dq}{|\vec{r} - \vec{r}\,'|},
$$

donde:

- $$\vec{r}$$ es la posición del punto de observación.  
- $$\vec{r}\,'$$ es la posición del elemento de carga diferencial $$dq$$.  
- $$\lvert \vec{r} - \vec{r}\,'\rvert$$ es la distancia entre ambos.

### Ejemplo de cálculo: anillo cargado

Consideremos un **anillo** de radio $$R$$ con **carga total** $$Q$$ distribuida uniformemente (densidad lineal $$\lambda$$). El **potencial eléctrico** en un punto $$P$$ sobre el eje del anillo, a una distancia $$z$$ de su centro, viene dado por:

$$
V(z) = k_e \,\frac{Q}{\sqrt{z^2 + R^2}}.
$$

Este resultado se obtiene sumando (integrando) la contribución de cada elemento diferencial de carga $$\lambda\,dl$$ que compone el anillo.

{% tabs prompts_cargas_continuas %}
{% tab prompts_cargas_continuas prompt-1 %}
**Ejercicio 1: Anillo cargado y comparación de límites**

1. Reproduce la derivación del potencial en el eje de un anillo de radio R.  
2. Analiza el comportamiento de V(z) cuando z \to 0 (punto en el centro del anillo) y cuando z \to \infty.  
3. Interpreta físicamente por qué el potencial se acerca a un valor finito en el centro y tiende a cero en el infinito.

{% endtab %}

{% tab prompts_cargas_continuas prompt-2 %}
**Ejercicio 2: Barra uniformemente cargada**

1. Considera una barra delgada de longitud L, con densidad lineal de carga \lambda.  
2. Calcula el potencial en un punto P situado sobre el eje perpendicular que pasa por uno de los extremos de la barra.  
3. Discute cómo simplificar el resultado cuando P está muy lejos de la barra, comparándolo con una sola carga puntual equivalente.

{% endtab %}
{% endtabs %}

---

# Campo eléctrico y potencial

El **campo eléctrico** $$\vec{E}$$ y el **potencial eléctrico** $$V$$ están íntimamente relacionados. El campo puede obtenerse **derivando** el potencial en el espacio, o el potencial puede encontrarse a partir de la **integral** del campo. Más formalmente, el **campo eléctrico** se asocia a la **pendiente negativa** del potencial:

$$
\vec{E} \;=\; - \nabla V,
$$

donde $$\nabla$$ (nabla) es el operador **gradiente**. De esta relación se desprenden varias conclusiones:

1. **Superficies equipotenciales**:  
   - Son las superficies donde $$V = \text{constante}$$.  
   - En estas superficies, el trabajo para mover una carga es **cero**, pues no hay cambio de energía potencial.  
2. **Relación perpendicular**:  
   - El **campo eléctrico** es **perpendicular** a las superficies equipotenciales, dirigiéndose desde las regiones de **mayor** potencial a las de **menor** potencial.  
3. **Reconstrucción**:  
   - Conociendo el campo, es posible **reconstruir** el potencial (hasta una constante) mediante integración.  
   - Conociendo el potencial, puede obtenerse el **campo** mediante derivadas espaciales.

{% tabs prompts_campo_y_potencial %}
{% tab prompts_campo_y_potencial prompt-1 %}
**Ejercicio 1: Obtención de \vec{E} a partir de V**

1. Dada la función de potencial V(x,y) = k(x^2 + y^2), encuentra \vec{E}(x,y) aplicando \vec{E} = -\nabla V.  
2. Identifica las **superficies equipotenciales** y explica cómo se distribuyen en el plano.  
3. Comprueba que \vec{E} sea perpendicular a esas superficies equipotenciales.

{% endtab %}

{% tab prompts_campo_y_potencial prompt-2 %}
**Ejercicio 2: De \vec{E} a V**

1. Supón que el campo eléctrico en una región está dado por \vec{E}(x) = E_0\,\hat{i} (constante en magnitud y dirección en el eje x).  
2. Integra \vec{E} para hallar el potencial V(x), escogiendo V = 0 en x = 0.  
3. ¿Por qué es posible afirmar que las líneas equipotenciales son planos perpendiculares a la dirección de \vec{E}?

{% endtab %}
{% endtabs %}

---

## Notación consistente

A lo largo de este documento, utilizamos:
- $$\vec{E}$$ para el **campo eléctrico** (vector).  
- $$V$$ para el **potencial eléctrico** (escalar).  
- $$\nabla V$$ para la operación de **gradiente** aplicada a $$V$$.  
- $$\epsilon_0$$ para la **permitividad** eléctrica del vacío.  
- $$k_e = \tfrac{1}{4\pi \epsilon_0}$$ para la constante de Coulomb.  
- $$q, Q, dq$$ para representar **carga(s)** en distintas escalas (puntual o diferencial).  

Estas definiciones se mantienen sin variación en todo el texto para evitar confusiones.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/EnriquedeltoPlaceholder.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>
