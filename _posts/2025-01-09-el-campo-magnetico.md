---
layout: distill
title: "Campo Magnético"
description: "Introducción al estudio del campo magnético y sus aplicaciones en ingeniería"
tags: [Electromagnetismo, Ingeniería, Fuerza de Lorentz, Biot-Savart, Ampère]
date: 2025-01-09
featured: false
giscus_comments: true

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

El **campo magnético** es un pilar fundamental de la física y la ingeniería eléctrica. Su estudio permite explicar fenómenos tan diversos como el comportamiento de imanes, la generación de fuerzas sobre cargas en movimiento y el funcionamiento de dispositivos cotidianos (motores, generadores, sensores, etc.). A lo largo de este texto se describen:

- Las **bases** teóricas del campo magnético y los principios físicos que lo sustentan.  
- Las **leyes** (Biot-Savart y Ampère) que permiten cuantificar el campo magnético en distintas configuraciones.  
- Las **aplicaciones** prácticas más relevantes en la industria, la ingeniería y la investigación científica.

Al concluir, se espera que el lector:

1. Comprenda el **origen** y la **naturaleza** del campo magnético.  
2. Sea capaz de **aplicar** la fuerza del campo magnético a casos concretos (corrientes, partículas cargadas, dispositivos).  
3. Reconozca la relevancia de fenómenos como el **Efecto Hall** y el **momento magnético** en espiras.  
4. Pueda **analizar** y **diseñar** sistemas donde intervenga el campo magnético (sensores, motores, etc.).

---

# Fuerza del campo magnético

Una de las manifestaciones más importantes del campo magnético es la **fuerza** que ejerce sobre cargas en movimiento y corrientes eléctricas. Este fenómeno se describe en términos de la **Fuerza de Lorentz**, que para la parte magnética se expresa como:

\[
\mathbf{F}_\text{magnética} = q \, (\mathbf{v} \times \mathbf{B}),
\]

donde:
- \(q\) es la carga eléctrica.
- \(\mathbf{v}\) es la velocidad de la partícula cargada.
- \(\mathbf{B}\) es el campo magnético.

Si en lugar de una partícula puntual consideramos un conductor con corriente, la fuerza se generaliza como:

\[
\mathbf{F} = I \, (\boldsymbol{\ell} \times \mathbf{B}),
\]

donde:
- \(I\) es la corriente eléctrica.  
- \(\boldsymbol{\ell}\) es el vector asociado a la longitud del conductor, con dirección del flujo de corriente.

El análisis de estas fuerzas explica el principio de funcionamiento de motores, **relés**, actuadores electromecánicos y la base de las trayectorias de cargas en campos magnéticos (p. ej. en tubos de rayos catódicos o aceleradores de partículas).

---

# Espiras e imanes

En el caso de **espiras** y **bobinas** recorridas por corriente, se define el **momento magnético**:

\[
\mathbf{m} = N \, I \, \mathbf{A},
\]

donde \(N\) es el número de espiras, \(I\) la corriente y \(\mathbf{A}\) el vector área (perpendicular al plano de la espira). Cuando se coloca este sistema en un campo magnético \(\mathbf{B}\), se induce un **torque**:

\[
\boldsymbol{\tau} = \mathbf{m} \times \mathbf{B},
\]

que tiende a alinear el momento magnético con el campo. Este mismo principio de **alineación** también explica por qué un **imán** (un dipolo magnético permanente) se orienta espontáneamente en la dirección del campo magnético. De esta forma se entiende, por ejemplo, el funcionamiento de una **brújula** o el comportamiento de imanes en motores de corriente continua.

---

# Efecto Hall

El **Efecto Hall** describe la aparición de una diferencia de potencial (voltaje Hall) en un conductor o semiconductor cuando circula una corriente en presencia de un campo magnético **perpendicular** a ella. Formalmente:

1. Aplicamos una **corriente** \(I\) a lo largo del eje \(x\).  
2. Un **campo magnético** \(\mathbf{B}\) se orienta en \(z\).  
3. Los portadores de carga (electrones en semiconductores tipo n, huecos en tipo p) experimentan una fuerza en la dirección \(y\).  
4. Esto crea un **acumulamiento de carga** que da origen a una **diferencia de potencial** en el eje \(y\), conocido como **voltaje Hall**.

Este fenómeno es crucial en la **medición de campos magnéticos** (sensores Hall), el **diagnóstico de semiconductores** y ciertos dispositivos de control y posición (encoders magnéticos, por ejemplo).

