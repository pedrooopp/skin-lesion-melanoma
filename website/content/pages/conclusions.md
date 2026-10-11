Title: Conclusiones
Date: 2023-07-03
Category: Page
Ordinal: 005

<style>
    table {
        border-collapse: collapse;
        width: 80%; /* Ajusta el ancho de la tabla según tus necesidades */
    }

    th, td {
        border: 1px solid black;
        padding: 8px;
        text-align: center;
        vertical-align: middle;
    }

    img {
      margin: 1px; /* Adjust the value to change the distance */
    }
</style>

# Resultado y conclusión
Las matrices de confusión del modelo final evaluado en el conjunto de prueba se presentan en la fígura {#cm_comp}.

<center>
  <div class="column">
    <figure>
      <!-- Incluir camino a la segunda imagen a mostrar -->
    <img src="../images/cm_comparacion_test.png" width="900">
    <figcaption>
      cm_comp:: Matrices de confusión de test para el modelo final y el modelo de referencia.
    </figcaption>
    </figure>
  </div>
</center>

Observando las matrices de confusión, es posible concluir que a pesar de tener menos falsos negativos en el modelo final, la cantidad de falsos positivos es significativamente mayor que en el modelo de referencia. Se considera que esta diferencia se debe la segmentación ya que si bien se han segmentado imágenes que han alcanzado un índice de Jaccard razonable, existe la presencia de imágenes cuya segmentación es desfavorable y características extraídas pierden sentido, introduciendo ruido en los datos.

# Próximos pasos

Teniendo en cuenta los resultados presentados, es claro que uno de los desafios que se está teniendo al momento de evaluar el modelo es la segmentación dada por el algoritmo. Entonces, una posible mejora sería establecer ciertos criterios al momento de tomar la imagen, de forma de minimizar los casos patologicos de la segmentación. Tambien, podria ser de interes explorar distintos tipos de segmentación. Por ejemplo, se vió que el usar CNNs para segmentar las lesiones brinda buenos resultados. 

Adicionalmente, se podrian explorar nuevas características que involucren la forma de la lesión, el tamaño, el borde y la simetria, ya que las reglas que usan los dermatologos tienen en cuenta estos aspectos pero las caracteristicas que fueron extraidas no lo tienen presentes. Además, contar con un mayor número de imágenes para el entrenamiento podría potenciar el rendimiento del modelo, ya que permitiría una mejor comprensión de las características distintivas que definen las diferentes clases, lo que llevaría a una clasificación más precisa y efectiva.