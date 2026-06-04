# Modelizado-de-sistemas-de-IA

# Practica 1
Esta práctica de laboratorio implementa dos soluciones de **Inteligencia Artificial Clásica** (Sistemas Basados en Conocimiento y Satisfacción de Restricciones) para automatizar la toma de decisiones y la seguridad en una obra en construcción.

Aquí te explico brevemente qué pasa en cada una de las dos misiones resueltas:

---

## Misión A: Diagnóstico de Seguridad (Motor de Inferencia)

En esta parte se utiliza la librería `experta` para crear un **Sistema Experto** que evalúa el nivel de riesgo climático y estructural de la obra.

* **¿Cómo funciona?** El sistema simula el pensamiento de un supervisor de seguridad mediante reglas lógicas (`@Rule`). Lee datos de sensores (viento, presencia de grietas, humedad) y determina si la obra debe continuar normalmente o detenerse.
* **La Clave Técnica:** Se configuró un parámetro llamado `salience=100` (prioridad) en la regla de **Riesgo Crítico**. Esto garantiza que si hay un peligro extremo (viento $> 60\ km/h$ o grietas), el motor detiene la obra inmediatamente antes de perder tiempo evaluando otras condiciones menores.
* **Resultado del test:** Se probó con viento de $65\ km/h$ y grietas activas, y el sistema arrojó con éxito el diagnóstico de **"PARO TOTAL DE OBRA"**.

---

## Misión B: Ubicación de Equipos (Problema de Satisfacción de Restricciones - CSP)

Aquí se utiliza la librería `python-constraint` para resolver un problema de logística: asignar **3 máquinas** (Grúa Torre, Excavadora, Hormigonera) a **3 zonas** de trabajo distintas sin que entren en conflicto.

El motor de búsqueda analiza todas las combinaciones posibles y "poda" (descarta) las que rompen las **Reglas de Oro**:

1. **Exclusividad:** No puede haber dos máquinas en la misma zona.
2. **Grúa Torre:** Obligatoriamente en la *Zona_Estable*.
3. **Excavadora:** No cabe en la *Zona_Estrecha*.
4. **Hormigonera:** No puede compartir espacio con la grúa para evitar tráfico.

* **Resultado:** El algoritmo descartó inteligentemente las opciones peligrosas y encontró **la única solución matemáticamente segura**:
* `Grua_Torre` $\rightarrow$ *Zona_Estable*
* `Hormigonera` $\rightarrow$ *Zona_Estrecha*
* `Excavadora` $\rightarrow$ *Zona_Comun*



---

### Lo que falta completar (Nota para tu entrega)

El enunciado de la práctica exige incluir una **Justificación Funcional** en celdas de texto explicando por qué estos enfoques son mejores que usar simples condicionales `if/else`.

> **Idea para tu justificación:** Si usaras `if/else` anidados, el código se volvería inmanejable, rígido y propenso a errores a medida que agregues más sensores o más máquinas. En cambio, con `experta` (árboles de decisión/algoritmo Rete) y `python-constraint` (grafos de restricciones), el motor de IA calcula las rutas y descartes óptimos de forma dinámica, haciendo el sistema escalable y fácil de mantener.
