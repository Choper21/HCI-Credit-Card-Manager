# Plan de Pruebas (Sprint de 3 Días) - HCI Credit Card Manager

## 1. Introducción

### 1.1 Propósito
Este documento define el protocolo para un sprint de evaluación de usabilidad de 3 días de la aplicación "HCI Credit Card Manager". El objetivo es identificar fricciones críticas en la interacción humano-computadora mediante observación directa.

### 1.2 Alcance y Restricciones
**Pruebas de Usabilidad:** Ejecución de tareas con usuarios finales bajo protocolo "Think-aloud".  

**Restricción de Recursos:** El ciclo de pruebas será conducido por un único facilitador (quien actúa también como desarrollador).  

**Muestra:** 3 participantes.  

**Nota:** Aunque Jakob Nielsen recomienda 5 usuarios para descubrir el 85% de los problemas de usabilidad, una muestra de 3 usuarios es suficiente para identificar los problemas más críticos y bloqueantes (aprox. 65-70% de los errores de diseño) en iteraciones tempranas (Virzi, 1992).

---

## 2. Metodología

### 2.1 Protocolo de Pruebas con Usuarios
**Participantes:** 3 usuarios con conocimientos básicos de herramientas digitales.  

**Sesiones:** Individuales, 30-45 minutos.  

**Rol Unificado (Moderador-Desarrollador):**  
Dada la dualidad del rol, se aplicará un protocolo de no-intervención estricta. El moderador no debe ofrecer ayuda ni explicaciones a menos que el usuario se encuentre en un "callejón sin salida" (bloqueo total) por más de 1 minuto.

**Mitigación de Sesgo:** Se utilizarán guiones de lectura literal para evitar preguntas inductivas que puedan alterar el comportamiento del usuario.

**Registro:** Grabación de pantalla y audio para revisión posterior, eliminando la necesidad de tomar notas extensas en tiempo real.

### 2.2 Evaluación Heurística Simplificada
**Método:** Auto-evaluación crítica previa a las sesiones.  
**Referencia:** 10 Heurísticas de Usabilidad de Nielsen.

---

## 3. Escenarios de Prueba (Guiones Estandarizados)

**Instrucción al Moderador:** Leer textualmente la sección "Acción" al usuario. No parafrasear.

---

### **Tarea 1: Registro y Onboarding**
**Objetivo:** Evaluar la claridad de los requisitos de seguridad y la carga cognitiva del formulario.  

**Acción:** "Por favor, regístrate en la aplicación utilizando tu correo electrónico actual."  

**Criterio de Éxito (Binario):** El usuario completa el registro sin errores de validación que requieran más de 2 intentos de corrección.

---

### **Tarea 2: Visualización del Estado del Sistema (Feedback)**
**Objetivo:** Validar el Principio HCI #1 (Visibilidad del estado del sistema).  

**Acción:** "Agrega una nueva tarjeta de tipo 'Visa Oro'. Configura un límite de crédito de $50,000. Antes de guardar, verifica que lo que ingresaste es correcto."  

**Criterio de Éxito:** El usuario verifica visualmente la previsualización antes de confirmar la acción (comportamiento observado).

---

### **Tarea 3: Eficiencia de Uso (Ley de Fitts)**
**Objetivo:** Medir la eficiencia en tareas frecuentes.  

**Acción:** "Imagina que acabas de gastar $45 en un café. Registra este gasto en la tarjeta que acabas de crear lo más rápido que puedas."  

**Criterio de Éxito:** La tarea se completa en menos de 4 clics/toques desde el Dashboard principal.

---

### **Tarea 4: Recuperación de Errores**
**Objetivo:** Validar el Principio HCI #9 (Ayudar a los usuarios a reconocer, diagnosticar y recuperarse de errores).  

**Acción (Escenario Forzado):** "Intenta editar la tarjeta y cambia el límite de crédito a '-500'. Observa la respuesta del sistema y realiza la acción necesaria para corregirlo."  

**Criterio de Éxito:** El usuario identifica la causa del error mediante el mensaje del sistema y lo corrige sin solicitar asistencia al moderador.

---

## 4. Métricas de Evaluación (Formales)

Para garantizar la objetividad del análisis, se utilizarán definiciones estándar de la norma ISO 9241-11 (Efectividad, Eficiencia y Satisfacción).

### **Tasa de Éxito (Efectividad)**
**Definición:** Porcentaje de tareas completadas exitosamente sin asistencia externa.  
**Cálculo:** (Tareas completadas sin ayuda / Total de tareas) * 100.  
**Meta:** 100% para tareas críticas.

### **Tiempo en Tarea (Eficiencia)**
**Definición:** Tiempo transcurrido desde que el usuario termina de leer la instrucción hasta que el sistema confirma la finalización de la tarea.  
**Medición:** Cronometraje post-sesión (vía grabación).

### **Single Ease Question - SEQ (Satisfacción)**
**Definición:** Métrica estandarizada post-tarea para medir la dificultad percibida inmediata.  
**Instrumento:** Escala Likert de 7 puntos. "En general, ¿qué tan difícil o fácil fue completar esta tarea?" (1 = Muy difícil, 7 = Muy fácil).  
**Referencia:** Sauro & Lewis (2012) establecen que el promedio histórico aceptable para SEQ es aprox. 5.5.

---

## 5. Cronograma de Ejecución (3 Días)

### **DÍA 1: Preparación Técnica y Piloto**
**Mañana:** Revisión de guiones y verificación técnica de herramientas de grabación (OBS/QuickTime). Es crucial que el audio del usuario sea nítido.  

### **DÍA 2: Recolección de Datos (Ejecución)**
- **Sesión 1 (Usuario A):** 19:00 - 19:30  
- **Sesión 2 (Usuario B):** 19:30 - 20:00  
- **Sesión 3 (Usuario C):** 20:00 - 20:30  

### **DÍA 3: Análisis y Síntesis**
**Mañana:**  
- Revisión de grabaciones.  
- Extracción de métricas de tiempo (Eficiencia).  
- Tabulación de respuestas SEQ (Satisfacción).  
- Identificación de patrones de error (Efectividad).  

**Tarde:** Generación de entregables (Reporte y Video).

---

## 6. Entregables

### **6.1 Reporte Técnico de Usabilidad (Resumido)**
Documento formal que incluirá:  
- Matriz de Resultados: Tabla comparativa por tarea y usuario (Éxito/Fallo, Tiempo, Score SEQ).  
- Hallazgos Críticos: Lista de problemas de usabilidad clasificados por severidad (Crítico, Importante).  
- Conclusión basada en datos: Determinación objetiva de si el software cumple los criterios de aprobación.

---

## 7. Criterios de Aprobación del Sprint

El software se considerará validado desde la perspectiva HCI si se cumplen todas las siguientes condiciones objetivas al finalizar el Día 3:

- **Tasa de Finalización:** 100% de los 3 usuarios logran completar las Tareas 1 y 3 (críticas) sin asistencia del moderador.  
- **Límite de Errores Críticos:** No se detectan errores de diseño que causen un callejón sin salida (dead-end) o pérdida de datos.  
- **Satisfacción Mínima:** El promedio global del SEQ es ≥ 5.5.  
- **Evidencia:** Se cuenta con registro audiovisual completo de las 3 sesiones.
