# machine_learnig_rio_magdalena

# Predicción del nivel del río Magdalena

Experimento de aprendizaje de machine learning con datos del IDEAM.

## Requisitos
- Python 3.14.2

## Cómo ejecutarlo
1. Crear un entorno: `python -m venv .venv`
2. Activarlo y instalar: `pip install -r requirements.txt`
3. Abrir `prediccion_rio.ipynb` y ejecutar todas las celdas

## Datos
Fuente: IDEAM, Datos Abiertos Colombia. [dataset usado](https://www.datos.gov.co/Ambiente-y-Desarrollo-Sostenible/Nivel-Instant-neo-del-Rio/bdmn-sqnh/explore/query/SELECT%20%60fechaobservacion%60%2C%20%60valorobservado%60%0AWHERE%20caseless_one_of%28%60codigoestacion%60%2C%20"0025027020"%29/page/filter)