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
- imagen de referencia
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

## Estructura recomendada del repositorio

```text
/
├── index.html
├── README.md
├── data/
│   ├── museos_galerias.geojson
│   └── cantones.geojson
├── js/
├── css/
├── legend/
├── images/
│   └── captura_mapa.png
└── documentos/
    ├── tabla_museos_galerias.xlsx
    └── tabla_museos_galerias.csv
```

> Nota: la estructura puede variar según la forma en que qgis2web exporte el proyecto. Lo importante es mantener el archivo `index.html` en la raíz del repositorio y conservar las carpetas generadas por qgis2web.

## Archivos principales

| Archivo o carpeta | Descripción |
|---|---|
| `index.html` | Archivo principal del mapa interactivo. |
| `data/` | Carpeta con las capas geográficas exportadas. |
| `js/` | Scripts necesarios para el funcionamiento del mapa. |
| `css/` | Estilos visuales del mapa. |
| `legend/` | Elementos gráficos de la leyenda, si fueron generados. |
| `images/` | Imágenes usadas para documentación o ventanas emergentes. |
| `documentos/` | Tablas base utilizadas para construir el mapa. |
| `README.md` | Descripción general del proyecto y metodología. |

## Visualización del mapa

El mapa puede abrirse directamente desde el archivo:

```text
index.html
```

También puede publicarse mediante GitHub Pages.

### Enlace al mapa interactivo

Agregar aquí el enlace cuando el repositorio esté publicado:

```text
https://USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/
```

## Instrucciones para publicar en GitHub Pages

1. Crear un repositorio en GitHub.
2. Subir todos los archivos exportados por qgis2web.
3. Verificar que `index.html` esté en la raíz del repositorio.
4. Entrar a **Settings**.
5. Ir a **Pages**.
6. En **Branch**, seleccionar `main`.
7. Seleccionar la carpeta `/root`.
8. Guardar los cambios.
9. Esperar a que GitHub genere el enlace del sitio.

## Créditos y atribución

Los datos geográficos base provienen de OpenStreetMap. Se debe incluir la atribución correspondiente:

**Datos geográficos: © OpenStreetMap contributors**

El mapa fue procesado y diseñado en QGIS, y exportado como mapa interactivo mediante qgis2web.

## Limitaciones

Algunos registros pueden presentar campos incompletos, especialmente en sitio web, teléfono o imagen. Por esta razón, se recomienda revisar cada dato antes de usar el mapa como fuente definitiva de consulta pública.

También puede existir diferencia entre la información disponible en OpenStreetMap y los datos oficiales de cada institución cultural.

## Autoría

Proyecto elaborado por:

**Adonis**

Curso:

**Antropología y herramientas tecnológicas**

Año:

**2026**
