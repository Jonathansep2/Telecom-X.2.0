# 📊 Informe Final — Modelo Predictivo de Cancelación de Clientes (Churn)

## 1. Introducción

El presente proyecto tuvo como objetivo desarrollar un modelo predictivo capaz de identificar clientes con alta probabilidad de cancelar sus servicios, con el fin de anticipar acciones de retención y apoyar la toma de decisiones estratégicas de la empresa.

El trabajo cubrió el flujo completo de un proyecto de Machine Learning aplicado a negocio, incluyendo preparación de datos, análisis exploratorio, modelado, evaluación e interpretación estratégica.

---

## 2. Preparación de los datos

Se utilizó un dataset previamente limpiado del desafío Telecom X, que contenía información demográfica, contractual, de servicios y facturación de los clientes.

Durante esta etapa se realizaron las siguientes acciones:

* Eliminación de columnas irrelevantes (identificadores y variables duplicadas).
* Selección de la variable objetivo (`churn_flag`).
* Transformación de variables categóricas mediante One-Hot Encoding.
* Verificación del balance de clases, encontrándose un desbalance moderado:

  * 73.5% clientes activos
  * 26.5% clientes cancelados

Se decidió no balancear inicialmente para evaluar primero el comportamiento real del modelo.

---

## 3. Modelado predictivo

Los datos se dividieron en:

* 80% entrenamiento
* 20% prueba
* Manteniendo la proporción de cancelación mediante estratificación.

Se entrenaron dos modelos:

### 3.1 Regresión Logística

Modelo base interpretable, adecuado para problemas de churn.

Resultados principales:

* Accuracy: 0.79
* Recall churn: 0.52
* Precision churn: 0.63
* F1 churn: 0.57

El modelo detecta más de la mitad de los clientes que cancelan, manteniendo un buen balance entre precisión y cobertura.

---

### 3.2 Random Forest

Modelo no lineal basado en árboles.

Resultados principales:

* Accuracy: 0.79
* Recall churn: 0.48
* Precision churn: 0.63
* F1 churn: 0.54

El desempeño fue ligeramente inferior al de la regresión logística en la detección de cancelaciones.

---

## 4. Comparación de modelos

Aunque ambos modelos mostraron desempeños similares en exactitud, la regresión logística presentó:

* Mayor recall de churn
* Mejor F1-score
* Mayor interpretabilidad

Por estas razones se seleccionó como modelo principal para el análisis estratégico.

---

## 5. Interpretación del modelo

El análisis de coeficientes permitió identificar los factores que más influyen en la cancelación.

### 5.1 Factores que aumentan la probabilidad de cancelación

* Alto gasto acumulado del cliente
* Uso de servicio de fibra óptica
* Facturación electrónica
* Pago mediante cheque electrónico
* Servicios adicionales como streaming

Estos factores sugieren que los clientes con mayor consumo y expectativas más altas son también los más sensibles a problemas de calidad o precio.

---

### 5.2 Factores que reducen la cancelación

* Mayor antigüedad del cliente
* Contratos de largo plazo (1 y 2 años)
* Disponibilidad de soporte técnico
* Servicios de seguridad y respaldo

Estos elementos reflejan mayor fidelización y percepción de valor del servicio.

---

## 6. Perfil de cliente con alto riesgo de cancelación

El modelo sugiere que los clientes con mayor probabilidad de cancelar presentan:

* Baja antigüedad en la empresa
* Contratos mensuales
* Alto gasto acumulado
* Uso de fibra óptica
* Ausencia de soporte técnico
* Métodos de pago menos vinculantes

Este perfil permite orientar acciones preventivas.

---

## 7. Recomendaciones estratégicas

A partir de los resultados del modelo se sugieren las siguientes acciones:

### 7.1 Fidelización temprana

* Programas de acompañamiento para clientes nuevos
* Beneficios durante los primeros meses

### 7.2 Incentivar contratos de permanencia

* Descuentos por contratos anuales
* Beneficios exclusivos por permanencia

### 7.3 Fortalecer soporte técnico

* Soporte prioritario para clientes de alto consumo
* Monitoreo proactivo de calidad del servicio

### 7.4 Estrategias sobre clientes premium

* Seguimiento a clientes con gasto alto
* Ofertas personalizadas antes de posibles cancelaciones

---

## 8. Conclusiones

El proyecto permitió construir un pipeline completo de modelado predictivo de churn y traducir los resultados a decisiones estratégicas de negocio.

La regresión logística demostró ser un modelo adecuado para esta etapa inicial, al combinar buen desempeño predictivo con alta interpretabilidad.

El análisis evidencia que la fidelización, la calidad del servicio y la estructura contractual son factores clave en la retención de clientes.

El modelo desarrollado puede servir como base para futuras mejoras, incluyendo balanceo de clases, ajuste de hiperparámetros y despliegue en entornos productivos.

---

## 9. Próximos pasos sugeridos

* Ajuste de hiperparámetros del modelo
* Evaluación con métricas ROC-AUC y curvas de precisión-recall
* Integración del modelo en sistemas de CRM
* Desarrollo de campañas automatizadas de retención

---

**Fin del informe**
