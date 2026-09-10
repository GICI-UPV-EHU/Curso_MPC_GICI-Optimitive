<p align="center">
  <img src="https://raw.githubusercontent.com/GICI-UPV-EHU/Imagenes_GICI/main/logos/Delfin03-Naranja-T6.png"
       alt="GICI"
       width="180">
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://raw.githubusercontent.com/GICI-UPV-EHU/Imagenes_GICI/main/logos/EHU_logotipo_positiboa_ALTUA.png"
       alt="UPV/EHU"
       width="150">
</p>

<h1 align="center">Ejercicios prácticos — Curso de Control Predictivo basado en Modelo (MPC)</h1>

<p align="center">
Material práctico del curso <strong>Curso MPC GICI–Optimitive</strong>.
</p>

---

## Notebooks disponibles

Las prácticas se ejecutarán en **Google Colab**, por lo que no es necesario instalar Python ni configurar un entorno local.

| Práctica | Notebook | Abrir |
|---|---|---|
| **1 — MAC** | `Practica_01_MAC_Optimitive.ipynb` | <a href="https://colab.research.google.com/github/GICI-UPV-EHU/Curso_MPC_GICI-Optimitive/blob/main/04_Ejercicios/Practica_01_MAC_Optimitive.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Abrir en Colab"></a> |
| **2 — DMC** | `Practica_02_DMC_Optimitive.ipynb` | <a href="https://colab.research.google.com/github/GICI-UPV-EHU/Curso_MPC_GICI-Optimitive/blob/main/04_Ejercicios/Practica_02_DMC_Optimitive.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Abrir en Colab"></a> |
| **3 — GPC** | `Practica_03_GPC_Optimitive.ipynb` | <a href="https://colab.research.google.com/github/GICI-UPV-EHU/Curso_MPC_GICI-Optimitive/blob/main/04_Ejercicios/Practica_03_GPC_Optimitive.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Abrir en Colab"></a> |
| **3 — GPC (enfoque práctico)** | `Practica_03_GPC_enfoque_practico.ipynb` | <a href="https://colab.research.google.com/github/GICI-UPV-EHU/Curso_MPC_GICI-Optimitive/blob/main/04_Ejercicios/Practica_03_GPC_enfoque_practico.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Abrir en Colab"></a> |

---

## Antes de comenzar

Para trabajar con las prácticas únicamente necesitas:

- un navegador web actualizado;
- conexión a Internet;
- una cuenta de Google;
- acceso a este repositorio.

No es necesario instalar **Python**, **Jupyter Notebook** ni ninguna librería en el ordenador.

> [!IMPORTANT]
> Los notebooks del repositorio son el material original del curso.  
> Cada asistente debe trabajar sobre **su propia copia en Google Drive**.

---

## Cómo trabajar con los notebooks

### 1. Abrir la práctica

Pulsa el botón **Open in Colab / Abrir en Colab** correspondiente a la práctica.

El notebook se abrirá en Google Colab directamente desde GitHub.

### 2. Guardar una copia personal

Antes de modificar o ejecutar la práctica, guarda una copia en tu Google Drive:

**Archivo → Guardar una copia en Drive**

El nombre de la opción puede variar ligeramente según el idioma de la interfaz de Google Colab.

A partir de ese momento, trabaja siempre sobre **tu copia personal**.

> [!WARNING]
> Los cambios realizados sobre el notebook abierto directamente desde GitHub **no se guardan en este repositorio**.

### 3. Conectar el entorno de ejecución

En la zona superior derecha de Colab pulsa **Conectar**.

Los notebooks utilizan una CPU estándar; **no es necesario activar GPU**.

### 4. Ejecutar las celdas en orden

Las celdas de código se ejecutan mediante el botón ▶ situado a la izquierda de cada celda o con:

```text
Shift + Enter
```

Durante el curso se recomienda ejecutar el notebook **secuencialmente, de arriba hacia abajo**.

Esto es importante porque muchas celdas utilizan variables y funciones definidas anteriormente.

### 5. Ejecutar inicialmente las celdas de preparación

Al comienzo de algunos notebooks pueden aparecer celdas destinadas a:

- importar librerías;
- definir funciones auxiliares;
- establecer el modelo de la planta;
- configurar parámetros iniciales.

