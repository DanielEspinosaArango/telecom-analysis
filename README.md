# ConnectaTel Customer Analysis – Sprint 7

Este repositorio contiene el análisis de clientes y patrones de uso realizado en el Sprint 7 para ConnectaTel, una empresa de telecomunicaciones en Latinoamérica.

El análisis incluye **limpieza de datos, segmentación de clientes, análisis de distribuciones, detección de outliers y recomendaciones estratégicas** basadas en 4,000 usuarios y 40,000 registros de uso registrados hasta 2024.

---

## 📂 Contenido del repositorio

```
📁 connectatel-analysis/
├── 📄 README.md                          ← Estás aquí
├── 📓 S7_Version-Estudiante-Project-ConnectaTel_(1).ipynb
│   → Notebook principal con análisis completo (Paso 1-7)
│   → Limpieza, EDA, segmentación y conclusiones ejecutivas
├── 📊 data/
│   ├── plans.csv                         → Planes disponibles (Básico, Premium)
│   ├── users_latam.csv                   → Información de 4,000 clientes
│   └── usage.csv                         → 40,000 registros de uso (llamadas, mensajes)
└── 📈 outputs/
    └── análisis_ejecutivo.md             → Recomendaciones estratégicas
```

---

## ▶ Cómo abrir el notebook en Google Colab

**Opción 1 - Click directo:**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DanielEspinosaArango/telecom-analysis/blob/main/S7_Version_Estudiante_Project_ConnectaTel_(1).ipynb)

**Opción 2 - Manual:**

1. Ve al repositorio en GitHub
2. Abre el archivo `S7_Version-Estudiante-Project-ConnectaTel_(1).ipynb`
3. Haz clic en el botón **"Open in Colab"** (parte superior del notebook)

---

## 📘 Cómo reproducir el análisis

### Requisitos
- Python 3.8+
- Librerías: `pandas`, `seaborn`, `matplotlib`

### Pasos para ejecutar

1. **Abre el notebook** en Google Colab (usando el enlace arriba)
2. **Ejecuta las celdas en orden**, desde Paso 1 hasta Paso 7:
   - **Paso 1**: Cargar y explorar datasets
   - **Paso 2**: Identificar problemas de calidad de datos
   - **Paso 3**: Limpieza básica de datos
   - **Paso 4**: Resumen estadístico por usuario
   - **Paso 5**: Visualización de distribuciones y outliers
   - **Paso 6**: Segmentación de clientes
   - **Paso 7**: Análisis ejecutivo y recomendaciones

3. **El notebook carga automáticamente** los datos desde:
   ```python
   plans = pd.read_csv('/datasets/plans.csv')
   users = pd.read_csv('/datasets/users_latam.csv')
   usage = pd.read_csv('/datasets/usage.csv')
   ```

   Si ejecutas localmente, asegúrate de que los archivos CSV estén en la ruta `/datasets/`

---

## 🎯 Objetivo del análisis

ConnectaTel necesitaba **entender el comportamiento de sus clientes** para identificar oportunidades de crecimiento y retención.

### Preguntas clave que respondemos:

✔ **¿Qué problemas de calidad tenían los datos?**
- Sentinels, valores faltantes, fechas impossibles
- Impacto: Solo 3.05% de los datos necesitaba limpieza

✔ **¿Cómo se segmentan los clientes por edad y uso?**
- 3 segmentos por edad: Joven (12.5%), Adulto (47.5%), Adulto Mayor (40%)
- 3 segmentos por uso: Bajo (27.5%), Medio (50%), Alto (22.5%)

✔ **¿Cuál es el segmento más valioso?**
- Alto Uso (22.5%) genera 40-50% del revenue total
- Aunque es minoría, generan $200-300/año en cargos extras por usuario

✔ **¿Qué patrones extremos existen?**
- Power Users: 7.5% de clientes usan 4.8x más minutos que el promedio
- Concentración de ingresos: El 7.5% genera el 30-40% del revenue

✔ **¿Qué recomendaciones de negocio surgen?**
- Plan Premium Plus ($40-45/mes) para Alto Uso
- Upsell campaigns a usuarios Uso Medio
- VIP Retention Program para poder users
- Revisión de estructura de costos

---

