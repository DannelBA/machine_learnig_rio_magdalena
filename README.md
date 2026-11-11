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

Al ejecutar el notebook se genera `filtrada.csv`, la única base usada para el modelado. Excluye ceros, niveles mayores a 12 m e historiales con intervalos superiores a 8 horas entre las seis lecturas recientes. Contiene 11 predictores (seis niveles recientes y cinco intervalos) y objetivos de máximo observado para 8 horas, 1 día, 3 días y 1 semana. La sección de árboles de decisión compara el árbol con dos líneas base: el último nivel y el máximo observado en la ventana histórica equivalente. Random Forest se entrena aparte y agrega resultados a esa comparación. Las dos celdas finales separan la búsqueda de hiperparámetros: 20 configuraciones de árbol y 16 de Random Forest mediante validación cronológica purgada de tres bloques en cada horizonte; escogen por MAE de validación y luego informan las métricas del 20 % de prueba. Los filtros de 12 m y 8 horas son decisiones experimentales, no criterios oficiales de IDEAM.