Ejecuta estas celdas antes de comenzar los experimentos.

Si Colab solicita instalar alguna dependencia, espera a que finalice la instalación antes de continuar.

---

## Durante los ejercicios

Las prácticas están planteadas para **experimentar con los parámetros del controlador** y observar cómo cambia el comportamiento del sistema.

Durante la sesión modificaremos, entre otros, parámetros como:

- horizonte de predicción;
- ponderación de la acción de control;
- longitud del modelo;
- parámetros del modelo de predicción;
- referencia;
- perturbaciones.

La secuencia de trabajo recomendada es:

```text
1. Ejecutar el caso base
        ↓
2. Observar salida y acción de control
        ↓
3. Modificar un único parámetro
        ↓
4. Ejecutar de nuevo
        ↓
5. Comparar los resultados
        ↓
6. Explicar por qué ha cambiado el comportamiento
```

> [!TIP]
> Modifica **un parámetro cada vez**. De esta forma será mucho más sencillo relacionar el cambio realizado con el efecto observado.

---

## Preguntas y respuestas desplegables

En diferentes puntos de los notebooks encontrarás preguntas destinadas a discutir los resultados obtenidos.

Intenta responderlas **antes de desplegar la solución**.

El objetivo de estas preguntas no es únicamente obtener una respuesta correcta, sino relacionar los resultados de la simulación con los conceptos de MPC vistos durante la sesión.

---

## Si modificas una celda y quieres volver al caso original

Tienes varias alternativas:

1. deshacer el cambio con `Ctrl + Z`;
2. volver a cargar tu copia guardada en Google Drive;
3. abrir de nuevo el notebook original desde el botón **Abrir en Colab** de este README.

El notebook almacenado en este repositorio permanecerá sin modificar.

---

## Si el entorno de Colab se reinicia o desconecta

Google Colab utiliza sesiones temporales.

Si el entorno se desconecta o se reinicia:

1. vuelve a pulsar **Conectar**;
2. ejecuta nuevamente las celdas desde el comienzo;
3. continúa desde el experimento en el que estabas trabajando.

Las variables almacenadas en memoria se pierden al reiniciar el entorno, pero **los cambios realizados en el notebook sí permanecerán en tu copia de Google Drive** siempre que la hayas guardado.

---

## Reiniciar completamente una práctica

Si durante las modificaciones el estado del notebook deja de estar claro, puedes reiniciar el entorno:

**Entorno de ejecución → Reiniciar sesión**

y después ejecutar nuevamente las celdas desde el principio.

Esta suele ser la forma más sencilla de recuperar un estado conocido de la simulación.

---

## Descargar una copia del notebook

Si deseas conservar el fichero fuera de Google Drive puedes descargarlo desde Colab mediante:

**Archivo → Descargar → Descargar `.ipynb`**

Posteriormente podrá abrirse de nuevo con Google Colab, Jupyter Notebook o JupyterLab.

---

## Orden recomendado

Para seguir el desarrollo del curso, se recomienda trabajar con las prácticas en este orden:

1. **MAC — Model Algorithmic Control**
2. **DMC — Dynamic Matrix Control**
3. **GPC — Generalized Predictive Control**

La práctica adicional **GPC — enfoque práctico** permite trabajar específicamente con una aproximación orientada a la interpretación y experimentación del controlador.

---

## Idea de trabajo

No es necesario comprender cada línea de Python para aprovechar las prácticas.

El objetivo principal es entender la lógica común de las estrategias MPC:

```text
MODELO
   ↓
PREDICCIÓN DEL FUTURO
   ↓
FUNCIÓN DE COSTE
   ↓
OPTIMIZACIÓN
   ↓
SECUENCIA DE CONTROL ÓPTIMA
   ↓
APLICAR SOLO LA PRIMERA ACCIÓN
   ↓
MEDIR DE NUEVO Y REPETIR
```

A lo largo de MAC, DMC y GPC cambia la forma de construir el **modelo y el predictor**, pero se mantiene esta filosofía de **horizonte deslizante**.

---

<p align="center">
<strong>GICI — Grupo de Inteligencia Computacional</strong><br>
Universidad del País Vasco / Euskal Herriko Unibertsitatea — UPV/EHU
</p>
