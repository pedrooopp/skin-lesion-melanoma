Title: Datasets
Date: 2023-07-03
Category: Page
Ordinal: 003

Para este proyecto, se utiliza una subbase compuesta por 1735 imágenes del concurso ISIC-2017. A partir de esta subbase, se han creado conjuntos de entrenamiento, validación y prueba. El conjunto de entrenamiento consta de 1031 instancias, el conjunto de validación de 183 instancias y el conjunto de prueba de 521 instancias.

## Desbalance entre clases

Es importante destacar que al separar la subbase en estos conjuntos, se ha tenido en cuenta el desbalance de clases. Se ha procurado mantener la misma proporción entre la clase positiva (melanoma) y la clase negativa (no melanoma) en los tres conjuntos. Esta consideración asegura que cada conjunto tenga una representación equilibrada de ambas clases, lo que es esencial para entrenar y evaluar modelos de manera justa y precisa; a continuación en la Figura {#fig_cddxc} muestra el desbalance de las clases en el conjunto de entrenamiento y validación.

<div style="display: flex; justify-content: center;">
  <figure>
    <!-- Incluir camino a la imagen a mostrar -->
    <img src="../images/cant_datos_por_clase.png" width="300">
    <figcaption>
      fig_cddxc :: 0: Benigno - 1: Maligno.
    </figcaption>
  </figure>
</div>

Por lo tanto, el desbalance de clases es un factor crítico que debe considerarse cuidadosamente durante el entrenamiento de un clasificador. En un conjunto de datos desbalanceado, las clases objetivo están representadas en proporciones significativamente diferentes, como se observa en la Figura {#fig_cddxc}.

Es importante abordar el desbalance de clases debido a sus implicaciones en el rendimiento y la capacidad de generalización de los modelos de aprendizaje automático. Cuando una clase está subrepresentada en comparación con la otra, el clasificador puede mostrar una tendencia hacia la clase dominante y tener dificultades para reconocer adecuadamente los ejemplos de la clase minoritaria. Si no se aborda adecuadamente el desbalance de clases, es probable que el modelo tenga un rendimiento deficiente en la detección de ejemplos de la clase minoritaria. Además, puede generar resultados sesgados y poco confiables en la evaluación y toma de decisiones.

A continuación, se presentan de manera general algunas imágenes pertenecientes al conjunto de entrenamiento, junto con su correspondiente clasificación.

<div class="row" style = "display: flex; justify-content: center;">
  <div class="column">
    <figure>
      <!-- Incluir camino a la primera imagen a mostrar -->
      <img src="../images/benigno_1.jpg" width="300">
      <figcaption>
        fig_benigno1 :: Clase: benigno.
      </figcaption>
    </figure>
  </div>
  
  <div class="column">
    <figure>
      <!-- Incluir camino a la segunda imagen a mostrar -->
      <img src="../images/maligno_1.jpg" width="300">
      <figcaption>
        fig_maligno1 :: Clase: maligno.
      </figcaption>
    </figure>
  </div>
</div>

<div class="row" style = "display: flex; justify-content: center;">
  <div class="column">
    <figure>
      <!-- Incluir camino a la tercera imagen a mostrar -->
      <img src="../images/maligno_2.jpg" width="300">
      <figcaption>
        fig_maligno2 :: Clase: maligno.
      </figcaption>
    </figure>
  </div>
  
  <div class="column">
    <figure>
      <!-- Incluir camino a la cuarta imagen a mostrar -->
      <img src="../images/benigno_2.jpg" width="300">
      <figcaption>
        fig_benigno2 :: Clase: benigno.
      </figcaption>
    </figure>
  </div>
</div>

## Exploración de las imágenes
Si bien gran parte de las imágenes son similares a las presentadas anteriormente, durante la exploración del conjunto de datos se observa una diversidad de imágenes que probablemente provengan de varias fuentes distintas. Al analizar las imágenes, se identifican diferentes características que es importante tener en cuenta:

1. Imágenes con bordes negros: Algunas imágenes presentan bordes negros alrededor de la lesión. Estos bordes pueden ser producto    del lente utilizado para capturar las lesiones de cerca. 

2. Imágenes con parches: Se detectó un conjunto de imágenes que contienen parches, los cuales pueden dificultar el proceso de segmentación y análisis de las lesiones. Estas imágenes se han descartado debido a que los parches podrían afectar la precisión y confiabilidad de los resultados.

3. Imágenes con señalizaciónes de tinta: Algunas imágenes presentan zonas alrededor de la lesión marcadas con tinta, con el propósito de señalar o encerrar la lesión.

4. Imágenes con aplicación de gel: También se han identificado imágenes en las cuales se ha aplicado lo que parece ser un gel en la lesión. Estas imágenes pueden presentar características visuales distintas debido a la presencia del gel.

A continuación se presentan algunas imágenes que ilustran los casos mencionados anteriormente. Esto servirá como una visualización de los diferentes escenarios identificados en el conjunto de datos.

<div class="row" style = "display: flex; justify-content: center;">
  <div class="column">
    <figure>
      <!-- Incluir camino a la primera imagen a mostrar -->
      <img src="../images/ejemplo_1.jpg" width="250">
      <figcaption>
        fig_ej1 :: Ejemplo - Imagen con bordes negros.
      </figcaption>
    </figure>
  </div>
  
  <div class="column">
    <figure>
      <!-- Incluir camino a la segunda imagen a mostrar -->
      <img src="../images/ejemplo_2.jpg" width="250">
      <figcaption>
        fig_ej2 :: Ejemplo - Imagen con parches.
      </figcaption>
    </figure>
  </div>
</div>

<div class="row" style = "display: flex; justify-content: center;">
  <div class="column">
    <figure>
      <!-- Incluir camino a la tercera imagen a mostrar -->
      <img src="../images/ejemplo_3.jpg" width="250">
      <figcaption>
        fig_ej3 :: Ejemplo - Imagen con marcas de tinta.
      </figcaption>
    </figure>
  </div>
  
  <div class="column">
    <figure>
      <!-- Incluir camino a la cuarta imagen a mostrar -->
      <img src="../images/ejemplo_4.jpg" width="250">
      <figcaption>
        fig_ej4 :: Ejemplo - Imagen con aplicación de gel.
      </figcaption>
    </figure>
  </div>
</div>

Todos los casos mencionados anteriormente pueden plantear inconvenientes al realizar la segmentación de las lesiones de piel en general. La presencia de bordes negros, marcaciones de tinta o la aplicación de gel en algunos casos, pueden introducir elementos adicionales que dificultan la identificación precisa de la región de interés.

## Subbase ISIC-2018
Debido a la gran variedad de imágenes en el connjunto de entrenamiento y como estos pueden afectar al momento de evaluar la segmentación, también se ha incorporado una subbase de ISIC-2018 brindada por un docente para tener un conjunto adicional en el cual se pueda evaluar la segmentación, en el cual la cantidad de casos patológicos comentados anteriormente se ve reducida.


