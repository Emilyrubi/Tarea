
# Desafío 1: Filtrar y manipular data frames
> Filtrar todas las especies que viven en un lago y ordenar los resultados por tamaño (de mayor a menor).

```r
# Cargar el paquete dplyr

library(dplyr)

# Crear el data frame
especies <- data.frame(
  especie = c("Ajolote", "Rana", "Serpiente", "Tortuga"),
  habitat = c("Lago", "Río", "Bosque", "Lago"),
  tamano = c(30, 10, 150, 50),
  peso = c(150, 25, 1000, 500)
)

# Filtrar las especies que viven en un lago y ordenar por tamaño (de mayor a menor)
especies_lago <- especies %>%
  filter(habitat == "Lago") %>%
  arrange(desc(tamano))

print(especies_lago)
```

### Resultado

| especie | habitat | tamano | peso |
|---------|---------|--------|------|
| Tortuga | Lago    | 50     | 500  |
| Ajolote | Lago    | 30     | 150  |


# Generación de gráficos - Reto 2
* Para este reto, usaremos el dataset iris. A continuación, crearemos un gráfico de dispersión entre `Sepal.Length` y `Sepal.Width` con colores personalizados.

```r
# Cargar ggplot2

library(ggplot2)

# Gráfico de dispersión con colores personalizados
ggplot(iris, aes(x = Sepal.Length, y = Sepal.Width, color = Species)) +
  geom_point(size = 3) +
  labs(title = "Relación entre Largo y Ancho de Sépalo",
       x = "Largo del Sépalo",
       y = "Ancho del Sépalo") +
  theme_minimal() +
  scale_color_manual(values = c("setosa" = "darkorchid4", "versicolor" = "black", "virginica" = "goldenrod2"))
```
![Emisepalo](https://github.com/user-attachments/assets/5c60349e-0c79-411d-b2c0-94696086c238)


# Generación de gráficos de barras - Reto 5
* Visualización de ventas mensuales con colores nuevos.

```r
# Crear el data frame de ventas
ventas <- data.frame(
  mes = c("Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio"),
  ventas = c(12000, 15000, 13000, 16000, 17500, 14000)
)

# Gráfico de barras con colores personalizados
ggplot(ventas, aes(x = mes, y = ventas, fill = mes)) +
  geom_bar(stat = "identity") +
  labs(title = "Ventas Mensuales",
       x = "Mes",
       y = "Ventas") +
  theme_minimal() +
  scale_fill_manual(values = c("Enero" = "darkslateblue", "Febrero" = "darkcyan", "Marzo" = "darkolivegreen", 
                               "Abril" = "firebrick", "Mayo" = "goldenrod", "Junio" = "steelblue"))
```
![emiventas](https://github.com/user-attachments/assets/ca855464-23c5-4dd9-82b1-53cd9d382697)


# Gráfico de caja (boxplot) - 
* Distribución de MPG según el número de cilindros, con colores diferentes para cada grupo.

```r
# Cargar el paquete ggplot2
install.packages("ggplot2")
library(ggplot2)

# Gráfico de caja con colores personalizados para cada grupo de cilindros
ggplot(mtcars, aes(x = factor(cyl), y = mpg, fill = factor(cyl))) +
  geom_boxplot() +
  labs(title = "Distribución de MPG según el Número de Cilindros",
       x = "Número de Cilindros",
       y = "Millas por Galón (MPG)") +
  scale_fill_manual(values = c("4" = "mediumorchid4", "6" = "dodgerblue4", "8" = "darkorange3")) +
  theme_minimal()
```

![emicilindros](https://github.com/user-attachments/assets/4110a95e-c450-435b-8769-f742080a48fc)
