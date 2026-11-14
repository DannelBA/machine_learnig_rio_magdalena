# machine_learnig_rio_magdalena

# Predicción del nivel máximo del río Magdalena

Experimento de aprendizaje de machine learning con datos del IDEAM.

## Requisitos
- Python 3.14.2

## Cómo ejecutarlo
1. Crear un entorno: `python -m venv .venv`
2. Activarlo y instalar: `pip install -r requirements.txt`
3. Abrir `prediccion_rio_magdalena.ipynb` y ejecutar todas las celdas

## Datos
Fuente: IDEAM, Datos Abiertos Colombia. [Nivel Máximo del Río](https://www.datos.gov.co/Ambiente-y-Desarrollo-Sostenible/Nivel-M-ximo-del-Rio/vfth-yucv), estación EL BANCO - AUT.

Al ejecutar el notebook se genera `filtrada.csv`, la única base usada para el modelado. Excluye ceros y niveles mayores a 12 m. Contiene 11 predictores (nivel actual, seno y coseno del día del año, máximo de las últimas 8, 24, 72 y 168 h, y la diferencia entre el nivel actual y cada uno de esos máximos) y los objetivos de máximo observado para las próximas 8 horas, 1 día, 3 días y 1 semana.

Los modelos (Ridge, árbol de decisión, Random Forest, MLP y DNN) predicen el cambio respecto al nivel actual, se ajustan con GridSearchCV usando validación cronológica purgada de tres pliegues y se comparan en el 20 % final de los datos contra dos líneas base: repetir el nivel actual y repetir el máximo de las últimas horas.

La ejecución completa tarda entre 20 y 50 minutos según el equipo, principalmente por las búsquedas de Random Forest y de las redes neuronales.