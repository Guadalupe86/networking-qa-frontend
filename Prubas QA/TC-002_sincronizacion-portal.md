# TC-002 – Sincronización de SKU entre SAP y Portal Web

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | TC-002 |
| **Módulo** | Integración SAP → Portal Web de Ventas |
| **Tipo** | Prueba de Integración Manual |
| **Prioridad** | Alta |
| **Autor** | Misael Antúnez Monsivais |
| **Fecha** | 2024 |

---

## Objetivo

Verificar que un SKU cargado correctamente en SAP se sincroniza y aparece visible en el portal web de ventas dentro del tiempo esperado.

---

## Precondiciones

- TC-001 ejecutado con resultado PASS (SKU-TEST-001 cargado en SAP)
- Portal web de ventas accesible
- Sincronización entre sistemas programada o manual activa

---

## Pasos de Ejecución

| # | Paso | Datos de Prueba | Resultado Esperado |
|---|------|-----------------|-------------------|
| 1 | Confirmar que SKU-TEST-001 existe en SAP | Búsqueda por código en SAP | SKU visible con estatus "Activo" |
| 2 | Esperar tiempo estimado de sincronización | 5–15 minutos según configuración del sistema | — |
| 3 | Acceder al portal web de ventas | URL del portal corporativo | Portal carga sin errores |
| 4 | Buscar el producto por código SKU | Buscador del portal: `SKU-TEST-001` | Producto aparece en resultados |
| 5 | Verificar que la información coincide con SAP | Nombre, precio, categoría, unidad | Datos idénticos a los registrados en SAP |
| 6 | Verificar imagen y estado del producto | — | Producto con estatus visible/publicado |

---

## Resultado Esperado

El SKU aparece en el portal web con la misma información registrada en SAP, dentro del tiempo de sincronización establecido.

## Resultado Obtenido

❌ **FAIL** – El SKU no aparece en el portal web tras esperar el tiempo estimado de sincronización. El producto existe en SAP con estatus "Activo" pero no se refleja en el catálogo del portal.

**→ Se generó BUG-001 para documentar y dar seguimiento al defecto.**

---

## Evidencia

- Captura de SAP mostrando SKU-TEST-001 con estatus Activo
- Captura del portal web sin mostrar el producto en búsqueda
- Timestamp de ambas capturas para verificar tiempo transcurrido

---

## Observaciones

- El problema se presentó de forma consistente con múltiples SKUs nuevos.
- SKUs previamente cargados sí aparecían en el portal con normalidad.
- Se descartó error de usuario al repetir el proceso con distintos productos y obtener el mismo resultado.
