# Modelos 3D (capas)

El visor carga cada IFC como una capa con su propia barra de opacidad (0–100 %) en el panel **Capas**; en 0 % la capa se oculta.
La lista está en `index.html`, constante `MODELS` (nombre visible y archivo):

| Capa       | Archivo          | Contenido                                                |
|------------|------------------|----------------------------------------------------------|
| Estructura | `model.ifc`      | Revit 2026, IFC2X3: 208 columnas, 124 vigas, 67 losas    |
| Escaleras  | `escaleras.ifc`  | Revit 2026, IFC2X3: 23 escaleras, 71 tramos, 69 losas    |

- La primera capa es obligatoria; si otra falla, aparece deshabilitada como "no disponible".
- Todas comparten el mismo origen, así que los IFC exportados del mismo proyecto Revit
  (coordenadas compartidas) quedan alineados.
- Para actualizar un modelo, reemplazá su archivo manteniendo el nombre y cambiá
  `MODELS_UPDATED` en `index.html` (fecha AAAA-MM-DD que se muestra bajo el sello).
- Para sumar una capa, subí el IFC acá y agregá una línea a `MODELS`.

Los elementos con la propiedad `Certificated` = YES/TRUE se pintan en verde y suman a la barra
**Avance** (certificados / total de elementos de todas las capas). Hoy los dos IFC tienen todos
sus elementos certificados mediante el Pset `KORN_Avance` (`Certificated` = TRUE), agregado al final
de cada archivo. Si se reexporta desde Revit, hay que cargar la propiedad allá.
