# 🧪 QA Manual Testing – Portal Web de Ventas (SKU Sync)

> Proyecto de pruebas manuales sobre el flujo de carga y sincronización de SKUs entre SAP y el portal web de ventas corporativo.

---

## 📌 Contexto del Proyecto

Durante mi práctica profesional en **GONHER** (2024–2025), participé en el equipo de TI Comercial donde uno de los procesos críticos era la carga de nuevos productos (SKUs) al sistema SAP y su posterior visibilidad en el portal web de ventas.

**El problema recurrente:** los SKUs se cargaban correctamente en SAP pero **no se reflejaban en el portal web**, lo que afectaba directamente las operaciones del área comercial.

Mi rol fue ejecutar pruebas manuales para validar el flujo completo, identificar en qué punto fallaba la sincronización y documentar los defectos para su seguimiento.

---

## 🗂️ Estructura del Repositorio

```
📁 test-cases/
   └── TC-001_carga-sku-sap.md
   └── TC-002_sincronizacion-portal.md
   └── TC-003_visibilidad-producto-web.md
📁 bug-reports/
   └── BUG-001_sku-no-visible-portal.md
   └── BUG-002_precio-no-actualizado.md
📁 evidencias/
   └── (capturas de pantalla de ejecución)
README.md
```

---

## ✅ Casos de Prueba Ejecutados

| ID | Módulo | Descripción | Resultado |
|----|--------|-------------|-----------|
| TC-001 | SAP | Carga de SKU con datos completos | ✅ PASS |
| TC-002 | SAP → Portal | Sincronización de SKU al portal web | ❌ FAIL |
| TC-003 | Portal Web | Visibilidad del producto en catálogo | ❌ FAIL |
| TC-004 | SAP | Carga de SKU con campos incompletos | ✅ PASS (error esperado) |
| TC-005 | Portal Web | Actualización de precio en tiempo real | ⚠️ INTERMITENTE |

---

## 🐛 Bugs Reportados

| ID | Severidad | Descripción | Estado |
|----|-----------|-------------|--------|
| BUG-001 | 🔴 Alta | SKU cargado en SAP no aparece en portal web | Reportado |
| BUG-002 | 🟡 Media | Precio desactualizado en portal tras modificación en SAP | Reportado |

---

## 🛠️ Herramientas Utilizadas

- **SAP** – Carga y gestión de SKUs mediante transacciones
- **Excel** – Documentación y seguimiento de casos de prueba y bugs
- **Jira** – Registro y seguimiento de defectos
- **Navegador** – Validación manual en portal web de ventas

---

## 📚 Habilidades Demostradas

- Diseño y ejecución de casos de prueba manuales
- Identificación y documentación de defectos
- Pruebas de integración entre sistemas (SAP ↔ Portal Web)
- Seguimiento del ciclo de vida de un bug
- Comunicación de resultados al equipo de desarrollo

---

## 👤 Autor

**Misael Antúnez Monsivais**  
QA Tester Jr. | TSU Desarrollo de Software y TI  
📧 gantunez895@gmail.com  
📍 Santa Catarina, N.L.