---

# Campo magnético debido a cargas en movimiento

Una **carga en movimiento** genera un **campo magnético** a su alrededor. En el caso más simple, la magnitud de ese campo puede analizarse como consecuencia de la **Ley de Biot-Savart** o de las **Ecuaciones de Maxwell**. De manera general:

- Si la carga viaja a velocidad constante, el campo magnético se distribuye en el espacio describiendo líneas de campo concéntricas alrededor de la trayectoria de la carga.  
- A velocidades relativistas, se requiere la formulación completa del electromagnetismo relativista para describir la **transformación** entre campos eléctricos y magnéticos en distintos sistemas de referencia.

En **circuitos cerrados**, la corriente neta (cargas en movimiento continuo) genera patrones de campo que pueden calcularse, lo que resulta clave en el diseño de **electroimanes** y **sistemas de bobinas** para controlar y guiar partículas (por ejemplo, en un **tokamak** de fusión nuclear).

---

# Ley de Biot y Savart

La **Ley de Biot-Savart** permite **calcular** el campo magnético \(\mathbf{B}\) generado por una corriente \(\mathbf{I}\) que circula a lo largo de un conductor. En su forma diferencial:

\[
d\mathbf{B} = \frac{\mu_0}{4\pi} 
               \frac{I \, d\mathbf{l} \times \hat{\mathbf{r}}}{r^2},
\]

donde:
- \(d\mathbf{l}\) es el elemento infinitesimal del conductor en la dirección de la corriente.  
- \(\hat{\mathbf{r}}\) es el vector unitario desde \(d\mathbf{l}\) hasta el punto de observación.  
- \(r\) es la distancia entre \(d\mathbf{l}\) y el punto de observación.  
- \(\mu_0\) es la permeabilidad del vacío.

**Aplicaciones** típicas:
- **Sistemas de bobinas** (cálculo del campo en el centro de una espira o solenoide).  
- **Diseño de sensores** y dispositivos que requieren campos magnéticos uniformes (p. ej. bobinas Helmholtz).  
- **Estudio de la densidad de campo** alrededor de cables conductores de potencia.

---

# Ley de Ampère

La **Ley de Ampère** es una de las expresiones más potentes y concisas para describir cómo se relaciona la **circulación** del campo magnético con la **corriente total** que atraviesa una superficie:

\[
\oint_{\mathcal{C}} \mathbf{B} \cdot d\mathbf{l} 
= \mu_0 \, I_{\text{enc}}.
\]

En esta forma clásica (magnetostática) se entiende que la circulación de \(\mathbf{B}\) a lo largo de una curva cerrada \(\mathcal{C}\) es proporcional a la corriente encerrada \(I_{\text{enc}}\) por dicha curva. Su **versión generalizada** (Ampère-Maxwell) incluye también la **corriente de desplazamiento**, crucial para analizar campos variables en el tiempo.

**Ejemplos de aplicación**:
- Cálculo del campo magnético en el **interior** y **exterior** de un cable largo con corriente uniforme.  
- Obtención de la intensidad de campo en el **centro** de un solenoide ideal.  
- Diseño de **blindajes magnéticos** y rutas de retorno de corriente en circuitos de alta potencia.

---

# Conclusiones

El **campo magnético** se manifiesta a través de fuerzas, torques y líneas de flujo que resultan determinantes en infinidad de aplicaciones tecnológicas. Aspectos clave tratados en este tema:

1. **Fuerza del campo magnético**: Base del funcionamiento de motores, generadores y dispositivos de control de partículas.  
2. **Espiras e imanes**: Principios de momento magnético y su relación con la generación de torque.  
3. **Efecto Hall**: Medición y detección de campos magnéticos mediante un voltaje transversal.  
4. **Campo magnético de cargas en movimiento**: Indispensable para diseñar dispositivos como electroimanes y guías de haces de partículas.  
5. **Ley de Biot y Savart**: Herramienta fundamental para el cálculo detallado del campo en geometrías específicas.  
6. **Ley de Ampère**: Método integral para relacionar la circulación del campo magnético con la corriente que lo origina.

El dominio de estas leyes y fenómenos es esencial tanto en **investigación** como en **práctica industrial**, sentando las bases para el diseño de máquinas eléctricas, sistemas de control magnético y tecnologías de vanguardia en física de altas energías y robótica.