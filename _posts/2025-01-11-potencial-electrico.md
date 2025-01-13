---
layout: post
title: "Potencial eléctrico"
description: "Introducción al estudio del potencial eléctrico y sus aplicaciones en ingeniería"
tags: [Electromagnetismo, Ingeniería, Fuerza de Lorentz, Biot-Savart, Ampère]
date: 2025-01-11
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

En esta sección, exploraremos el concepto de **potencial eléctrico** y su importancia en el estudio del electromagnetismo y la ingeniería. A diferencia del **campo eléctrico**, que describe la fuerza por unidad de carga en un punto del espacio, el **potencial eléctrico** se asocia a la energía por unidad de carga. Esta perspectiva basada en la energía resulta de gran utilidad para analizar y diseñar dispositivos y sistemas eléctricos y electrónicos, ya que:

- Permite describir el **trabajo** necesario para mover cargas de un punto a otro dentro de un campo eléctrico.  
- Facilita el estudio y la **simulación** de campos eléctricos en sistemas complejos, gracias a la superposición de potenciales.  
- Constituye la base de muchos cálculos en componentes como **condensadores**, **baterías** y otros sistemas de almacenamiento y distribución de energía.

El objetivo principal de esta sección es comprender la definición y el cálculo del potencial eléctrico en diferentes configuraciones de cargas, tanto puntuales como continuas, y relacionarlo con el campo eléctrico.

---

# Diferencia de potencial

El **potencial eléctrico** en un punto se define como la **energía potencial eléctrica** por unidad de carga necesaria para llevar una carga de prueba desde una posición de referencia (generalmente el infinito) hasta ese punto, **sin** alterar la configuración de las cargas que crean el campo.

**Diferencia de potencial (ddp)** entre dos puntos A y B:  

$$
V_B - V_A \;=\; - \int_{A}^{B} \vec{E} \cdot d\vec{r}
$$

Donde:  
- $$\vec{E}$$ es el campo eléctrico.  
- $$d\vec{r}$$ es el vector infinitesimal de desplazamiento desde A hasta B.  
- La integral se realiza a lo largo de un camino que va de A hasta B.  

En muchos casos, se selecciona el potencial igual a cero en el infinito ($$V(\infty) = 0$$), de modo que el **potencial en un punto P** puede expresarse como:

$$
V(P) \;=\; - \int_{\infty}^{P} \vec{E} \cdot d\vec{r}
$$

---

# Potencial debido a cargas puntuales

Cuando se trata de **cargas puntuales**, el potencial eléctrico resultante en un punto se obtiene mediante la **suma escalar** de los potenciales debidos a cada carga individual. Para una **carga puntual** $$q$$ situada en el origen, el **potencial** en un punto que está a una distancia $$r$$ de dicha carga es:

$$
V = k_e \,\frac{q}{r}
$$

donde
- $$k_e = \frac{1}{4\pi \epsilon_0} \approx 9 \times 10^9 \ \text{N}\cdot\text{m}^2/\text{C}^2$$,
- $$\epsilon_0$$ es la permitividad eléctrica del vacío.

**Superposición de potenciales**  
Si se tienen varias cargas puntuales $$q_1, q_2, \ldots, q_n$$ y se desea calcular el potencial en un punto P, la **superposición** establece que:

$$
V_{\text{total}}(P) \;=\; \sum_{i=1}^{n} k_e \,\frac{q_i}{r_i}
$$

donde $$r_i$$ es la distancia desde la carga $$q_i$$ al punto P.

---

# Potencial eléctrico debido a cargas continuas

Para distribuciones **no puntuales** de carga (por ejemplo, líneas, superficies o volúmenes cargados), el **potencial eléctrico** se calcula integrando la contribución de todos los elementos diferenciales de carga $$dq$$. La expresión general es:

