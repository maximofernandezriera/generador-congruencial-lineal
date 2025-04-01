# generador-congruencial-lineal
Generador Congruencial Lineal - Simulación - UOC - 2025

```r
# Implementación del Linear Congruential Generator (LCG) en R
# Fórmula: X_{n+1} = (a*X_n + c) mod m

# Función para generar números aleatorios usando LCG
lcg <- function(n, seed = 12345, a = 1664525, c = 1013904223, m = 2^32) {
  # Inicializar vector para almacenar los números generados
  x <- numeric(n)
  
  # Establecer la semilla inicial
  x[1] <- seed
  
  # Generar n-1 números aleatorios
  for (i in 2:n) {
    x[i] <- (a * x[i-1] + c) %% m
  }
  
  # Normalizar los valores al rango [0,1)
  return(x / m)
}

# Generar 10000 números aleatorios usando LCG
set.seed(42)  # Para reproducibilidad
n <- 10000
random_numbers <- lcg(n)
```
