## Casos de Uso 

### CU-01: Agregar Tarjeta de Crédito (RF03)

| Campo | Especificación |
| :--- | :--- |
| **Identificador** | CU-01 |
| **Nombre** | Agregar Tarjeta de Crédito |
| **Meta** | El usuario registra un nuevo perfil de tarjeta de crédito en el sistema para comenzar a rastrear su saldo y gastos. |
| **Actor Principal** | Usuario (Autenticado) |
| **Precondiciones** | 1. El usuario ha iniciado sesión exitosamente (RF02). 2. El usuario tiene acceso a la función "Agregar Tarjeta". |
| **Postcondición Éxito** | Una nueva tarjeta queda registrada en la base de datos (RF03.1) y el Dashboard (RF07) se actualiza con el nuevo perfil. |
| **Postcondición Fallo** | No se añade la tarjeta y el sistema muestra un mensaje de error claro (RNF10). |
| **Prioridad** | Alta |

#### Flujo Principal

| Paso | Acción del Actor | Respuesta del Sistema | Referencia RF |
| :--- | :--- | :--- | :--- |
| 1.0 | El Usuario navega al menú o botón de "Agregar Tarjeta". | El Sistema presenta el formulario de registro de tarjeta. | RF03 |
| 2.0 | El Usuario ingresa todos los datos obligatorios (Alias, Últimos 4 dígitos, Límite, Fecha de Cierre, Fecha de Pago). | (N/A) | RF03.1 |
| 3.0 | El Usuario pulsa el botón "Guardar Tarjeta". | El Sistema valida que todos los campos obligatorios cumplen las restricciones de formato (ej. Límite es numérico positivo). | RF03.2, RF03.3 |
| 4.0 | | El Sistema almacena el nuevo registro de tarjeta en la base de datos. | RF03 |
| 5.0 | | El Sistema redirige al Dashboard y muestra una notificación de éxito ("Tarjeta añadida exitosamente"). | RNF03.1, RF07 |

#### Flujos Alternativos

| ID | Desviación | Retorno al Paso |
| :--- | :--- | :--- |
| **2.1** | El Usuario omite un campo obligatorio o ingresa un formato incorrecto (ej. texto en Límite). | (Paso 2.0) El Sistema detecta el fallo y muestra un mensaje de error *inline* junto al campo afectado (RNF10). El flujo principal no se continúa hasta que se corrijan los errores. |
| **3.1** | El Usuario intenta cancelar la operación. | (Paso 1.0) El Sistema descarta la información ingresada y devuelve al usuario a la pantalla anterior o al Dashboard. |

---

### CU-02: Registrar Movimiento de Gasto (RF05)

| Campo | Especificación |
| :--- | :--- |
| **Identificador** | CU-02 |
| **Nombre** | Registrar Movimiento de Gasto |
| **Meta** | El usuario registra un gasto, asociándolo a una tarjeta específica y a una categoría, y el saldo deudor de dicha tarjeta se actualiza. |
| **Actor Principal** | Usuario (Autenticado) |
| **Precondiciones** | 1. El usuario ha iniciado sesión. 2. Existe al menos una tarjeta de crédito registrada (CU-01). 3. El usuario tiene acceso a la función "Registrar Movimiento". |
| **Postcondición Éxito** | El movimiento se registra, y el saldo deudor de la tarjeta asociada se incrementa por el monto del gasto (RF05.5). |
| **Postcondición Fallo** | No se crea el movimiento y el sistema notifica el error. |
| **Prioridad** | Alta |

#### Flujo Principal

| Paso | Acción del Actor | Respuesta del Sistema | Referencia RF |
| :--- | :--- | :--- | :--- |
| 1.0 | El Usuario navega a la función "Registrar Movimiento". | El Sistema presenta el formulario de registro de movimiento. | RF05 |
| 2.0 | El Usuario selecciona **"Gasto"** como Tipo de Movimiento. | (N/A) | RF05.2 |
| 3.0 | El Usuario completa los campos obligatorios: Tarjeta Asociada, Monto, Descripción y Categoría. | (N/A) | RF05.2, RF05.3 |
| 4.0 | El Usuario pulsa el botón "Guardar Gasto". | El Sistema valida que el Monto sea positivo y que todos los campos obligatorios estén llenos. | RF05.2 |
| 5.0 | | El Sistema registra el movimiento en la base de datos. | RF05 |
| 6.0 | | El Sistema recupera el saldo deudor actual de la Tarjeta Asociada y lo incrementa por el valor del Monto. | RF05.5 |
| 7.0 | | El Sistema muestra una notificación de éxito ("Gasto registrado") y actualiza el Dashboard para reflejar el cambio de saldo. | RNF03.1, RF07.2 |

#### Flujos Alternativos

| ID | Desviación | Retorno al Paso |
| :--- | :--- | :--- |
| **3.1** | El Usuario intenta registrar un Gasto sin haber seleccionado una Categoría. | (Paso 3.0) El Sistema marca el campo Categoría como requerido y bloquea el envío hasta que se seleccione una opción. | RF05.2 |
| **3.2** | El Usuario ingresa un Monto igual a cero o negativo. | (Paso 3.0) El Sistema rechaza el Monto y muestra un mensaje de error (RNF10) indicando que el gasto debe ser un valor positivo. | RF05.2 |
| **6.1** | El nuevo Gasto provoca que el "Saldo Deudor Actual" exceda el umbral de alerta configurado (RF08.1). | (Paso 7.0) Además de la notificación de éxito, el Sistema genera una alerta *in-app* y/o *push* (RF08.2) para notificar el incumplimiento del umbral. | RF08.2 |
