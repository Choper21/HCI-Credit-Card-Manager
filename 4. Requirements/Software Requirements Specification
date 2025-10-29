# 💳 HCI Credit Card Manager — Documento de Especificación de Requisitos (SRS) - IEEE 830 (Versión Ampliada en Markdown)

## 1. Introducción

### 1.1 Propósito

El propósito de este documento es especificar los **requisitos funcionales y no funcionales** de la aplicación **HCI Credit Card Manager**. Este sistema busca permitir a los usuarios registrar, gestionar y analizar sus tarjetas de crédito y movimientos asociados de forma segura, eficiente y accesible. 

### 1.2 Alcance

La aplicación proporcionará **gestión de cuentas, gestión de perfiles de tarjetas** (sin almacenar datos sensibles), **registro detallado de movimientos**, un **dashboard visual** para análisis, un sistema de **alertas** personalizables, funciones de **exportación de datos** y **configuración** de la aplicación. El diseño se centrará en una experiencia de usuario intuitiva y accesible (WCAG).

### 1.3 Definiciones, Acrónimos y Abreviaturas

* **HCI:** Human-Computer Interaction
* **SRS:** Software Requirements Specification
* **WCAG:** Web Content Accessibility Guidelines
* **RF / RNF:** Requisito Funcional / No Funcional
* **CRUD:** Create, Read, Update, Delete
* **PCI-DSS:** Payment Card Industry Data Security Standard

---

## 2. Descripción General del Sistema

### 2.1 Perspectiva del Producto

Aplicación autónoma (móvil) para la gestión financiera personal, enfocada en tarjetas de crédito. Actúa como un libro de contabilidad digital manual.

### 2.2 Funciones del Producto (Alto Nivel)

* **Gestión de Cuentas:** Registro y autenticación segura.
* **Gestión de Tarjetas:** Operaciones CRUD sobre las representaciones de las tarjetas.
* **Gestión de Movimientos:** Registro y categorización de gastos y pagos.
* **Análisis y Visualización:** Dashboard, historial y filtrado.
* **Notificaciones:** Alertas configurables de límites y pagos.
* **Portabilidad:** Exportación de datos.

### 2.3 Restricciones Clave

1.  **Ingreso Manual de Datos:** No hay conexión a APIs bancarias externas.
2.  **Seguridad (PCI-DSS):** **Nunca** se almacenarán el número completo de la tarjeta (PAN) ni el CVV/CVC.

---

## 3. Requisitos Específicos

### 3.1 Requisitos Funcionales (RF)

| ID | Requisito Detallado | Prioridad |
| :--- | :--- | :--- |
| **RF01** | **Registro de Usuario** | **Alta** |
| RF01.1 | Proveer formulario con: Nombre, Email, Contraseña. | Alta |
| RF01.4 | Requerir política de contraseña segura (mín. 8 chars, mayús, minús, número). | Alta |
| RF01.6 | Almacenar contraseña únicamente en formato **hashed** con *salt* (**bcrypt** o similar). | Alta |
| **RF02** | **Autenticación de Usuario** | **Alta** |
| RF02.2 | Iniciar sesión segura y validar credenciales. | Alta |
| RF02.4 | Proveer función de "Olvidé mi contraseña" (enlace/token de un solo uso). | Alta |
| **RF03** | **Agregar Tarjeta de Crédito** | **Alta** |
| RF03.1 | Permitir registro manual de: Alias, Banco, **Últimos 4 dígitos**, Límite de Crédito, Fecha de Cierre, Fecha Límite de Pago. | Alta |
| RF03.3 | Validar que el "Límite de Crédito" sea un valor numérico positivo. | Alta |
| **RF04** | **Editar o Eliminar Tarjeta** | **Alta** |
| RF04.3 | Al eliminar, mostrar modal de confirmación informando de la **eliminación en cascada** de movimientos. | Alta |
| **RF05** | **Registrar Movimiento (Gasto/Pago)** | **Alta** |
| RF05.2 | Formulario debe incluir: Tarjeta Asociada, Tipo (Gasto/Pago), Monto, Fecha/Hora, Descripción, **Categoría**. | Alta |
| RF05.5 | **Gasto** debe sumarse al saldo deudor de la tarjeta. | Alta |
| RF05.6 | **Pago** debe restarse al saldo deudor de la tarjeta. | Alta |
| **RF06** | **Visualizar Historial de Movimientos** | **Alta** |
| RF06.3 | Permitir filtrar por: Tarjeta específica, Rango de Fechas, Categoría y Tipo. | Alta |
| **RF07** | **Dashboard Financiero** | **Alta** |
| RF07.2 | Widget de "Resumen por Tarjeta" debe mostrar: Saldo Deudor Actual, Límite, Crédito Disponible y Próxima Fecha de Pago. | Alta |
| RF07.4 | Incluir gráfico de distribución de gastos por categoría (para el período seleccionado). | Alta |
| **RF08** | **Alertas de Límite de Gasto** | **Media** |
| RF08.1 | Permitir configurar un **umbral de alerta (%)** para el límite de crédito por tarjeta. | Media |
| RF08.2 | Generar notificación *in-app* o *push* cuando el saldo deudor exceda el umbral. | Media |
| **RF09** | **Exportar Información** | **Media** |
| RF09.3 | Soportar exportación en formato **CSV**. | Media |
| RF09.4 | Soportar exportación en formato **PDF** (reporte). | Baja |
| **RF10** | **Configuración de Preferencias** | **Baja** |
| RF10.2 | Permitir seleccionar un tema visual (Claro / Oscuro). | Baja |

