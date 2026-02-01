# 📥 Guía de Importación de Datos

## ¿Para qué sirve?

La funcionalidad de importación te permite **ampliar la observabilidad** del dashboard sin necesidad de regenerar todo el HTML. Puedes:

- ✅ Agregar datos de nuevas campañas
- ✅ Incluir máquinas adicionales
- ✅ Actualizar datos de períodos recientes
- ✅ Reemplazar completamente el dataset si es necesario

## 📋 Requisitos del Archivo CSV

Tu archivo CSV **debe** contener estas columnas (en cualquier orden):

### Columnas Obligatorias:
- `common_unitname` - Nombre de la máquina/cosechadora
- `contratista` - Nombre del contratista
- `motor` - Estado del motor (ON/OFF)
- `time_of_fix_actual` - Fecha y hora del punto GPS
- `speed` - Velocidad en km/h
- `latitud` - Coordenada latitud
- `longitud` - Coordenada longitud

### Columnas Opcionales (pueden estar pero no se usan):
- `skycop_unitid`
- `fleet_name`
- `establecimiento`
- `parcela`
- `time_of_reception_actual`

## 🚀 Paso a Paso

### 1. Preparar tu CSV

**Ejemplo de formato correcto:**
```csv
common_unitname,contratista,motor,time_of_fix_actual,speed,latitud,longitud
CA1MARQUIN,MARQUIÑOS,ON,2026-02-01 10:30:00,4.5,-26.210037,-58.021249
CA1MARQUIN,MARQUIÑOS,ON,2026-02-01 10:30:30,4.8,-26.210087,-58.021299
```

**⚠️ Formato de fecha:** `YYYY-MM-DD HH:MM:SS`

### 2. Importar en el Dashboard

1. Abre el dashboard en tu navegador
2. Click en tab **"📥 Importar"**
3. Click en **"Seleccionar Archivo CSV"**
4. Elige tu archivo
5. Selecciona el modo:
   - **Agregar a datos existentes**: Combina con lo que ya tienes
   - **Reemplazar datos existentes**: Borra todo y usa solo el nuevo archivo

### 3. Procesar

1. Click en **"📊 Procesar Archivo"**
2. El sistema validará automáticamente:
   - ✅ Estructura del CSV
   - ✅ Columnas requeridas
   - ✅ Formato de datos
   - ✅ Coordenadas válidas

### 4. Vista Previa

Verás un resumen con:
- 📊 Total de registros procesados
- 🚜 Número de máquinas detectadas
- 📋 Lista de máquinas con días de datos

### 5. Confirmar

1. Revisa la información
2. Click en **"Confirmar"** para aplicar los cambios
3. O **"Cancelar"** si algo no se ve bien

## 💡 Modos de Importación

### 🔄 Modo: Reemplazar

**Cuándo usar:**
- Quieres empezar de cero
- Tienes un dataset completamente nuevo
- Los datos viejos ya no son relevantes

**Qué pasa:**
- Se borran TODOS los datos actuales
- Se cargan solo los datos del nuevo CSV
- Las configuraciones de anchos se mantienen si la máquina existe

### 📥 Modo: Agregar

**Cuándo usar:**
- Quieres extender el período analizado
- Agregas máquinas nuevas al análisis
- Actualizas datos de días recientes

**Qué pasa:**
- Los datos existentes se mantienen
- Los nuevos datos se combinan
- Si una máquina ya existe, se agregan los días nuevos
- Las máquinas nuevas se añaden con ancho default (8.5m)

## 🎯 Ejemplo Práctico

Incluimos un archivo de ejemplo: `ejemplo_importacion.csv`

### Para probarlo:

1. Descarga `ejemplo_importacion.csv`
2. Ábrelo en el dashboard (tab Importar)
3. Selecciona modo **"Agregar a datos existentes"**
4. Procesa el archivo
5. Verás 2 máquinas nuevas:
   - `MACO_NUEVA` (AGRIPLUS)
   - `CA_TEST` (TEST_CONTRACTOR)

## ⚠️ Errores Comunes

### "Faltan columnas requeridas"
❌ Tu CSV no tiene todas las columnas necesarias
✅ Verifica que tenga: `common_unitname`, `contratista`, `motor`, `time_of_fix_actual`, `speed`, `latitud`, `longitud`

### "No se encontraron registros válidos"
❌ Las coordenadas están mal o vacías
✅ Verifica que latitud/longitud sean números válidos

### "El archivo está vacío"
❌ El CSV no tiene datos o solo tiene header
✅ Asegúrate de tener al menos 1 fila de datos

## 🔍 Validación Automática

El sistema aplica la **misma lógica de detección** que los datos originales:

✅ Velocidad: 2.5 - 6.5 km/h
✅ Motor: ON
✅ Distancia entre puntos: < 100m
✅ Cambio de rumbo: < 45°

Los puntos que no cumplan se descartan automáticamente.

## 💾 Persistencia

Después de importar:
- Los datos se quedan en el navegador (localStorage)
- Permanecen aunque cierres el navegador
- Se mantienen en futuras sesiones
- Para borrar: usa modo "Reemplazar" con un CSV vacío

## 🔄 Actualizar Datos Regularmente

**Flujo recomendado:**

1. Exporta datos de tu plataforma de tracking
2. Guarda como CSV con el formato correcto
3. Importa en modo "Agregar"
4. El dashboard se actualiza automáticamente

**Frecuencia sugerida:** Semanal o al final de cada campaña

## 📞 Soporte

¿Problemas con la importación?

- Verifica el formato del CSV con el ejemplo
- Asegúrate de tener las columnas requeridas
- Contacto: hvp@icodriver.com

---

Desarrollado por **Appoha**
