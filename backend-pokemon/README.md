# BackendPokemon

Este proyecto fue generedo con Java, haciendo uso del framework Springboot, y una base de datos MongoDB

## Servidor de desarrollo

Springboot nos brinda las herramientas necesarias para desplegar de forma rápida nuestro proyecto, por defecto se ejecuta en la URL `http://localhost:8080/`.

## Estructura de carpetas

Para trabajar de una forma mas eficiente, se utilizó una arquitecuta de N-capas, en donde la primera de estas, es la capa de modelo, luego tenemos la capa DAO, seguida de la capa de servicios y por último, la capa de recursos, acontinuación, se detallas más de cada una de estas.

## Capa model

Aqui se creo la clase correspondiente al Pokemon, se mapeo cada uno de los atributos con los de la coleccion Pokemon de la base de datos, como se trabajo con MongoDB, se utilizaron las anotaciones `@Document` y `@TypeAlias` para hacer referencia a la colección alojada en nuestra base de datos. Se establecio un id y los campos obligatorios mediante `@NotNull`.

## Capa DAO

En esta capa se tiene la inteface correspondite para acceder a los datos, para ello nuestra interface se extiende de `MongoRepository`, la cual nos servira para establecer los métodos con los que se consultan los pokemon.

## Capa service

Aquí se establece la lógica necesaria para interactuar con los datos, se tienen 3 métodos los cuales son:
    `listarPokemon()`: este método permite recuperar todos los pokemon de la BD;
    `buscarPorNombre(String nombre)`: este método permite buscar un pokemon por medio de su nombre exacto;
    `buscarPorTermino(String nombre)`: este método permite buscar pokemons en base a un término.

## Capa resource

Esta capa sirve para exponer los servicios creados mediante API REST, aqui se establece el path para acceder a la API, el cual es `/api/v1/pokemon`. Mediante la anotación `@GetMapping`, se exponen los métodos implementador para ser accedidos por medio de una solicitud HTTP de tipo GET.

## Ejecución

Al ejecutar la aplicación, se exponen los servicios mediante API REST y estos fueron probados haciendo uso de Postman, en donde se testeo cada endpoint y que estos funcionaran correctamente.