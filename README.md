# proyecto-mineria

# Problema: 
Predecir el rating del libro de un amigo.

Método: regresión 

# next steps 
Es un problema cold start ya que es un libro nuevo, de un autor nuevo y únicamente tenemos el libro en si. 
Cosas que tenemos: 
- Todo el texto del libro. 
- Genero y lenguaje.
- `author_rating`: lo podemos definir como `Novice`
- Podemos proponer precios, también jugar con esto.
Tenemos que limpiar el libro en sí, pero primero saber que se usará. Dada la naturaleza del problema, tendremos que usar NLP's para extraer cosas del texto, por lo que una vez teniendo el modelo ya podemos saber como limpiar el libro—me mando un word.
## Sacar features del libro usando NLP
Posibles features pueden ser: no de palabras, de oraciones, promedio del largo de las palabras, oraciones, score de sentimiento (textblob o vader ya tienen algo asi), buscar contestar que tan fácil es de leer.
Otra cosa que se peude hacer es transformarlo en un vector de frecuencia de palabras para un Bag of words lo cual se puede meter a una regresion 
## meter el registro del libro en el data set

| author_rating | publisher | publishing year | genre | language_code | sale_price | demas |
| ------------- | --------- | --------------- | ----- | ------------- | ---------- | ----- |
| Novice        | Unknown   | 2025            | tbd   | tbd           | tbd        | NaN   |
## entrenar el modelo con todos los demas libros
como ya definimos, usaremos random forest.
## predecir! 
podemos usar libros similares para validar el modelo :) 