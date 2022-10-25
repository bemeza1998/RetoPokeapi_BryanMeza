# Frontend ApiPokemon

Este proyecto fue generedo con Angular CLI version 14.1.0.

## Servidor de desarrollo

Ejecutando el comando `ng serve` se ejecuta un servidor de desarrollo local. Accediendo a la URL `http://localhost:4200/`, se mostrará el index.html correspondiente a la página principal de la aplicación.

## Creación de elementos

Con el comando `ng g m <module-name>` se realizó la creación de los módulos pokemon, el cual contiene los componentes relacionados a mostrar pokemons y sus servicios, el módulo shared el cual contiene los componenetes compartidos en la aplicación como el encabezado, y el módulo app-routing para estrablecer las rutas de nuestra aplicación.
Con el comando `ng g c <component-name>` se realizó la creación de los componentes en cada uno de los módulos, como por ejemplo el encabezado.
Con el comando `ng g s <service-name>` se creó el servicio para el módulo pokemon, el cual realiza las peticiones al backend y recupera los pokemon de la base de datos MongoDB.

Los modulos creados anteriormente, fueron importados en el modulo principal.

## Módulo pokemon

Este módulo contiene una interface en donde se establecieron los atributos de un Pokemon para que al momento de traerlos de la BD, tener un mapeo adecuado, ademas de que TypeScript nos pueda dar sugerencias.
En la carpeta de pages, se tiene el componente de `listado-pokemon`, el cual muestra un input para buscar pokemons en base a un término, además se muestran varios pokemons en la página principal haciendo uso de tarjetas de Bootstrap. Tambien se tiene el componente `ver-pokemon`, el cual muestra los datos de un pokemon en específico.
En la carpeta service, se tiene el servicio necesario para interactuar con el backend haciendo uso de `HttpClient`.

## Módulo shared

Este módulo contiene un componente correspondiente al header de la aplicación, el cual se va a mostrar en todas las rutas de la misma.

## Ejecución

Al ejecutar la aplicación, se muestran 10 pokemons en la página principal, en donde se puede observar su nombre, descripción y un botón para ver mas detalles. Al dar clic en uno de ellos, se muestran detalles mas específicos del pokemon seleccionado.