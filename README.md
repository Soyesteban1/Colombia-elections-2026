# 🗳️ Elecciones Presidenciales de Colombia 2026

## Análisis Predictivo con Machine Learning

**Modelo predictivo basado en datos electorales, demográficos y socioeconómicos a nivel municipal**

---

## Resumen Ejecutivo

Este proyecto desarrolla un **modelo predictivo de Machine Learning** para estimar el posible resultado de las elecciones presidenciales de Colombia en 2026.

El análisis utiliza información de **856 municipios**, integrando:

* Resultados electorales históricos
* Indicadores socioeconómicos municipales
* Índice de Pobreza Multidimensional (IPM)
* Variables demográficas

El objetivo es identificar **patrones territoriales de votación** y analizar cómo factores estructurales influyen en el comportamiento electoral.

Los resultados muestran que la elección se mantiene **estadísticamente competitiva**, con un alto número de municipios donde la diferencia proyectada es mínima.

---

## Hallazgo Principal

**El 56.8% de los municipios analizados presenta un margen de victoria menor al 5%.**

Esto sugiere que la elección presidencial de 2026 **se definirá principalmente a nivel territorial**, especialmente en municipios intermedios donde la volatilidad electoral es mayor.

| Candidato                  | Municipios Predichos | Porcentaje de voto estimado |
| -------------------------- | -------------------- | --------------------------- |
| Iván Cepeda (Izquierda)    | 495                  | 50.4%                       |
| Oposición (Centro/Derecha) | 361                  | 49.6%                       |

### Desempeño del modelo

| Modelo              | Métrica                     | Resultado   |
| ------------------- | --------------------------- | ----------- |
| Regresión Logística | Precisión                   | 96.0%       |
| Regresión Logística | Validación cruzada (5-fold) | 96.6% ±1.1% |
| Regresión Lineal    | R²                          | 98.8%       |
| Regresión Lineal    | RMSE                        | 2.55%       |

---

## Contexto Político

Las elecciones presidenciales de **2026 representan un momento clave en la evolución política de Colombia**.

En 2022, el país eligió por primera vez un presidente de izquierda cuando **Gustavo Petro** derrotó a Rodolfo Hernández con **50.4% frente a 47.3%**, una diferencia aproximada de **700.000 votos de 20 millones emitidos**.

El gobierno de Petro impulsó reformas estructurales enfocadas en:

* Reforma agraria
* Transición energética
* Expansión de programas sociales

Sin embargo, su administración también ha enfrentado críticas relacionadas con:

* Presiones inflacionarias
* Incertidumbre fiscal
* Polarización política

En este contexto, las elecciones de 2026 se interpretan como **una evaluación del proyecto político iniciado en 2022**.

---

## Principales Candidatos

### Iván Cepeda — Pacto Histórico

**Encuestas actuales:** ~36%

Senador desde 2010 y reconocido defensor de derechos humanos. Representa la continuidad del proyecto político del gobierno actual.

**Base electoral**

* Votantes progresistas urbanos
* Regiones del Pacífico y Caribe
* Municipios con altos niveles de pobreza

**Factores de riesgo**

* Asociación con un gobierno impopular
* Menor reconocimiento nacional fuera de grandes ciudades
* Percepción de radicalismo ideológico entre votantes de centro

---

### Abelardo de la Espriella — Centro-Derecha Independiente

**Encuestas actuales:** ~28%

Abogado originario de Montería que ha ganado notoriedad nacional a través de casos legales de alto perfil.

**Base electoral**

* Municipios rurales del Caribe
* Votantes anti-establecimiento
* Regiones con descontento hacia los partidos tradicionales

**Factores de riesgo**

* Organización política nacional limitada
* Ambigüedad ideológica
* Plataforma programática poco definida

---

### Paloma Valencia — Coalición de Derecha

**Encuestas actuales:** ~17.5%

Senadora vinculada al movimiento conservador asociado históricamente al expresidente Álvaro Uribe.

**Base electoral**

* Antioquia y Eje Cafetero
* Sector empresarial
* Voto urbano opositor al gobierno Petro

**Factores de riesgo**

* Base electoral concentrada geográficamente
* Dificultad para expandirse más allá del voto conservador tradicional

---

### Sergio Fajardo — Centro Esperanza

**Encuestas actuales:** ~5%

Exalcalde de Medellín y exgobernador de Antioquia, reconocido por programas de innovación urbana.

**Base electoral**

* Clase media urbana
* Sector académico y profesional
* Votantes moderados

**Factores de riesgo**

* Varias candidaturas presidenciales sin victoria
* Pérdida de impulso político frente a nuevas figuras

---

## Principales Hallazgos del Análisis

### 1. La pobreza y el voto de izquierda

Los municipios con altos niveles de **Índice de Pobreza Multidimensional (IPM)** muestran mayor apoyo a candidatos de izquierda.

No obstante, la relación es **no lineal**:

* Alta pobreza urbana → mayor voto de izquierda
* Pobreza rural extrema → mayor voto conservador

Esto sugiere que **la presencia del Estado y el acceso a servicios públicos** influyen significativamente.

---

### 2. Brecha urbano-rural

La idea de que **las zonas rurales votan consistentemente por la izquierda no se confirma completamente**.

El predictor más fuerte del voto progresista es **la pobreza urbana en ciudades intermedias**.

---

### 3. La primera vuelta como predictor principal

La variable más influyente del modelo es el **porcentaje de voto en primera vuelta**.

Coeficiente: **5.77**

Los municipios rara vez cambian más de **8 puntos porcentuales entre la primera y segunda vuelta**, lo que evidencia **alta lealtad electoral**.

---

## Importancia de Variables

Coeficientes del modelo de regresión logística

| Variable            | Coeficiente | Interpretación                                       |
| ------------------- | ----------- | ---------------------------------------------------- |
| pct_petro_v1        | +5.77       | Predictor más fuerte                                 |
| desempeño_fiscal    | +0.41       | Mejor gestión fiscal favorece voto de izquierda      |
| tasa_homicidios     | +0.31       | Mayor violencia correlaciona con voto de izquierda   |
| nbi_rural           | +0.16       | Pobreza rural favorece a la izquierda                |
| ipm                 | -0.35       | Mayor pobreza multidimensional favorece a la derecha |
| cobertura_acueducto | -0.28       | Mejores servicios correlacionan con voto de derecha  |
| pct_rodolfo_v1      | -1.14       | Base electoral de derecha                            |

---

## Estructura del Proyecto

```id="rg5xqm"
colombia-elecciones-2026/

data/
 ├ raw/
 └ processed/

notebooks/
 ├ 01_etl.ipynb
 ├ 02_eda.ipynb
 ├ 03_modelo.ipynb
 └ 04_prediccion_2026.ipynb

dashboard/
reports/
src/
```

---

## Fuentes de Datos

| Fuente                 | Descripción                                 |
| ---------------------- | ------------------------------------------- |
| Registraduría Nacional | Resultados electorales por municipio (2022) |
| DNP TerriData          | Indicadores socioeconómicos municipales     |
| DANE                   | Datos demográficos del censo                |

---

## Limitaciones

* Falta de datos completos para **Antioquia**
* Simulación de primera vuelta 2026 basada en encuestas
* Cambios estructurales posteriores a 2022 no capturados por el modelo

---

## Autor

**David Esteban**
Proyecto de portafolio en Ciencia de Datos y Machine Learning

GitHub
https://github.com/Soyesteban1
