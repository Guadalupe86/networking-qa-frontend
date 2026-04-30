# BUG-001 – SKU cargado en SAP no se refleja en Portal Web de Ventas

## Información del Defecto

| Campo | Detalle |
|-------|---------|
| **ID** | BUG-001 |
| **Reportado por** | Misael Antúnez Monsivais |
| **Fecha reporte** | 2024 |
| **Severidad** | 🔴 Alta |
| **Prioridad** | Alta |
| **Estado** | Reportado |
| **Módulo afectado** | Integración SAP ↔ Portal Web de Ventas |
| **Caso de prueba origen** | TC-002 |

---

## Título

> SKU dado de alta correctamente en SAP no aparece en el catálogo del portal web de ventas tras el tiempo esperado de sincronización.

---

## Descripción

Al cargar un nuevo SKU en el sistema SAP con todos los campos requeridos y estatus "Activo", el producto **no se refleja en el portal web de ventas** incluso después de esperar el tiempo de sincronización establecido (5–15 minutos).

El impacto directo es que el área comercial no puede ofrecer ni vender los productos nuevos a través del portal, generando retrasos operativos.

---

## Pasos para Reproducir

1. Iniciar sesión en SAP con perfil Comercial
2. Navegar al módulo de alta de productos
3. Crear un nuevo SKU con todos los campos completos (código, descripción, precio, categoría, unidad)
4. Guardar el SKU — sistema confirma alta exitosa
5. Esperar 15 minutos
6. Acceder al portal web de ventas
7. Buscar el producto por código o nombre

---

## Resultado Esperado

El producto recién creado aparece en el catálogo del portal web con la información correspondiente.

## Resultado Obtenido

El producto **no aparece** en el portal web. La búsqueda no devuelve resultados. En SAP el SKU figura con estatus "Activo".

---

## Evidencia

| Archivo | Descripción |
|---------|-------------|
| `sap-sku-activo.png` | SKU-TEST-001 en SAP con estatus Activo |
| `portal-sin-producto.png` | Búsqueda en portal sin resultados para SKU-TEST-001 |

---

## Frecuencia

🔁 **Reproducible consistentemente** – Ocurre con todos los SKUs nuevos creados durante el período de pruebas.

---

## Impacto en el Negocio

- El equipo comercial no puede publicar nuevos productos en tiempo real
- Retraso en lanzamiento de productos al catálogo web
- Necesidad de intervención manual del equipo de TI para cada nuevo SKU

---

## Ambiente de Pruebas

| Componente | Versión / Detalle |
|------------|-------------------|
| Sistema | SAP (módulo comercial) |
| Portal | Portal web de ventas corporativo |
| Navegador | Google Chrome (última versión) |
| SO | Windows 10 |

---

## Notas Adicionales

- El problema no afecta a SKUs que ya existían previamente en el sistema.
- Se descartó error de usuario al reproducir con distintos perfiles y productos.
- Se escaló al equipo de desarrollo para revisión del proceso de sincronización entre SAP y el portal.
