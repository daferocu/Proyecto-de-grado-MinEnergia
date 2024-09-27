# Titulo de la Solución: Proyecto analítico de predicción de costo unitario de energía en Colombia en el sector residencial  

>Este documento presenta la decripción de la solución, la arquitectura y las principales consideraciones y pasos requeridos para realizar el despliegue e instalación del proyecto. 

Tambien, en el siguientes links se encuentran la informacion documental asociada al proyecto: 

[Carpeta Asociada a Protocolo de Informacion de Equipo](https://livejaverianaedu-my.sharepoint.com/:f:/g/personal/pa_castro_javeriana_edu_co/ErlQ_hKjBOxAnsgC1RHSwdEBbZKuS5rvswKs8toX6o5aEg?e=0d0J5V) 


[Informe Proyecto](https://gitlab.com/CAOBA-Central/pruebas-concepto/puj-bogota/pruebas-concepto-g9/poc-071-minenergia-prediccion-costo-unitario-fase1/-/blob/develop/docs/Informe%20Proyecto/Entrega%201/Proyecto%20anal%C3%ADtico%20de%20predicci%C3%B3n%20de%20costo%20unitario%20de%20energ%C3%ADa%20en%20Colombia%20en%20el%20sector%20residencial.docx?ref_type=heads)

[Manual de Usuario](https://gitlab.com/CAOBA-Central/pruebas-concepto/puj-bogota/pruebas-concepto-g9/poc-071-minenergia-prediccion-costo-unitario-fase1/-/tree/develop/docs/manual%20usuario?ref_type=heads) 

[Video Demo](https://gitlab.com/CAOBA-Central/pruebas-concepto/puj-bogota/pruebas-concepto-g9/poc-071-minenergia-prediccion-costo-unitario-fase1/-/tree/develop/docs/video%20demo?ref_type=heads)

[Hacer copia y llenar plantilla de Comunicaciones](https://gitlab.com/CAOBA-Central/pruebas-concepto/puj-bogota/pruebas-concepto-g9/poc-071-minenergia-prediccion-costo-unitario-fase1/-/blob/develop/docs/Comunicaciones%20Caoba.docx?ref_type=heads)

## Tabla de Contenidos 

* [Descripción de la solución](#descripción-de-la-solución) 

* [Screenshots](#screenshots) 

* [Requerimientos](#requerimientos) 

* [Instalacion](#instalación) 

* [Ejemplos de Codigo](#ejemplos-de-codigo) 

* [Pruebas Automatizadas](#pruebas-automatizadas) 

* [Autores](#autores) 

 

## Descripción de la solución 

Este proyecto tiene como propósito principal desarrollar un modelo de Machine Learning capaz de predecir el costo unitario de la energía eléctrica en el segmento residencial de Colombia, utilizando datos históricos y técnicas avanzadas de análisis de series temporales. El modelo está diseñado para generar estimaciones a seis meses, proporcionando proyecciones más precisas que las del modelo actual utilizado por el Ministerio de Energía. Esto permitirá al ministerio mejorar la calidad de sus predicciones y tomar decisiones más informadas y estratégicas para la gestión de precios en el sector energético. 

**Objetivo General**

Desarrollar un modelo de machine learning que, mediante el análisis de datos históricos, identifique patrones y tendencias para estimar el costo unitario de energía eléctrica en el segmento residencial de Colombia a seis meses, con el propósito de mejorar la precisión del modelo actualmente utilizado por el ministerio entregando una mejor proyección del costo unitario de energía en Colombia, para soportar la toma de decisiones de negocio que realiza el ministerio de Energía.   

**Objetivos específicos**

• Comprender el contexto del negocio y los datos históricos del costo unitario de energía eléctrica residencial en Colombia, mediante la exploración y análisis del modelo de predicción actual del ministerio y los datos disponibles.  

• Identificar modelos de Machine Learning que permitan predecir patrones y tendencias en los datos históricos del costo unitario de energía eléctrica residencial en Colombia y evalúen el impacto de las variables externas en el pronóstico del costo.   

• Diseñar, entrenar y validar modelos de machine learning de series temporales utilizando datos históricos del costo unitario de energía eléctrica para el segmento residencial en Colombia, y evaluar su precisión y rendimiento para seleccionar el modelo más adecuado en comparación con el modelo actual del ministerio.  

### Reto del cliente 

El Ministerio de Energía requiere conocer la proyección del costo unitario de energía en Colombia para poder proporcionar recomendaciones basadas en datos y así optimizar la estructura tarifaria, balanceando eficiencia, sostenibilidad, transparencia y equidad, así como, proporcionar alertas tempranas para identificar posibles anomalías o cambios en los costos futuros.  

También permite disponibilizar la información para los usuarios y stakeholders del sector, lo cual es fundamental para la planificación presupuestaria de entidades públicas y privadas, anticipando y gestionando los gastos energéticos futuros de manera informada. 

### Solución Alianza CAOBA 

Desarrollar y validar un modelo de regresión para series de tiempo que, utilizando técnicas de machine learning, analice datos históricos de los precios de los componentes del costo unitario y patrones de variables externas (Aportes hídricos, Precio de Bolsa, Capacidad Efectiva Neta, IPP, IPC, TRM), desde el 2015 hasta 2023. 

Para predecir con precisión el costo unitario de la energía eléctrica en el segmento residencial de Colombia a seis meses, mejorando así las proyecciones actuales del Ministerio de Minas y Energía. 

## Impacto potencial esperado en el Negocio 

El nuevo modelo de Machine Learning permitirá al Ministerio de Energía mejorar la precisión de las predicciones del costo unitario de la energía eléctrica, lo que optimizará la toma de decisiones estratégicas en la fijación de tarifas y la gestión de recursos. Esto reducirá los riesgos financieros asociados a fluctuaciones de precios, permitiendo una planificación más eficiente y predecible. 

Además, el modelo favorecerá una mayor transparencia y confianza por parte de los consumidores al ofrecer proyecciones más confiables y estables, lo que también apoyará la transición hacia una gestión más eficiente y sostenible del sistema energético en Colombia. 

### Screenshots / Demo 

![screenshot](https://gitlab.com/CAOBA-Central/pruebas-concepto/puj-bogota/pruebas-concepto-g9/poc-071-minenergia-prediccion-costo-unitario-fase1/-/blob/develop/docs/readme/Integrame_Dashboard_actual.png?ref_type=heads)

## Arquitectura logica de la solución 

El proyecto se basa en la construcción de un modelo de Machine Learning para predecir el costo unitario de energía eléctrica en Colombia, comparándolo con el modelo actual del ministerio (VEC). A continuación, se describen los puntos clave: 

1.	Componentes y Variables Exógenas: Se recolectarán datos históricos de componentes como comercialización, distribución, generación, pérdidas, restricciones y transmisión, junto con variables exógenas como aportes hídricos, precio de bolsa, capacidad efectiva neta, IPP, IPC y TRM. 

2.	Preprocesamiento de Datos: Incluirá la limpieza, integración y validación de los datos, garantizando que no haya valores nulos y que los formatos de fecha sean consistentes para análisis de series temporales. 

3.	Análisis Exploratorio y Correlación: Se realizarán análisis estadísticos descriptivos, visualización de tendencias y pruebas de correlación (Pearson o Spearman) para identificar las relaciones entre las variables. 

4.	Modelos de Machine Learning: Se probarán varios modelos de series temporales, incluyendo ARIMA, SARIMA, LSTM, XGBoost y TCN, seleccionando el más adecuado para las características de los datos. 

5.	División de Datos y Validación: Los datos se dividirán en entrenamiento y prueba (87%-13%), manteniendo el orden temporal. Se utilizará validación cruzada para ajustar hiperparámetros, repitiendo el proceso de entrenamiento y prueba en ventanas de tiempo deslizantes. 

6.	Evaluación y Métricas: El rendimiento del modelo propuesto se evaluará mediante la comparación con el modelo VEC usando métricas como el error absoluto medio (MAE) o el error cuadrático medio (RMSE), asegurando que ambos modelos sean evaluados bajo los mismos periodos y criterios. 

Este enfoque permitirá identificar un modelo más preciso para la predicción del costo unitario de energía eléctrica en Colombia. 

**Flujo de datos:**  

![](structure_example/docs/readme/flujo_datos.jpg)

## Estructura del proyecto 

``` 
.
├── README.md
├── Requirements.txt
├── conf
│   └── todo.txt
├── dashboard
│   └── todo.txt
├── data
│   ├── analytics
│   │   └── todo.txt
│   ├── raw
│   │   ├── IPC_Indices.xlsx
│   │   ├── IPP_Indices.xlsx
│   │   ├── TRM.xlsx
│   │   ├── aportes_hidricos.csv
│   │   ├── capacidad.csv
│   │   ├── componentes_tarifas_energia.csv
│   │   ├── data.txt
│   │   ├── data_ignorar.txt
│   │   └── precio_de_bolsa.csv
│   └── stage
│       ├── AS03CU03AA-DatosIntegradosComponentesCU.csv
│       └── todo.txt
├── datalab
│   ├── Modelo_Prueba.ipynb
│   ├── Modelo_TCN.ipynb
│   ├── Modelo_XGBoost.ipynb
│   ├── PRUEBA_1.ipynb
│   ├── predicciones_vs_valores_reales.png
│   └── todo.txt
├── deploy
│   └── todo.txt
├── docs
│   ├── Comunicaciones Caoba.docx
│   ├── Informe Proyecto
│   │   ├── Entrega 1
│   │   │   ├── Presentación primera entrega trabajo de grado.pptx
│   │   │   └── Proyecto de predicción de costo unitario de energía.docx
│   │   └── Entrega 2
│   │       └── Proyecto de predicción de costo unitario de energía.docx
│   ├── archivos soporte
│   │   ├── Diagrama Gantt Proyecto.xlsx
│   │   ├── Seguimiento XGB.xlsx
│   │   └── XGBoost vs VEC(2).pptx
│   ├── manual usuario
│   │   └── todo.txt
│   ├── readme
│   │   ├── Integrame_Dashboard_actual.png
│   │   ├── docs_Arquitectura.png
│   │   ├── docs_modeloDatosPowerBI.png
│   │   ├── ejemplo_descripcion_proyecto.png
│   │   ├── ejemplo_estructura_proyecto.png
│   │   └── flujo_datos.jpg
│   ├── todo.txt
│   └── video demo
│       └── todo.txt
├── src
│   └── todo.txt
└── temp
    ├── 00Standard_Ref_to_make_Experiments.ipynb
    ├── README.md
    └── root.py
``` 

## Proceso de ejecucion y despliegue 

## Requerimientos 

**Back-End:**
	•	Python (versión 3.9.7 o superior)

**Otros Requerimientos:**

	•	Git (versión 2.33.0 o superior): Para el control de versiones.
	•	GitHub: Repositorio para almacenamiento y colaboración en el código fuente.
	•	IDE recomendado: Visual Studio Code.

### Librerias Empleadas  

	•	Pandas (versión 1.3.3 o superior): Para manipulación y análisis de datos.
	•	NumPy (versión 1.21.2 o superior): Para operaciones matemáticas y manejo de matrices.
	•	SciPy (versión 1.7.1 o superior): Para cálculos científicos y estadísticos.
	•	scikit-learn (versión 0.24.2 o superior): Para la implementación de modelos de Machine Learning.
	•	statsmodels (versión 0.12.2 o superior): Para modelado estadístico y análisis de series temporales.
	•	TensorFlow (versión 2.6.0 o superior): Para el desarrollo de redes neuronales y modelos de aprendizaje profundo.
	•	XGBoost (versión 1.4.2 o superior): Para modelos de boosting y predicción.
	•	Matplotlib (versión 3.4.3 o superior): Para la visualización de datos.
	•	Seaborn (versión 0.11.2 o superior): Para gráficos estadísticos.
	•	Jupyter Notebook (versión 6.4.3 o superior): Para la creación de notebooks interactivos. 

### Requerimientos Hardware 

	•	Procesador (CPU): Mínimo: Intel Core i5 (4 núcleos) o equivalente.
	•	Memoria RAM: Mínimo: 8 GB.
	•	Almacenamiento:Mínimo: 256 GB SSD.
	•	Tarjeta Gráfica (GPU): Opcional: NVIDIA GTX 1050 o superior (recomendado para que los modelos puedan beneficiarse de la aceleración por GPU).
	•	Conectividad: Conexión a Internet estable.

### Requerimientos Software 
	•	Sistema Operativo: Windows 10 (64-bit), macOS Big Sur (11.0) o superior, o distribuciones de Linux (Ubuntu 20.04 LTS o superior).

## Instalación:  

**Nota:** Obligatorio: Minimo debe haber en el proyecto el archivo que permita instalar el ambiente necesario para el despliegue de la solución y los comandos ejecutados para la instalacion. Por ejemplo, si es Python un requeriments.txt o un archivo de DESCRIPTION en R.  

## Configuracion 
**Nota:** En desarrollo
## Ejemplos de Codigo 
**Nota:** En desarrollo

## Errores conocidos 
**Nota:** En desarrollo

## Pruebas Automatizadas 
**Nota:** En desarrollo

## Autores

| Organización  | Nombre del Miembro                     | Correo Electrónico            |
|---------------|----------------------------------------|-------------------------------|
| PUJ-Bogotá    | Diana Katherin Ibáñez: Experta Analítica | ibanezc.d@javeriana.edu.co    |
| PUJ-Bogotá    | Daniel Felipe Rodríguez: Experto Analítica | fa.martinez@javeriana.edu.co |
| PUJ-Bogotá    | Fabián Ricardo Martínez: Experto Analítica | d.rodriguez@javeriana.edu.co |
| PUJ-Bogotá    | Paola Andrea Castro: Experta Analítica  | pa.castro@javeriana.edu.co    |
| MinEnergia    | Jorge Lozano: Líder del negocio         | jelozano@minenergia.gov.co    |
| MinEnergia    | Andrés Ayure: Experto Analítica         | aaayure@minenergia.gov.co     |
| MinEnergia    | Francisco Maya: Experto Negocio         | fimaya@minenergia.gov.co      |
| MinEnergia    | Denis López: Experto Negocio            | dlopezc@minenergia.gov.co     |
| UPME          | John Ávila: Representante UPME          | john.avila@upme.gov.co        |
| UPME          | Marlet García: Representante UPME       | marlet.garcia@upme.gov.co     |
| UPME          | Armando Bossio: Representante UPME      | armando.bossio@upme.gov.co    |
