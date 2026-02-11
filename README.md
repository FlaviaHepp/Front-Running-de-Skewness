# Front-Running de Skewness

El rastro estadístico previo a Fusiones y Adquisiciones

## 📌Descripción General

Este proyecto busca detectar señales estadísticas de información privilegiada analizando el comportamiento del skewness (asimetría de los retornos) en los días previos a un anuncio de Adquisición.

La hipótesis central es que, cuando actores informados comienzan a posicionarse antes de la noticia oficial, la distribución de retornos se vuelve asimétricamente positiva, aun cuando el precio no muestre movimientos evidentes.

## 📍Insight Clave

- ¿El skewness se vuelve anormalmente positivo antes de que el mercado conozca una Adquisición?

Un skewness elevado previo al anuncio sugiere:
- mayor frecuencia de retornos positivos extremos,
- acumulación silenciosa,
- distorsión estadística causada por trading informado.

Por Qué es Sorprendente?
- El precio puede permanecer relativamente estable.
- El volumen puede no dispararse.
- Pero la forma de la distribución de retornos ya delata el evento.
- Es una huella que los indicadores clásicos no capturan.

## 💼Valor de Negocio

- Detección temprana de posibles operaciones de insider trading.
- Identificación de oportunidades event-driven antes del anuncio público.
- Herramienta cuantitativa para:
  vigilancia de mercado,
  compliance,
  estrategias de arbitraje informacional.
- Complemento ideal a análisis de volumen y volatilidad.

Fuentes de Datos:
- eventos_corporativos
- ticker_id
- fecha
- tipo_evento
- indicadores_tecnicos
- ticker_id
- fecha
- skewness

## 🧠Lógica del Análisis

- Se filtran eventos corporativos del tipo Adquisición.

Para cada evento:
- Se calcula el skewness promedio en los 5 días previos al anuncio.
- Se seleccionan solo los casos donde:
   skewness_promedio_pre > 2.0
lo que indica una asimetría positiva extrema.

Se agrupan resultados por ticker y fecha de anuncio.

## 📊Interpretación de Resultados

Skewness pre-evento > 2.0
→ Alta probabilidad de acumulación informada.
→ Señal de front-running estadístico.

Skewness cercano a 0
→ Evento sorpresivo, sin filtración previa detectable.

Skewness negativo
→ No compatible con lógica de M&A anticipado.

## 🧩Casos de Uso

- Monitoreo cuantitativo de eventos sensibles.
- Filtrado de rumores creíbles vs. ruido de mercado.
- Análisis forense post-evento.
- Input para modelos predictivos de M&A.

## 🚀Posibles Extensiones

- Comparar adquisiciones exitosas vs. canceladas.
- Medir skewness vs. kurtosis (intensidad del riesgo).
- Analizar diferencias por país o regulación.
- Combinar con volumen anómalo y opciones (IV skew).
- Backtesting de estrategias long-pre-evento.

## ✒️Nota Final

**Este insight no busca predecir eventos.
Busca algo más sutil y poderoso:
detectar cuándo el mercado ya sabe algo que todavía no puede decir.**

## 👤Autora
Flavia Hepp Proyecto de SQL aplicó un análisis de riesgo basado en eventos.
