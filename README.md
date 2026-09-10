<p align="center">
  <img src="https://raw.githubusercontent.com/GICI-UPV-EHU/Imagenes_GICI/main/logos/Delfin03-Naranja-T6.png"
       alt="GICI"
       width="180">
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://raw.githubusercontent.com/GICI-UPV-EHU/Imagenes_GICI/main/logos/EHU_logotipo_positiboa_ALTUA.png"
       alt="UPV/EHU"
       width="150">
</p>

<h1 align="center">Fundamentos del Control Predictivo basado en Modelo y su uso en la industria</h1>

Material del curso formativo dedicado a los **fundamentos del Model Predictive Control (MPC)**, con especial énfasis en su interpretación práctica, su relación con las primeras formulaciones industriales y su implementación mediante ejemplos ejecutables.

El objetivo del repositorio es que pueda utilizarse **durante las sesiones del curso y posteriormente como material de consulta y experimentación**.

---

## Objetivos del curso

Al finalizar el curso, el participante debería ser capaz de:

- comprender la filosofía general del **Control Predictivo basado en Modelo**;
- identificar los elementos comunes de una estrategia MPC: **modelo, predicción, función de coste, optimización y horizonte deslizante**;
- entender las diferencias entre distintas formulaciones predictivas;
- interpretar el efecto de parámetros como el **horizonte de predicción** y las **ponderaciones de la función de coste**;
- implementar y analizar controladores predictivos sencillos;
- comprender cómo se incorporan **sistemas multivariables, perturbaciones y restricciones**.

El enfoque del curso será fundamentalmente **práctico e intuitivo**, introduciendo la formulación matemática necesaria a medida que se utilice en los ejemplos.

---

## Programa

### Día 1 — Concepción y sistemas monovariables

1. **Introducción al MPC**
   - Motivación y fundamentos.
   - Predicción del comportamiento futuro.
   - Optimización.
   - Horizonte deslizante.
   - Diferencias conceptuales entre PID y MPC.

2. **Model Algorithmic Control (MAC)**
   - Modelo basado en la **respuesta impulsional**.
   - Predicción libre y forzada.
   - Función de coste.
   - Cálculo de la acción de control.
   - Influencia de los parámetros de ajuste.

3. **Dynamic Matrix Control (DMC)**
   - Modelo basado en la **respuesta escalón**.
   - Construcción de la matriz dinámica.
   - Predicción libre y forzada.
   - Función de coste y ley de control.
   - Influencia del horizonte y de la penalización del esfuerzo de control.

4. **Generalized Predictive Control (GPC)**
   - Modelo mediante **función de transferencia**.
   - Introducción al modelo **CARIMA**.
   - Construcción del predictor.
   - Predicción sobre el horizonte.
   - Función de coste y acción de control.

### Día 2 — Sistemas multivariables y restricciones

5. **MPC basado en modelos de espacio de estados**
   - Formulación SISO.
   - Formulación MIMO.
   - Horizontes de predicción y de control.

6. **Extensión a sistemas multivariables**
   - Interpretación de los acoplamientos.
   - DMC y GPC en sistemas MIMO.

7. **Perturbaciones**
   - Perturbaciones medibles.
   - Perturbaciones no medibles.
   - Corrección del error de predicción.

8. **Restricciones y estabilidad**
   - Restricciones sobre entradas, incrementos de entrada y salidas.
   - Introducción a la optimización cuadrática.
   - Conceptos básicos de estabilidad en MPC.

---

## Material práctico

El repositorio contiene notebooks interactivos que se utilizarán durante el curso.

En la primera sesión trabajaremos principalmente con:

| Práctica | Estrategia | Modelo utilizado |
|---|---|---|
| 1 | **MAC** | Respuesta impulsional |
| 2 | **DMC** | Respuesta escalón |
| 3 | **GPC** | Función de transferencia / CARIMA |

Los notebooks están diseñados para que puedan modificarse durante la explicación. A lo largo de cada práctica se propondrán pequeños experimentos del tipo:

- ¿qué ocurre si aumentamos el horizonte de predicción?
- ¿qué sucede al modificar la penalización de la acción de control?
- ¿cómo afecta un modelo demasiado corto o poco preciso?
- ¿qué diferencias aparecen entre una respuesta agresiva y una respuesta suave?
- ¿qué información necesita cada formulación para construir sus predicciones?

La intención no es únicamente ejecutar el código, sino **modificar parámetros, observar resultados y razonar el comportamiento del controlador**.

---

## Entorno de trabajo

Las prácticas están preparadas para ejecutarse con **Python en Google Colab**, por lo que no es necesario instalar previamente un entorno de Python en el ordenador.

