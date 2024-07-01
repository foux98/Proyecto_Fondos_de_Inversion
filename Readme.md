# Proyecto de Análisis de Fondos de Inversión
Este proyecto tiene como objetivo analizar datos de fondos de inversión de un país ficticio utilizando Python, pandas y Power BI. A continuación se detalla el proceso realizado y los gráficos generados para entender mejor el comportamiento de los fondos y las inversiones.

1. **Preparación de Datos** 
En primer lugar, se realizaron operaciones de unión (merge) entre varias tablas de datos utilizando pandas en Python. Las tablas utilizadas incluyeron auditoría, fondos, rendimiento, transacciones, inversiones, activos, inversores, gestores, tarifas y datos de mercado. Con el objetivo de consolidar la información para su posterior análisis.
import pandas as pd

**Cargar datos desde archivos CSV**
assets = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\assets.csv") audit = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\audit.csv") fees = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\fees.csv") funds = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\funds.csv") investments = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\investments.csv") investors = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\investors.csv") managers = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\managers.csv") marketdata = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\marketdata.csv") performance = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\performance.csv") transactions = pd.read_csv(r"C:\Users\hp\Documents\ironhack_2_parte\valeria\data\transactions.csv")

**Fusionar tablas según requerimientos**
Fondos5 = pd.merge(fees, investors) Fondos = pd.merge(investments, performance) Fondos2 = pd.merge(Fondos, fees) Fondos3 = pd.merge(Fondos2, assets) Fondos4 = pd.merge(Fondos3, funds) Fondos6 = pd.merge(Fondos4, Fondos5) Fondos7 = pd.merge(Fondos6, transactions) Fondos8 = pd.merge(Fondos7, managers)

**Guardar el resultado en un archivo CSV**
ruta_archivo = r"C:\Users\hp\OneDrive\Escritorio\Proyecto_4\Proyecto_4.csv" Fondos6.to_csv(ruta_archivo, index=False)

2. **Análisis en Power BI^**
Una vez preparados los datos, se utilizó Power BI para analizarlos y generar visualizaciones informativas sobre los fondos de inversión.

**Grafico de Anillos (Donut Chart)**
En este gráfico se muestra la distribución de tipos de fondos según las sumas totales de inversiones. Los tipos de fondos más destacados fueron:

Multi estrategia
Fixed income
Quantitative
Equity

**Grafico de Columnas Apiladas (Stacked Column Chart)**
Se representa el rendimiento de diferentes fondos, comparando su desempeño a lo largo del tiempo.

**Grafico de Líneas (Line Chart)**
Compara el rendimiento y las tarifas de rendimiento de los fondos de inversión para investigar si las tarifas aplicadas se reflejan en el rendimiento.

**Grafico Circular (Pie Chart)**
Muestra la inversión total en diferentes tipos de activos, identificando los activos más invertidos en el país ficticio.

**Grafico de Barras Agrupadas (Clustered Bar Chart)**
Compara la cantidad invertida y el rendimiento de diferentes fondos de inversión, evaluando si la inversión está proporcionalmente relacionada con el rendimiento.

**Grafico de Barras Apiladas (Stacked Bar Chart)**
Muestra la inversión por país y por inversor, identificando los países con mayor inversión en fondos de inversión.

# Conclusiones
Tras analizar los datos y generar diversas visualizaciones en Power BI, he conseguido llegar a varias conclusiones importantes sobre los fondos de inversión y su comportamiento en el país ficticio.


