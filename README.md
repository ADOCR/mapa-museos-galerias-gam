# Mapa interactivo de museos y salas de arte en la Gran Área Metropolitana

## Descripción del proyecto

Este repositorio contiene un mapa interactivo de museos y salas de arte ubicados en la Gran Área Metropolitana de Costa Rica. El mapa busca facilitar la identificación de espacios culturales visitables, mostrando su ubicación territorial y datos básicos de consulta como nombre, tipo de espacio, cantón, sitio web, teléfono e imagen de referencia.

El producto fue elaborado como parte de una actividad práctica orientada a comunicar elementos del patrimonio cultural mediante herramientas cartográficas digitales.

## Objetivo del mapa

Mostrar la distribución espacial de museos y salas de arte en la Gran Área Metropolitana, permitiendo que las personas usuarias identifiquen qué espacios culturales existen, en qué cantón se ubican y cómo pueden acceder a información básica para visitarlos.

## Tema seleccionado

**Museos y salas de arte en la Gran Área Metropolitana**

El tema se seleccionó porque estos espacios forman parte del patrimonio cultural accesible al público y cumplen funciones educativas, históricas, artísticas y de difusión cultural.

## Fuentes de datos

Los datos geográficos fueron obtenidos mediante una consulta en **OpenStreetMap**, utilizando **Overpass Turbo**.

La consulta empleada fue:

```overpass
[out:csv(::type,::id,name,tourism,museum,amenity,"addr:city",website,phone,::lat,::lon; true; ",")][timeout:60];
(
  nwr["tourism"="museum"]({{bbox}});
  nwr["tourism"="gallery"]({{bbox}});
);
out center;
```

La información fue organizada en una tabla con campos como:

- nombre
- tipo general
- subtipo OSM
- ciudad o cantón
- latitud
- longitud
- sitio web
- teléfono
- información para ventanas emergentes del mapa

Los datos de contacto fueron complementados mediante revisión de sitios institucionales, páginas oficiales y fuentes disponibles en línea.

## Metodología resumida

1. Se definió el tema del mapa: museos y salas de arte en la Gran Área Metropolitana.
2. Se realizó una consulta en OpenStreetMap mediante Overpass Turbo, usando las etiquetas `tourism=museum` y `tourism=gallery`.
3. Los resultados fueron exportados en formato tabular.
4. La tabla fue revisada y organizada para su uso en QGIS.
5. Se añadieron campos complementarios como tipo de espacio, ciudad, sitio web, teléfono e imagen.
6. La tabla fue importada en QGIS como capa de puntos usando coordenadas en WGS 84 / EPSG:4326.
7. Se incorporó una capa de cantones para contextualizar territorialmente los espacios culturales.
8. El mapa fue exportado como mapa interactivo mediante qgis2web.
9. Los archivos resultantes fueron preparados para su publicación en GitHub.

## Sistema de coordenadas

Los puntos del mapa utilizan el sistema de referencia:

**WGS 84 / EPSG:4326**

En QGIS, la importación de la tabla debe realizarse con:

- **Campo X:** longitud
- **Campo Y:** latitud





## Visualización del mapa

El mapa puede abrirse directamente desde el archivo:

```text
index.html
```
o visitando el sitio web: [el sitio web: (https://adocr.github.io/mapa-museos-galerias-gam/)





## Autoría

Proyecto elaborado por:

**Adonis**

Curso:

**SP-6095 Antropología en la era digital: Herramientaspara la investigación y la representación.**

Año:

**2026**
