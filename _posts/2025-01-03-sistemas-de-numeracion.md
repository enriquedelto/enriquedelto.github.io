---
layout: distill
title: "La unidad aritmético lógica (ALU)"
description:
tags: [TAG1, TAG2, ...]
giscus_comments: true
date: 2025-01-03
featured: false

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
  # - name: "OTRO_AUTOR"
  #   url: "URL_DEL_AUTOR"
  #   affiliations:
  #     name: "AFILIACIÓN_DEL_AUTOR"

bibliography: "ARCHIVO_DE_BIBLIOGRAFÍA.bib"

toc:
  - name: "SECCIÓN_1"
    # subsections:
    #   - name: "SUBSECCIÓN_1"
    #   - name: "SUBSECCIÓN_2"
  - name: "SECCIÓN_2"
  - name: "SECCIÓN_3"
  - name: "SECCIÓN_4"
  # Agrega o elimina secciones según necesites

# Estilos específicos del post (opcional)
_styles: >
  .fake-img {
    background: #bbb;
    border: 1px solid rgba(0, 0, 0, 0.1);
    box-shadow: 0 0px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
  }
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: center;
    margin: 12px 0;
    font-size: 16px;
  }
---

# **Introducción**

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec placerat diam et tortor accumsan, a porttitor nisi ornare.

## **La unidad aritmético-lógica**

La Unidad Aritmético-Lógica (ALU) es el componente de la CPU encargado de realizar operaciones lógicas manipulando datos binarios. A partir de estas operaciones lógicas, se realiza una abstracción a nivel de diseño, aplicando conocimientos de [álgebra de Boole](URL_ALGEBRA_DE_BOOLE), [lógica combinacional](URL_LOGICA_COMBINACIONAL), [teoría de números](URL_TEORIA_DE_NUMEROS) y [diseño de circuitos digitales](URL_DISENO_CIRCUITOS) para que el resultado simule operaciones aritméticas.

Para comprender mejor este tema, es recomendable familiarizarse con los conceptos mencionados previamente, ya que forman la base para entender el funcionamiento de la ALU en detalle.

---

### **Arquitectura e interconexión de la ALU en un sistema digital**

La ALU es suministrada de datos que indican el **tipo de operación**, **la operación específica**, **los operandos** y **el acarreo**.

Como ejemplo, usaremos el [**DM74LS181 4-Bit Arithmetic Logic Unit**](https://www.alldatasheet.es/datasheet-pdf/download/51044/FAIRCHILD/DM74LS181.html).

---

#### **Inputs de la ALU**

**Señales suministradas por la [Unidad de Control]()**:

- **Function Select (S0-S3)**: Seleccionan la operación específica a realizar (son 4 bits que permiten elegir entre 16 operaciones diferentes).  
- **Mode Control (M)**: Define si la operación es lógica (**M = 1**) o aritmética (**M = 0**).  
- **Carry In (Cn)**: Bit de acarreo de entrada, usado en operaciones aritméticas para introducir un valor extra en la suma/resta (por ejemplo, al realizar [complementos a 2]() para restas).  
  - Este acarreo puede provenir de la unidad de control o de la salida de otra ALU en operaciones de varias ALUs en cascada.

**Señales suministradas por los [Registros]()**:

- **A (A0–A3)**: Primer operando de 4 bits.  
- **B (B0–B3)**: Segundo operando de 4 bits.

**Nota sobre la habilitación de registros:**  
Aunque los datos de los operandos A y B provienen de los registros, la unidad de control es la encargada de:  
1. **Habilitar los registros** para que liberen sus datos hacia la ALU.  
2. **Indicar** cuándo debe realizarse la operación.

Tras procesar las señales de entrada, la ALU genera señales de salida que se envían tanto a los registros de datos como a otros componentes para la toma de decisiones de la unidad de control:

---

#### **Outputs de la ALU**

**Señales dirigidas a los registros de datos y memoria**:

- **F (F0–F3)**: Resultado de la operación realizada (4 bits).  
  - **Almacenamiento temporal**: La unidad de control puede almacenar este resultado temporalmente en los registros de datos si el valor se necesita para operaciones posteriores.  
  - **Almacenamiento definitivo**: Si no se requiere continuar procesando el dato, la unidad de control habilita la transferencia hacia la RAM para su almacenamiento permanente.  
  - Este envío a la RAM se realiza a través del bus de datos, bajo la coordinación de la unidad de control.

**Señales dirigidas a indicadores de estado (flags) de la unidad de control**:

Estas señales indican condiciones específicas del resultado de la operación y se dirigen a la Unidad de Control para modificar el flujo de ejecución según sea necesario:

- **Cn+4 (Carry Out)**:
  - Indica si se ha producido un acarreo en una operación de suma o un "préstamo" en una resta.
  - Puede ser utilizado como entrada de acarreo (**Cn**) en operaciones de varias ALUs o para actualizar el flag de carry del registro de estado.

- **P (Carry Propagate)**:
  - Indica si el resultado de la operación propaga un acarreo si hay un acarreo entrante.
  - Se utiliza en configuraciones de carry lookahead para acelerar las operaciones.

- **G (Carry Generate)**:
  - Indica si la operación genera un acarreo de manera inmediata, independientemente del acarreo entrante.

- **A = B**:
  - Va a 1 cuando los operandos A y B son iguales, indicando una comparación exitosa.
  - Este indicador se usa para verificar condiciones de salto condicional (por ejemplo, "salta si igual").