# TC-001 – Carga de SKU en SAP con datos completos

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | TC-001 |
| **Módulo** | SAP – Gestión de Productos |
| **Tipo** | Prueba Funcional Manual |
| **Prioridad** | Alta |
| **Autor** | Misael Antúnez Monsivais |
| **Fecha** | 2024 |

---

## Objetivo

Verificar que un SKU con todos los campos obligatorios se carga correctamente en el sistema SAP y queda disponible para sincronización con el portal web.

---

## Precondiciones

- Usuario con acceso al módulo de gestión de productos en SAP
- SKU con información completa: código, descripción, precio, categoría, unidad de medida
- Portal web de ventas activo y accesible

---

## Pasos de Ejecución

| # | Paso | Datos de Prueba | Resultado Esperado |
|---|------|-----------------|-------------------|
| 1 | Iniciar sesión en SAP con usuario autorizado | Usuario: tester_qa / Perfil: Comercial | Login exitoso, acceso al menú principal |
| 2 | Navegar al módulo de gestión de productos | Menú → Comercial → Productos → Alta de SKU | Módulo cargado sin errores |
| 3 | Ingresar código de SKU | Ejemplo: `SKU-TEST-001` | Campo acepta el valor |
| 4 | Completar descripción del producto | "Producto de prueba QA 001" | Campo acepta hasta 100 caracteres |
| 5 | Ingresar precio unitario | `$250.00 MXN` | Campo acepta formato numérico correcto |
| 6 | Seleccionar categoría del producto | "Herramientas" | Categoría seleccionada de la lista |
| 7 | Seleccionar unidad de medida | "PZA" | Unidad asignada correctamente |
| 8 | Guardar el SKU | Clic en botón "Guardar" / transacción correspondiente | Mensaje de confirmación: "SKU guardado exitosamente" |
| 9 | Buscar el SKU recién creado en SAP | Código: `SKU-TEST-001` | SKU visible en el sistema con todos los datos correctos |

---

## Resultado Esperado

El SKU queda registrado en SAP con todos los campos completos y sin errores. El sistema muestra confirmación de alta exitosa.

## Resultado Obtenido

✅ **PASS** – El SKU se registra correctamente en SAP. Confirmación mostrada al usuario.

---

## Observaciones

- El tiempo de respuesta del sistema al guardar fue de aproximadamente 3–5 segundos.
- No se validó aún la sincronización con el portal web (ver TC-002).