$$
V(\vec{r}) \;=\; k_e \int \frac{dq}{|\vec{r} - \vec{r}\,'|}
$$

donde
- $$\vec{r}$$ es la posición del punto de observación,
- $$\vec{r}\,'$$ es la posición del elemento de carga diferencial $$dq$$,
- $$\lvert \vec{r} - \vec{r}\,'\rvert$$ es la distancia entre ambos.

### Ejemplo de cálculo: anillo cargado

Consideremos un **anillo** de radio $$R$$ con **carga total** $$Q$$ distribuida uniformemente (densidad lineal $$\lambda$$). El **potencial eléctrico** en un punto $$P$$ sobre el eje del anillo, a una distancia $$z$$ de su centro, viene dado por:

$$
V(z) = k_e \,\frac{Q}{\sqrt{z^2 + R^2}}
$$

Este resultado se obtiene sumando (integrando) la contribución de cada elemento diferencial de carga $$\lambda \, dl$$ que compone el anillo.

---

# Campo eléctrico y potencial

El **campo eléctrico** y el **potencial eléctrico** están íntimamente relacionados. El campo puede obtenerse derivando el potencial en el espacio, o el potencial puede encontrarse a partir de la integral del campo. Más formalmente, el **campo eléctrico** se asocia a la **pendiente negativa** del potencial:

$$
\vec{E} = - \nabla V
$$

donde $$\nabla$$ (nabla) es el operador gradiente. De esta relación se desprenden varias conclusiones:

1. **Las superficies equipotenciales** son aquellas donde $$V = \text{constante}$$. En estas superficies, el trabajo para mover una carga es **cero**, pues no hay cambio de energía potencial.  
2. El **campo eléctrico** es **perpendicular** a las superficies equipotenciales, dirigiéndose desde las regiones de mayor potencial a las de menor potencial.  
3. Una vez conocido el campo, es posible **reconstruir** el potencial (hasta una constante) mediante integración; y conociendo el potencial, puede obtenerse el **campo** mediante derivadas espaciales.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/EnriquedeltoPlaceholder.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=false %}
    </div>
</div>

---

{% tabs prompts_potencial_electrico %}
{% tab prompts_potencial_electrico prompt-1 %}

Eres un profesor de física que quiere que sus estudiantes comprendan la **relación entre el trabajo y el potencial eléctrico**. Diseña un ejercicio donde:
1. Se presente una **carga puntual** $$q$$ y un punto inicial A y un punto final B.
2. Se indique la **distancia** de cada punto hasta la carga.
3. Se pida al estudiante **calcular** la diferencia de potencial $$V_B - V_A$$.
4. Se solicite que el estudiante **explique** por qué esto se relaciona con el **trabajo realizado** al mover una carga de prueba entre A y B.

{% endtab %}
{% tab prompts_potencial_electrico prompt-2 %}

Crea un problema enfocado en la **superposición de potenciales** de **dos cargas puntuales**:
1. Se tienen dos cargas $$q_1$$ y $$q_2$$ en posiciones dadas.
2. Se pide al estudiante **hallar el potencial eléctrico** en un punto $$P$$ del espacio.
3. Solicita una **explicación** de por qué en el potencial se hace una **suma escalar** (y no vectorial) de los aportes de cada carga.

{% endtab %}
{% tab prompts_potencial_electrico prompt-3 %}

Genera un ejercicio sobre el **potencial de un anillo cargado**:
1. Indica un **anillo** de radio $$R$$ con **carga total** $$Q$$.
2. Pide al estudiante **derivar** la expresión del potencial en un punto a una distancia $$z$$ a lo largo del eje del anillo.
3. Solicita al estudiante que **analice** cómo el potencial varía al **acercarse** o **alejarse** del centro del anillo sobre dicho eje.

{% endtab %}
{% tab prompts_potencial_electrico prompt-4 %}

Diseña un ejercicio que requiera el uso de **integrales** para el cálculo del potencial en una **barra cargada**:
1. Presenta una **barra** de longitud $$L$$ con **densidad lineal de carga** $$\lambda$$.
2. Pide al estudiante **calcular** el potencial en un punto $$P$$ situado sobre la perpendicular que pasa por un extremo de la barra.
3. Solicita una **comparación** de resultados en dos casos:  
   - Cuando el punto $$P$$ está **muy lejano** (aproximación de carga puntual).  
   - Cuando el punto $$P$$ está **cerca** de la barra.

{% endtab %}
{% tab prompts_potencial_electrico prompt-5 %}

Crea un problema que conecte la **relación** entre **campo eléctrico** y **potencial**:
1. Indica una **función de potencial** $$V(x, y)$$ sencilla, por ejemplo $$V(x,y) = k(x^2 + y^2)$$.
2. Pide al estudiante que **calcule** el campo eléctrico $$\vec{E} = -\nabla V$$.
3. Solicita **identificar** las líneas de campo y las **superficies equipotenciales**.
4. Pide un comentario sobre por qué las líneas de campo eléctrico son perpendiculares a las superficies equipotenciales.

{% endtab %}
{% endtabs %}
