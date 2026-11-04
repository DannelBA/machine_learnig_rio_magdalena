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

Al ejecutar el notebook se genera o sobrescribe `filtrada.csv` después de construir los predictores y objetivos. Para este experimento se excluyen ceros, niveles mayores a 12 m e historiales con intervalos superiores a 8 horas entre las seis lecturas recientes. El CSV contiene una fila por origen, 17 predictores y objetivos de máximo observado para nueve horizontes. Los filtros de 12 m y 8 horas son decisiones experimentales, no criterios oficiales de IDEAM.