# 🌾 Agriplus Dashboard - Sistema de Análisis de Cosecha

Dashboard interactivo profesional para visualización y análisis de datos de cosecha de arroz en tiempo real.

## ✨ Características Principales

### 📊 **Análisis en Tiempo Real**
- Filtrado dinámico por rango de fechas
- Selección múltiple de máquinas
- Cálculo automático de hectáreas cosechadas
- Visualización GPS en mapa interactivo
- Detección inteligente de trabajo vs traslado

### ⚙️ **Configuración Avanzada**
- **Ancho de labor configurable por máquina**
- Todas las máquinas inician con 8.5m por defecto
- Posibilidad de ajustar individualmente según el cabezal
- Recálculo automático al cambiar configuraciones
- Persistencia de configuraciones en el navegador

### 📥 **Importación de Datos**
- **Carga de nuevos CSVs directamente desde el navegador**
- Validación automática de formato
- Vista previa antes de confirmar
- Modo agregar o reemplazar datos
- Procesamiento con la misma lógica de detección

### 📈 **Gráficos y Reportes**
- Gráfico de línea: Evolución diaria de hectáreas
- Gráfico de barras: Comparación por contratista
- Exportación a Excel con todos los detalles
- Generación de reportes en PDF

### 🎨 **Diseño Profesional**
- Interfaz moderna con tabs organizados
- Colores temáticos de agricultura
- Responsive y optimizado para desktop
- Animaciones suaves y UX intuitiva

## 🎯 Lógica de Detección

El sistema clasifica automáticamente puntos GPS como "trabajo de cosecha" aplicando:

1. ✅ **Velocidad**: 2.5 - 6.5 km/h (velocidad típica de cosecha de arroz)
2. ✅ **Motor encendido**: Solo puntos con motor ON
3. ✅ **Distancia entre puntos**: Máximo 100m (filtra traslados largos)
4. ✅ **Análisis de rumbo**: Cambios máximo 45° (detecta trabajo en línea recta vs curvas)
5. ✅ **Ancho de labor**: Configurable por máquina (default 8.5m)

**Fórmula:**
```
Hectáreas = (Distancia trabajada en metros × Ancho de labor en metros) / 10,000
```

## 🚀 Cómo Usar

### Análisis de Datos

1. **Seleccionar Período**
   - Define fecha desde/hasta
   - Click en "Aplicar"

2. **Elegir Máquinas**
   - Usa checkboxes individuales
   - O botones "Todas"/"Ninguna"
   - Búsqueda por nombre o contratista

3. **Ver Resultados**
   - Panel muestra total de hectáreas
   - Detalle por máquina ordenado
   - Mapa con recorridos GPS

### Configurar Anchos de Labor

1. Ir a tab **"⚙️ Configuración"**
2. Ajustar ancho (en metros) para cada máquina
3. Click en **"💾 Guardar Cambios"**
4. Las hectáreas se recalculan automáticamente

**Opciones rápidas:**
- Editar directo en lista de máquinas (tab Análisis)
- Restaurar todos a default con **"↺ Restaurar Default"**

### Importar Nuevos Datos

1. Ir a tab **"📥 Importar"**
2. Seleccionar archivo CSV con nuevos datos
3. Elegir modo:
   - **Agregar**: Combina con datos existentes
   - **Reemplazar**: Sustituye todos los datos
4. Click en **"📊 Procesar Archivo"**
5. Revisar vista previa
6. Confirmar importación

**Formato requerido del CSV:**
```
skycop_unitid, common_unitname, fleet_name, contratista, establecimiento,
parcela, motor, time_of_fix_actual, time_of_reception_actual,
speed, latitud, longitud
```

### Exportar Datos

1. Ir a tab **"💾 Exportar"**
2. Elegir formato:
   - **Excel**: Incluye máquina, fecha, ancho, hectáreas, distancia
   - **PDF**: Reporte ejecutivo con totales

## 📈 Métricas del Proyecto

- **35 máquinas** monitoreadas
- **9 contratistas** activos
- **~2,400 hectáreas** cosechadas (enero 2026)
- **847,560 puntos GPS** procesados
- **91,677 puntos** clasificados como trabajo (10.8%)

## 🛠️ Tecnologías

- **Frontend**: HTML5, CSS3, JavaScript ES6
- **Mapas**: Leaflet.js + OpenStreetMap
- **Gráficos**: Chart.js
- **Exportación**: SheetJS (Excel) + jsPDF
- **Almacenamiento**: LocalStorage API

## 📂 Estructura de Datos

```json
{
  "maquina_id": {
    "contratista": "NOMBRE",
    "color": "#hexcolor",
    "ancho_default": 8.5,
    "dias": {
      "2026-01-15": {
        "distancia_m": 125000.50,
        "puntos_trabajo": 1234,
        "puntos": [...]
      }
    }
  }
}
```



## 🔒 Notas de Seguridad

- Los datos se procesan 100% en el navegador
- No hay transmisión a servidores externos
- Configuraciones guardadas localmente (localStorage)
- Safe para datos sensibles de producción

## 📝 Próximas Mejoras Sugeridas

- [x] Importación de nuevos datos CSV ✅
- [ ] Comparación entre múltiples campañas/períodos
- [ ] Alertas de rendimiento bajo
- [ ] Integración con API backend
- [ ] Modo offline (PWA)
- [ ] Filtros avanzados por establecimiento/parcela
- [ ] Exportación de configuración de anchos

## 📧 Contacto

Desarrollado por **Appoha**
Email: hvp@icodriver.com

---

🌾 **Agriplus** - Tecnología al servicio del campo