---

### 3.2 Requisitos No Funcionales (RNF)

| ID | Categoría | Requisito Detallado | Prioridad |
| :--- | :--- | :--- | :--- |
| **RNF01** | **Usabilidad** | La interfaz debe ser **intuitiva y consistente** en todos los flujos. | Alta |
| **RNF02** | **Usabilidad** | Los flujos principales (**Agregar Tarjeta, Registrar Movimiento**) deben ser completables en un **máximo de 3 clics/taps** desde el dashboard. | Alta |
| RNF02.1 | Usabilidad | Tasa de éxito de pruebas de usabilidad (sin asistencia) $\geq$ **90%**. | Alta |
| **RNF03** | **Feedback (UI)** | Mostrar indicador de estado (`spinner`) para acciones que tomen **$>$ 100ms**. | Alta |
| RNF03.1 | Feedback (UI)| Mostrar `toast` o `snackbar` de éxito para acciones completadas. | Alta |
| **RNF05** | **Accesibilidad** | Cumplir con los criterios de Nivel **AA de las WCAG 2.1**. | Alta |
| RNF05.1 | Accesibilidad | Ratio de contraste de texto $\geq$ **4.5:1** con el fondo. | Alta |
| RNF05.2 | Accesibilidad | Compatibilidad total con **lectores de pantalla** (ARIA, semántica). | Alta |
| **RNF06** | **Rendimiento** | La carga de pantallas (transiciones) y el historial deben completarse en **$<$ 2 segundos** con hasta 1000 registros. | Alta |
| **RNF07** | **Seguridad** | Comunicación cliente-servidor exclusivamente sobre **HTTPS (TLS 1.3)**. | Alta |
| RNF07.1 | Seguridad | **Prohibición estricta** de almacenar PAN y CVV. | Crítica |
| RNF07.2 | Seguridad | Contraseñas con **bcrypt** (costo $\geq$ 12). | Alta |
| RNF07.4 | Seguridad | (Móvil) Requerir autenticación biométrica/PIN al reanudar la app desde el fondo (después de 5 min). | Media |
| **RNF08** | **Compatibilidad** | (Web) Compatible con las **2 últimas versiones** de Chrome, Firefox, Safari. | Alta |
| RNF08.2 | Compatibilidad | Diseño **responsive** y adaptable desde móvil (360px) hasta escritorio (1920px). | Alta |
| **RNF10** | **Recuperación de Errores** | Mensajes de error de validación mostrados **inline** y en lenguaje **no técnico**. | Alta |
| RNF11 | Documentación | Incluir un **"Primer Tour" (Onboarding)** para nuevos usuarios. | Media |

---

## 4. Anexos

* **Anexo A: Casos de Uso Detallados:** (Incluir precondiciones, flujos principales y alternativos para RF03, RF05, RF06).
* **Anexo B: Mockups y Prototipos de UI/UX:** (Referencia a artefactos de diseño).
* **Anexo C: Diagrama de Flujo de Interacción:** (Diagramas de navegación).
* **Anexo D: Modelo de Datos:** (Diagrama Entidad-Relación: Usuarios, Tarjetas, Movimientos, Categorías).

---