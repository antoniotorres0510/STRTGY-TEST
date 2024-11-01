# STRTGY-TEST
Este scipt es una API sencilla construida con Flask que permite buscar películas utilizando la API de OMDb. La API permite busca películas por palabra clave y devuelve aquellas que tienen un `imdbRating` superior a 7.

## Funcionalidades
- Búsqueda de películas mediante una palabra clave.
- Filtrado de resultados para incluir solo películas con un `imdbRating` mayor a 7.
- Almacenamiento de `imdbID` de las películas en un archivo JSON.
- Almacenamiento de detalles de películas filtradas en otro archivo JSON.

## Requisitos
- Python 3.x
- Flask
- requests

## Instalación
1. Clona este repositorio o descarga el código.
2. Instala las dependencias necesarias:
   ```bash
   pip install Flask requests

### Recomendación:
3. Usar thunder client para pruebas de modificación(disponible en VS code).

## Uso practico:

Modifica el scrip para incluir tu clave de API de OMDb en la variable OMDB_API_KEY.
OMDB_API_KEY = 'tu_clave_de_api'
Realiza una solicitud GET a la API:
GET http://127.0.0.1:5000/strtgy?query=tu_palabra_clave
•	Reemplaza tu_palabra_clave con el término que desees buscar.

## Respuestas
•	Si la búsqueda es exitosa y hay películas con imdbRating > 7, recibirás un JSON con la lista de películas:
json
Copiar código
{
    "Movies": [
        {
            "Title": "Título de la película",
            "Year": "Año",
            "imdbID": "ID de IMDb",
            "Type": "Tipo",
            "Poster": "URL del poster",
            "imdbRating": "Calificación de IMDb"
        },
        ...
    ]
}
•	Si no se proporciona una palabra clave, la API devolverá un error:
{
    "error": "Por favor proporciona una palabra clave para la busqueda."
}
•	Si no se encuentran películas con un imdbRating mayor a 7:
{
    "message": "No se encontraron peliculas con un imdbRating mayor a 7."
}
•	Si hay un error al conectarse con la API de OMDb:
{
    "error": "Error al conectarse con la API de OMDb."
}
