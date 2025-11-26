# 📊 **Análisis de Usabilidad – Sprint de 3 Días**
Basado en los resultados recopilados de los tres participantes y en el protocolo definido en **# Plan de Pruebas (Sprint de 3 Días) – HCI Credit Card Manager**, aquí se presenta un **análisis sintético, estructurado y accionable** conforme a la metodología definida.

---

# ## 1. Síntesis General de Resultados

### ** Conclusión Ejecutiva**
Los tres usuarios lograron completar todas las tareas clave del flujo —registro, creación de tarjeta, registro de gastos y recuperación de errores— sin bloqueos críticos. La tasa de éxito fue del 100% y la satisfacción percibida (SEQ = 6.5 promedio) está por encima del estándar aceptable (≥5.5).

Sin embargo, emergen patrones de fricción que, si bien no impiden completar las tareas, **reducen eficiencia y claridad cognitiva**, especialmente en:

- Ambigüedad de placeholders  
- Interpretación de categorías  
- Validaciones que podrían predecirse antes del input  
- Jerarquía visual insuficiente para ciertos campos

---

## 2. Matriz de Rendimiento Consolidada (ISO 9241-11)

| Métrica | Resultado Global | Interpretación |
|--------|------------------|----------------|
| **Efectividad (Tasa de éxito)** | **100%** | Todas las tareas fueron completadas por todos los participantes |
| **Eficiencia (Tiempo promedio por tarea)** | **≈ 38–45 seg** | Variabilidad aceptable, pero con oportunidades claras de reducción de clics |
| **SEQ promedio (Satisfacción)** | **6.5 / 7** | Alto nivel de facilidad percibida |
| **Errores críticos** | **0** | Ningún dead-end o pérdida de datos |

---

# ## 3. Patrones de Comportamiento Observados

### ** 3.1 Consistencia entre usuarios**
Los tres participantes muestran patrones similares:

- Confusión inicial con **placeholders que parecen valores reales**
- Selección incorrecta o tardía de **categorías de gasto**
- Duda sobre requisitos de clave al registrarse (la interfaz no los anticipa)
- Todos verifican visualmente la previsualización (Tarea 2), pero lo hacen por **desconfianza más que por claridad visual del layout**

### **🔍 3.2 Diferencias entre usuarios**
Aunque la tasa de éxito fue total…

- Los novatos tardan más en identificar campos relevantes de la pantalla  
- Los participantes con mayor experiencia digital corrigen errores más rápido  
- Un usuario requirió **2 intentos** para comprender la validación del límite negativo (Tarea 4)

---

# ## 4. Análisis según las heurísticas de Nielsen

### **🟥 4.1 Problemas Críticos (0 encontrados)**
No se registraron problemas que bloquearan el flujo, en línea con los criterios de aprobación del sprint.

---

### **🟧 4.2 Problemas Importantes**

#### **1. Ambigüedad en placeholders**
- Generan interpretación errónea de que existen datos precargados.  
- Afecta Tareas 1, 2 y 3.  
- Viola **H2: Relación entre sistema y mundo real**.

#### **2. Jerarquía visual insuficiente**
- El campo de categoría no destaca como interacción obligatoria.  
- Contribuye a errores de clasificación.  
- Viola **H8: Estética y diseño minimalista**.

#### **3. Validaciones tardías**
- El sistema muestra errores sólo después de enviar valores incorrectos.  
- Ejemplo claro: límite negativo en Tarea 4.  
- Limita **H5: Prevención de errores**.

---

### **🟨 4.3 Problemas Menores**

- Etiquetas y textos poco predictivos.  
- Mensajes de error muy técnicos, no explican el *por qué*.  
- Interacciones con más clics de lo necesario (violación ligera a Ley de Fitts).

---

# ## 5. Insights por Tarea (alineado con el documento base)

### **Tarea 1: Registro**
- Usuarios completan sin asistencia, pero todos dudan sobre contraseñas.  
- Falta claridad anticipada → **añadir checklist de requisitos**.

### **Tarea 2: Agregar tarjeta**
- Ningún error crítico, pero la verificación visual ocurre porque *el diseño no genera confianza inmediata*.

### **Tarea 3: Registrar gasto**
- Tiempo más alto por **elección de categoría**.  
- Se sugiere convertir categorías frecuentes en accesos rápidos.

### **Tarea 4: Recuperación de error**
- El sistema advierte error correctamente.  
- Mensaje actual carece de explicación clara → mejorar semántica del error.

---

# ## 6. Recomendaciones Accionables (Priorizadas)

### **🟥 Nivel Crítico (resolver antes del próximo sprint)**
1. **Rediseñar placeholders**  
2. **Mejorar jerarquía visual de campos obligatorios**  
3. **Implementar validaciones predictivas (pre-submit)**

### **🟧 Nivel Importante (Sprint siguiente)**
1. Auto-categorizar gastos por patrones comunes  
2. Ajustar copywriting de errores para que incluya causa + solución  
3. Simplificar flujo de registro (menos pasos, más claridad)

### **🟨 Nivel Menor (en mantenimiento continuo)**
1. Estética general más minimalista  
2. Reducir clics necesarios para registrar gastos  
3. Reforzar diseño de previsualización

---

# ## 7. Conclusión – ¿Se cumplieron los criterios del sprint?

| Criterio | Resultado | Estado |
|---------|-----------|--------|
| **Tasa de finalización 100%** | Sí | ✔ |
| **Cero errores críticos** | Sí | ✔ |
| **SEQ ≥ 5.5** | Promedio = 6.5 | ✔ |
| **Evidencia audiovisual completa** | Sí | ✔ |