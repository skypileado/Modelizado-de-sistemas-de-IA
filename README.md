# Modelizado de sistemas de IA

# Practica 1
Esta práctica aplica **IA Clásica** para resolver dos problemas en una obra:

1. **Misión A (Seguridad):** Usa la librería `experta` como un motor de reglas. Si los sensores detectan peligro extremo (viento $> 60\ km/h$ o grietas), la regla con máxima prioridad (`salience=100`) se activa inmediatamente y frena todo. En la prueba, el sistema ordenó con éxito el **"PARO TOTAL DE OBRA"**.
2. **Misión B (Logística):** Usa `python-constraint` para asignar 3 máquinas a 3 zonas sin que colisionen ni violen normas de seguridad. El algoritmo descarta las opciones incorrectas y encuentra **la única combinación segura**: Grúa en *Zona_Estable*, Hormigonera en *Zona_Estrecha* y Excavadora en *Zona_Comun*.

# Practica 2
Este script usa un **Algoritmo Genético** (`pygad`) para organizar un calendario de construcción eficiente.

* **El Objetivo:** Iniciar **10 tareas** en el menor tiempo posible, sin usar nunca más de **10 operarios por día**.
* **¿Cómo funciona?** El algoritmo prueba miles de calendarios (individuos) donde cada gen es el día de inicio de una tarea.
* **La Clave (Penalización):** Si un calendario junta muchas tareas en paralelo y supera los 10 operarios, su nivel de aptitud (*fitness*) cae a cero para ser descartado inmediatamente.
* **Resultado:** En la simulación, la IA logró acomodar perfectamente las tareas para terminar la casa en solo **16 días**, respetando siempre el límite de personal.

# Practica 3
Este script utiliza **Lógica Difusa (Fuzzy Logic)** (`skfuzzy`) para automatizar el **frenado autónomo de emergencia** de un vehículo inteligente.

* **El Objetivo:** Calcular la **Fuerza de Frenado** óptima basándose en la **Distancia** al obstáculo y la **Velocidad** del auto.
* **¿Cómo funciona?** 1. **Fuzzificación:** Convierte los datos de los sensores en etiquetas como *"Cerca"*, *"Lejos"*, *"Baja"* o *"Alta velocidad"*.
2. **Reglas Difusas:** Evalúa sentencias lógicas (ej. *SI la distancia es "Muy Cerca" Y la velocidad es "Alta", ENTONCES el freno es "Crítico"*).
3. **Defuzzificación:** Procesa las reglas activadas y devuelve un porcentaje exacto de presión de freno (ej. **78.47%**).
* **Resultado:** Ante un peligro inminente (obstáculo a 8 metros y viajando a 90 km/h), el sistema reacciona con precisión ordenando un **frenado intenso del 78.47%** para evitar el choque.

# Practica 4 
Este script aplica el algoritmo **A*** (A-Estrella) para que un robot de rescate esquive escombros y salve a una víctima.

* **El Objetivo:** Encontrar la **ruta más corta y segura** en un mapa cuadriculado con obstáculos.
* **¿Cómo funciona?** El algoritmo decide qué casilla pisar usando una fórmula inteligente:

$$f(n) = g(n) + h(n)$$


* $g(n)$: Pasos dados desde el inicio.
* $h(n)$: Distancia estimada en línea recta hasta la víctima (Heurística).


* **Resultado:** El algoritmo calcula la ruta óptima, dibuja el mapa con los obstáculos y traza el camino exacto para el rescate.
