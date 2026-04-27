# Mapa interactivo de museos y salas de arte en la Gran Área Metropolitana

Este repositorio contiene un mapa interactivo de museos y salas de arte ubicados en la Gran Área Metropolitana de Costa Rica. El producto fue elaborado como parte de una actividad práctica orientada a representar elementos del patrimonio cultural mediante herramientas de cartografía digital.

## Objetivo del mapa

El mapa busca mostrar la distribución espacial de museos y salas de arte en la Gran Área Metropolitana, indicando su ubicación por cantón y ofreciendo información básica de contacto para facilitar posibles visitas. Con ello se pretende visibilizar estos espacios como parte del patrimonio cultural accesible al público.

## Descripción del contenido

Cada punto del mapa representa un museo o sala de arte. La información incluida puede contener:

- Nombre del espacio cultural
- Tipo general: museo o galería de arte
- Subtipo, cuando se encuentra disponible
- Cantón o ciudad
- Latitud y longitud
- Sitio web
- Teléfono
- Imagen de referencia
- Información emergente mediante ventanas popup

Además, el mapa incorpora una capa territorial de cantones para contextualizar la ubicación de los espacios culturales.

## Obtención de los datos

Los datos geográficos fueron obtenidos mediante una consulta en OpenStreetMap utilizando Overpass Turbo. La búsqueda se realizó con las etiquetas:

```overpass
tourism=museum
tourism=gallery```
