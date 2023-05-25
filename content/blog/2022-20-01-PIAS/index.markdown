---
title: "PIAS - Planes individuales de ahorro sistemático"
subtitle: "Descripcion, Requisitos y Caraterísticas - ¿es un buen producto?"
excerpt: "¿merece la pena contratar un PIAS?"
date: 2022-10-01
author: "jcc"
draft: false
images:
series:
tags:
categories:
layout: single
---






### ¿Que es un PIAS??

Los planes individuales de ahorro sistemático o PIAS son seguros de vida-ahorro. Creados en 2007 tras la reforma del IRPF, el objetivo de este producto es el de incentivar el ahorro a largo plazo con ciertas ventajas fiscales previstas en el caso de cobrarse como renta vitalicia. En este caso los beneficios obtenidos de la inversión son rendimientos exentos de tributación (aunque la renta vitalicia sí que tributa, en un rango variable, en función de la edad del beneficiario).
Es un seguro de vida que está más enfocado a ser un producto de ahorro. La aportación al PIAS se divide en dos partes, la primera destinada al pago de una prima para una cobertura de fallecimiento (esta proporción es muy pequeña respecto del total aportado) más una cantidad destinada a la inversión.



### Requisitos y Características de los PIAS

* Requisitos
  + El tomador, asegurado y beneficiario debe ser el propio contribuyente
  + Renta vitalicia. Para poder constituirla y obtener las ventajas fiscales el PIAS deberá tener una antigüedad mínima de 5 años (aunque se pueda rescatar en cualquier momento)
  + El límite de primas que se pueden aportar al producto anualmente es de 8.000€, eso sí, independientemente de las aportaciones a sistemas de previsión social
  + El límite total de primas acumuladas no debe ser superior a 240.000€
  
* Características
  + Las aportaciones no desgravan en la renta aunque sea un seguro
  + Permite el traspaso entre PIAS y sin tributar por los beneficios
  + En caso de fallecimiento se puede elegir el beneficiario sin tener que ser un heredero
  + Los activos no están a nombre del asegurado sino de la compañía aseguradora. Importante en caso de quiebra de la compañía 
  + Son de dos tipos: garantizados o aquellos donde el riesgo de la inversión lo tiene el tomador (en este caso suele tener el mismo formato que los Unit Link)
  + Es un producto líquido aunque la penalización por rescate los primeros años es muy alta
  + Es un producto con varias capas de comisiones ya que a las comisiones de los PIAS hay que sumar la de los productos de inversión y la prima del seguro. En ocasiones son muy elevadas
  + Es complicado comparara productos ya que no hay datos oficiales
  
* Otro dato importante a tener en cuenta es que en caso de ser mayor de 65 años, si se reembolsa un fondo de inversión y se reinvierte en una renta vitalicia, se está exento de tributar por la ganancia patrimonial. Esto hace que el PIAS pierda su principal ventaja frente a otras opciones


```
## Hello Python!
```



```r
summary(cars)
```

```
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
```

## Including Plots

You can also embed plots, for example:

<img src="{{< blogdown/postref >}}index_files/figure-html/pressure-1.png" width="672" />

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.


```r
library(shiny)
library(ggplot2)

# UI
ui <- fluidPage(
  titlePanel("Sum and Graph Example"),
  
  sidebarLayout(
    sidebarPanel(
      numericInput("number1", "Enter number 1:", value = 0),
      numericInput("number2", "Enter number 2:", value = 0),
      actionButton("calculate", "Calculate")
    ),
    
    mainPanel(
      plotOutput("graph")
    )
  )
)

# Server
server <- function(input, output) {
  observeEvent(input$calculate, {
    # Calculate sum
    sum_result <- input$number1 + input$number2
    
    # Create a data frame for graph
    data <- data.frame(
      Number = c("Number 1", "Number 2", "Sum"),
      Value = c(input$number1, input$number2, sum_result)
    )
    
    # Render graph
    output$graph <- renderPlot({
      ggplot(data, aes(x = Number, y = Value, fill = Number)) +
        geom_bar(stat = "identity") +
        labs(title = "Sum and Graph Example", x = "Number", y = "Value") +
        theme_minimal()
    })
  })
}

# Run the application
shinyApp(ui = ui, server = server)
```