Se recomienda disponer de:

- un navegador web actualizado;
- una cuenta de Google para poder guardar una copia propia de los notebooks;
- conocimientos básicos de sistemas de control y representación de sistemas dinámicos;
- conocimientos básicos de Python útiles, aunque no imprescindibles.

### Abrir un notebook en Google Colab

La forma recomendada de trabajar durante el curso es:

1. abrir el notebook correspondiente desde este repositorio;
2. abrirlo en **Google Colab**;
3. seleccionar `Archivo > Guardar una copia en Drive`;
4. trabajar sobre esa copia personal;
5. ejecutar las celdas secuencialmente desde el inicio.

También puede abrirse directamente un repositorio de GitHub desde Colab mediante:

`Archivo > Abrir cuaderno > GitHub`

y pegando la dirección de este repositorio.

> **Recomendación:** antes de comenzar cada práctica, ejecutar el notebook completo una vez para comprobar que todas las dependencias se cargan correctamente.

---

## Cómo utilizar los notebooks

Los notebooks combinan cuatro tipos de contenido:

**Explicación**  
Introduce las ideas necesarias para entender cada algoritmo.

**Código**  
Implementa los modelos, predictores y controladores.

**Experimentos**  
Permite modificar parámetros y observar su efecto sobre el comportamiento del sistema.

**Preguntas para discusión**  
Se utilizarán durante la sesión para analizar los resultados y relacionarlos con los conceptos teóricos.

No es necesario comprender inicialmente cada línea de código. El objetivo principal es entender la secuencia:

**modelo → predicción → optimización → aplicación de la primera acción → nueva predicción**

que constituye la idea central del MPC.

---

## Notación básica

A lo largo del curso aparecerán con frecuencia los siguientes símbolos:

| Símbolo | Significado |
|---|---|
| $u(k)$ | acción de control |
| $\Delta u(k)$ | incremento de la acción de control |
| $y(k)$ | salida medida del proceso |
| $\hat{y}(k+j\mid k)$ | salida predicha en el instante futuro $k+j$ |
| $r(k)$ | referencia |
| $h$ | horizonte de predicción |
| $h_u$ | horizonte de control |
| $\lambda$ | ponderación asociada al esfuerzo o variación de control |
| $N_t$ | longitud utilizada para truncar un modelo de convolución |

---

## Idea fundamental del MPC

Aunque existen muchas formulaciones diferentes, todas comparten la misma filosofía:

1. utilizar un **modelo** para predecir cómo evolucionará el sistema;
2. calcular una secuencia de acciones futuras que minimice una **función objetivo**;
3. considerar, cuando sea necesario, las **restricciones** del proceso;
4. aplicar únicamente la **primera acción de control** calculada;
5. medir de nuevo el sistema y repetir el proceso desplazando el horizonte.

Este mecanismo se denomina **Receding Horizon Control** o **control con horizonte deslizante**.

---

## Recomendaciones durante el curso

- Modifica los parámetros de los ejemplos: el objetivo es experimentar.
- Observa conjuntamente la **salida** y la **acción de control**.
- No valores un ajuste únicamente por la rapidez del seguimiento.
- Relaciona siempre el comportamiento obtenido con el **modelo empleado para predecir**.
- Compara MAC, DMC y GPC buscando primero sus similitudes y después sus diferencias.
- Si una simulación produce un resultado inesperado, revisa primero el modelo, los horizontes y las ponderaciones antes de modificar el algoritmo.

---

## Bibliografía recomendada

- E. F. Camacho, C. Bordons y J. M. Maestre, *Model Predictive Control*, 3rd ed., Springer, 2026.
- J. B. Rawlings, D. Q. Mayne y M. M. Diehl, *Model Predictive Control: Theory, Computation, and Design*, 2nd ed., 5th printing, Nob Hill Publishing, 2024.

Durante el curso se proporcionarán explicaciones y ejemplos suficientes para seguir las prácticas; estas referencias se recomiendan para profundizar posteriormente.

---

## Uso del material

Este repositorio está destinado al seguimiento del curso y al estudio posterior por parte de sus asistentes.

Los notebooks pueden contener código y material docente adaptado a partir de recursos previos. Antes de reutilizar o redistribuir el contenido fuera del contexto del curso, debe consultarse la licencia y la información de autoría incluida en el repositorio.

---

## Antes de empezar

Para la primera sesión únicamente necesitas:

1. acceso a este repositorio;
2. un navegador;
3. acceso a Google Colab;
4. ganas de modificar parámetros y comprobar qué ocurre.

**Empezaremos por MAC, continuaremos con DMC y terminaremos la primera parte práctica con GPC.**
