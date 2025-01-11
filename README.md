# Predicción del Precio de Bitcoin 📈

Este repositorio contiene un proyecto de análisis y predicción del precio de Bitcoin utilizando un modelo de **Random Forest**. El archivo principal, `PrediccionBitcoin.ipynb`, guía al usuario a través de todo el proceso, desde la limpieza de datos hasta la predicción.

⚠️ **Nota importante:** Este proyecto ha sido desarrollado con fines educativos y de aprendizaje. **No debe utilizarse como base para realizar compras, trading o inversiones relacionadas con Bitcoin.** El modelo y los datos pueden no reflejar con precisión el comportamiento real del mercado.

## **Datos del Proyecto**
La base de datos utilizada en este proyecto fue obtenida de [Investing.com](https://es.investing.com/crypto/bitcoin/historical-data). Contiene precios históricos de Bitcoin desde el **12.01.2012** hasta el **10.01.2025**.

## **Estructura del Proyecto**

1. **Importación de Librerías**  
   - Configuración de herramientas clave como `pandas`, `numpy`, `matplotlib`, y `scikit-learn` para la manipulación de datos, visualización y modelado.

2. **Carga de Datos**  
   - Cargamos un dataset de precios históricos de Bitcoin desde un archivo CSV. Este incluye columnas como `Fecha`, `Último`, `Apertura`, `Máximo`, `Mínimo`, `Vol.` y `% var.`.

3. **Limpieza y Preprocesamiento**  
   - Transformamos los datos para que sean adecuados para el modelo:
     - Conversiones de fecha al formato `datetime` y orden cronológico.
     - Limpieza de columnas numéricas (separadores de miles, comas/puntos).
     - Conversión de valores de volumen (en `K`, `M`, `B`) a valores numéricos.
     - Generación de nuevas características como:
       - **Rango**: Diferencia entre el precio máximo y mínimo del día.
       - **Cambio**: Diferencia entre el precio de apertura y el último precio.

4. **Selección de Variables y División de Datos**  
   - Elegimos las características más relevantes para predecir el precio de Bitcoin y dividimos el dataset en **entrenamiento (80%)** y **prueba (20%)**.

5. **Ajuste del Modelo Random Forest**  
   - Utilizamos **GridSearchCV** para ajustar los hiperparámetros del modelo. Esto incluye la validación cruzada específica para series temporales (**TimeSeriesSplit**), asegurando que el modelo generalice correctamente a nuevas fechas.

6. **Evaluación del Modelo**  
   - Métricas principales calculadas:
     - **Error Cuadrático Medio (MSE)** y **Raíz del Error Cuadrático Medio (RMSE)** para medir la precisión.
     - **Error Absoluto Medio (MAE)** como indicador del error promedio.

7. **Predicción del Precio del Siguiente Día**  
   - Utilizamos el modelo entrenado para predecir el precio de Bitcoin para el próximo día disponible, basado en los datos más recientes.

8. **Visualización de Resultados**  
   - Incluimos gráficos interactivos y estáticos para mostrar:
     - Los datos reales históricos.
     - Las predicciones del modelo para los datos históricos.
     - La predicción específica para el próximo día.

9. **Validación Adicional**  
   - Validamos el modelo con métricas adicionales como el promedio del **MSE en validación cruzada**, identificando posibles problemas como el sobreajuste.

## **Motivación del Proyecto**

El mercado de criptomonedas es volátil y presenta grandes desafíos para predecir precios. Este proyecto explora un enfoque basado en **machine learning** para entender patrones históricos y realizar predicciones útiles, ayudando a la toma de decisiones informadas.

## **Próximos Pasos**
- Extender el modelo para considerar factores externos (como volumen de transacciones globales).
- Comparar el rendimiento del modelo con otras técnicas, como redes neuronales recurrentes (RNNs).
- Implementar predicciones a mediano y largo plazo.