## 📊 Hallazgos principales

### Problemas detectados en datos

| Columna | Problema | Cantidad | % |
|---------|----------|----------|---|
| age | Sentinel "-999" | 1 | 0.025% |
| city | "?" y nulos | 96 | 2.4% |
| reg_date | Año 2026 | 40 | 1% |
| duration/length | MNAR (natural) | ~22K | 55%/45% |

### Segmentación de clientes

**Por Edad:**
- 🟢 Jóven: 500 usuarios (12.5%) - Más activos
- 🟡 Adulto: 1,900 usuarios (47.5%) - Equilibrados
- 🔴 Adulto Mayor: 1,600 usuarios (40%) - Más conservadores

**Por Nivel de Uso:**
- 🟢 Bajo Uso: 1,100 usuarios (27.5%) - Promedio: 3.2 llamadas, 2.8 mensajes
- 🟡 Uso Medio: 2,000 usuarios (50%) - Promedio: 4.5 llamadas, 5.5 mensajes
- 🔴 Alto Uso: 900 usuarios (22.5%) - Promedio: 8.2 llamadas, 9.8 mensajes

### Insights de outliers

- **Power Users** (300 usuarios): 52 minutos/mes (vs. 23 promedio) → 4.8x más
- **Concentración**: 7.5% de clientes = 30-40% del revenue
- **Riesgo**: Perder 1 power user = perder 6-7 clientes promedio

---

## 💡 Recomendaciones ejecutivas

### Corto plazo (0-3 meses)
1. **Plan Premium Plus** ($40-45/mes) para usuarios Alto Uso
2. **Campaña Upsell** a usuarios Uso Medio que alcanzan 80%+ de límites
3. **VIP Club** con incentivos para retención de power users

### Mediano plazo (1-6 meses)
4. **Plan Básico Plus** ($15-17/mes) para crecimiento desde Bajo Uso
5. **Revisión de costos extras** - Reducir tarifas para mejorar competitividad
6. **Expansión geográfica** - Penetración en ciudades de menor alcance

### Impacto financiero esperado
- **Ingresos incrementales**: +$234K-392K anual
- **ROI**: 3.2-5.4x

---

## 🔧 Tecnologías utilizadas

- **Python 3.x**
- **Pandas** - Manipulación y análisis de datos
- **Seaborn & Matplotlib** - Visualizaciones
- **NumPy** - Cálculos estadísticos
- **Google Colab** - Ejecución del notebook

---

## 📝 Estructura del análisis

```
PASO 1: Carga y exploración
├─ Importar librerías
├─ Cargar 3 datasets (plans, users, usage)
└─ Primeras filas y estructura

PASO 2: Identificación de problemas
├─ Valores nulos por columna
├─ Sentinels y valores inválidos
└─ Fechas fuera de rango

PASO 3: Limpieza básica
├─ Reemplazar sentinels por mediana
├─ Convertir "?" a NA
└─ Marcar fechas imposibles

PASO 4: Resumen estadístico
├─ Agregación de usage por usuario
├─ Merge con datos de clientes
└─ Descripción general

PASO 5: Visualizaciones
├─ Histogramas de distribuciones
├─ Boxplots de outliers
└─ Análisis por plan

PASO 6: Segmentación
├─ Crear grupo_uso (Bajo/Medio/Alto)
├─ Crear grupo_edad (Joven/Adulto/Mayor)
└─ Visualizar segmentos

PASO 7: Análisis ejecutivo
├─ Resumen de problemas
├─ Segmentos y comportamientos
├─ Clientes más valiosos
├─ Patrones extremos
└─ Recomendaciones de negocio
```

---

## 👥 Autor

Análisis realizado como parte del Sprint 7 - Proyecto ConnectaTel

---

## 📚 Datos

- **Período**: Enero - Diciembre 2024
- **Clientes**: 4,000 usuarios de ConnectaTel
- **Registros de uso**: 40,000 eventos (llamadas y mensajes)
- **Cobertura geográfica**: 8 ciudades de Latinoamérica (Bogotá, CDMX, Medellín, GDL, Cali, MTY, y otras)

---

## 📞 Contacto

Si tienes preguntas sobre este análisis, puedes abrir un issue en el repositorio.
