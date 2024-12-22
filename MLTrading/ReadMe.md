# Conceptos Principales

Este documento detalla cómo se relacionan los conceptos de **trading**.

---

## **1. Benchmark Returns**

### ¿Qué son?
Los **benchmark returns** son los rendimientos generados por un índice o activo financiero utilizado como referencia para evaluar el desempeño de una estrategia de inversión.

### Ejemplos comunes:
- **Índices bursátiles**: S&P 500, NASDAQ, MSCI World Index.
- **Tasa libre de riesgo**: Rendimiento de bonos gubernamentales.
- **Índices sectoriales**: Índices que reflejan el rendimiento de sectores específicos.

### Propósito:
- Proporcionar un punto de comparación objetivo.
- Determinar si una estrategia supera al mercado o simplemente refleja su comportamiento.

---

## **2. Strategy Returns**

### ¿Qué son?
Los **strategy returns** son los rendimientos obtenidos por la estrategia de inversión implementada, en este caso, basada en señales de trading como **MA12 > MA21**.

### ¿Cómo se calculan?
Los rendimientos de la estrategia se calculan usando la fórmula:

\[
R_t = \frac{P_t - P_{t-1}}{P_{t-1}}
\]

Donde:
- \(R_t\): Rendimiento de la estrategia en el período \(t\).
- \(P_t\): Valor de la cartera al final del período \(t\).
- \(P_{t-1}\): Valor de la cartera al inicio del período \(t\).

### Propósito:
- Mostrar el rendimiento real de la estrategia frente al benchmark.
- Evaluar si la estrategia genera valor adicional sobre una inversión pasiva.

---

## **3. Sharpe Ratio**

### ¿Qué es?
El **Sharpe ratio** mide el rendimiento ajustado al riesgo de una inversión o estrategia, y se utiliza para evaluar su eficiencia.

### Fórmula:
\[
\text{Sharpe Ratio} = \frac{R_p - R_f}{\sigma_p}
\]

Donde:
- \(R_p\): Rendimiento promedio de la estrategia o benchmark.
- \(R_f\): Tasa de rendimiento libre de riesgo.
- \(\sigma_p\): Desviación estándar del rendimiento (una medida de riesgo o volatilidad).

### Propósito:
- Comparar estrategias o inversiones en términos de eficiencia.
- Determinar si una estrategia justifica el riesgo asumido en función de sus rendimientos.

### Interpretación:
- **Sharpe ratio alto**: Mejor rendimiento ajustado al riesgo.
- **Sharpe ratio bajo**: Peor rendimiento ajustado al riesgo.

---

## **4. Señales de Trading: MA12 > MA21**

### ¿Qué significa?
- **MA12**: Media móvil de 12 períodos (puede ser días, horas, etc.).
- **MA21**: Media móvil de 21 períodos.
- La regla **MA12 > MA21** indica que la media móvil rápida (corto plazo) cruza hacia arriba la media móvil lenta (largo plazo), señalando una **tendencia alcista**.

### Generación de señales:
1. **Signal de compra**: Cuando **MA12 cruza hacia arriba a MA21**.
2. **Signal de venta**: Cuando **MA12 cruza hacia abajo a MA21**.

Estas señales se utilizan para determinar puntos de entrada y salida en el mercado.

---

## **5. Evaluación conjunta: Benchmark vs Strategy**

### Comparación de retornos:
- **Benchmark Returns**: Rendimientos del índice de referencia (mercado).
- **Strategy Returns**: Rendimientos obtenidos por la estrategia basada en las señales.

**Objetivo**: Comparar ambos para determinar si la estrategia agrega valor sobre el benchmark.

### Evaluación ajustada al riesgo:
Se comparan los **Sharpe ratios** de la estrategia y el benchmark:

1. **Strategy Sharpe Ratio**:
   \[
   \text{Sharpe Ratio (estrategia)} = \frac{\text{Rendimiento promedio de la estrategia} - \text{Tasa libre de riesgo}}{\text{Volatilidad de la estrategia}}
   \]

2. **Benchmark Sharpe Ratio**:
   \[
   \text{Sharpe Ratio (benchmark)} = \frac{\text{Rendimiento promedio del benchmark} - \text{Tasa libre de riesgo}}{\text{Volatilidad del benchmark}}
   \]

**Conclusión**:
- Si el **Sharpe ratio** de la estrategia es mayor, significa que ofrece mejores rendimientos ajustados al riesgo.
- Si el **Sharpe ratio** del benchmark es mayor, la estrategia no está generando valor adicional frente al mercado.

**Ejemplo Práctico**

### Suposiciones:
- **Benchmark (S&P 500)**:
  - Rendimiento promedio: 10%.
  - Volatilidad: 15%.
- **Estrategia basada en MA12 > MA21**:
  - Rendimiento promedio: 15%.
  - Volatilidad: 20%.
- **Tasa libre de riesgo (\(R_f\))**: 2%.

### Cálculo del Sharpe Ratio:
1. **Benchmark Sharpe Ratio**:
   \[
   \text{Sharpe Ratio} = \frac{10\% - 2\%}{15\%} = 0.53
   \]

2. **Strategy Sharpe Ratio**:
   \[
   \text{Sharpe Ratio} = \frac{15\% - 2\%}{20\%} = 0.65
   \]

### Interpretación:
- La estrategia tiene un mejor rendimiento ajustado al riesgo que el benchmark.

---

## **6. Pairs Trading**

### ¿Qué es?
**Pairs Trading** es una estrategia de trading que busca explotar la relación estadística entre dos activos que están históricamente correlacionados.

### Cómo funciona:
1. Identificas dos activos que tienen una relación histórica predecible, como dos acciones del mismo sector (por ejemplo, Coca-Cola y Pepsi).
2. Cuando los precios se desvían de su relación habitual (spread), tomas posiciones:
   - **Comprar** el activo que está infravalorado (por debajo de su precio esperado).
   - **Vender** el activo que está sobrevalorado (por encima de su precio esperado).
3. El beneficio se genera cuando los precios regresan a su relación habitual.

### Propósito:
Aprovechar las ineficiencias de precio sin importar si el mercado en general sube o baja.

---

## **7. Cointegration**

### ¿Qué es?
La **cointegración** es un concepto estadístico que describe una relación estable y predecible entre dos o más series temporales a largo plazo, a pesar de que cada una de ellas pueda ser no estacionaria por sí misma.

### Relación con Pairs Trading:
- En pairs trading, se busca que los activos sean cointegrados en lugar de simplemente correlacionados.
- La cointegración garantiza que el spread (la diferencia entre los precios) sea estacionario y regrese a su media a lo largo del tiempo.

### Ejemplo:
Dos acciones de una misma industria pueden ser cointegradas porque están afectadas por factores comunes (como cambios en el sector), lo que significa que cualquier desviación entre sus precios será temporal.

---
