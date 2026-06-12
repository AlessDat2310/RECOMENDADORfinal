# RECOMENDADOR DE MÚSICA
Recomendador de Música a partir de Encuesta
# 🎵 Melodify - Sistema de Recomendación Musical

![Melodify Banner](https://images.pexels.com/photos/167636/pexels-photo-167636.jpeg?auto=compress&cs=tinysrgb&w=1200)

## 📖 Descripción del Proyecto

**Melodify** es una plataforma web interactiva diseñada para recolectar datos sobre hábitos y preferencias musicales de los usuarios, analizar tendencias estadísticas y generar recomendaciones personalizadas de canciones basadas en sus gustos. El sistema utiliza inteligencia artificial simulada para procesar las respuestas y ofrecer sugerencias musicales adaptadas a cada perfil.

Este proyecto fue desarrollado como parte de un análisis académico sobre hábitos de consumo musical, relaciones entre variables demográficas y preferencias musicales, y la efectividad de sistemas de recomendación basados en encuestas.

---

## 🚀 Funcionalidades Principales

### 1. **Página de Inicio (index.html)**
- Hero section con imagen atractiva y llamado a la acción
- Vista previa de las últimas encuestas realizadas con insights generados por IA
- Estadísticas rápidas: género musical predominante, edad promedio, plataforma más usada y motivo principal
- Navegación intuitiva hacia todas las secciones

### 2. **Encuesta de Preferencias Musicales (recomendador.html)**
Formulario completo que recolecta:
- **Consentimiento informado** para uso de datos académicos
- **Datos demográficos:** género (incluyendo opción no binaria), edad, ocupación
- **Preferencias musicales:** género favorito, plataforma de streaming, motivo para escuchar música
- **Evaluación de 30 canciones** en escala del 1 al 5 (1 = No me gusta, 5 = Me encanta, 6 = No conozco la canción)
  - *Rock:* Bohemian Rhapsody, Smells Like Teen Spirit, Hotel California, etc.
  - *Pop:* Blinding Lights, Anti-Hero, As It Was, Flowers, Espresso, etc.
  - *Hip-Hop:* Lose Yourself, HUMBLE., God's Plan, etc.

### 3. **Sistema de Recomendación IA (envio.html)**
Basado en las valoraciones del usuario, el sistema:
- Calcula el género musical con mayor puntaje promedio
- Genera una recomendación personalizada de:
  - **Estilo musical** predominante
  - **Artista sugerido**
  - **Canción específica** (aleatoria dentro del género)
- Muestra análisis estadísticos predefinidos sobre relaciones entre:
  - Edad y género musical favorito
  - Ocupación y preferencias musicales
  - Género de la persona y gustos musicales
- Persiste los resultados en `localStorage` para consultas futuras

### 4. **Historial de Encuestas (encuestas_realizadas.html)**
- Visualización de todas las encuestas realizadas (CSV base + nuevas)
- Filtros dinámicos por:
  - Género musical favorito
  - Edad
  - Ocupación
- Insights generados por IA para cada encuesta
- Diferenciación visual entre encuestas históricas (CSV) y nuevas
- Botón para eliminar solo las encuestas del usuario actual

### 5. **Panel de Estadísticas (estadisticas.html)**
Dashboard completo con:
- **Tarjetas resumen:** total encuestas, género top, edad promedio, plataforma favorita
- **Gráficos interactivos** (Chart.js):
  - Géneros musicales favoritos (gráfico de barras)
  - Motivos para escuchar música (gráfico de pastel)
  - Plataformas más usadas (gráfico de dona)
  - Distribución por ocupación (gráfico de barras)
- Tabla de últimas recomendaciones generadas
- Datos combinados de encuestas históricas + nuevas

---

## 📊 Estructura de Datos

### Variables recolectadas

| Campo | Descripción | Tipo |
|-------|-------------|------|
| `genero` | Identidad de género del encuestado | Categórico |
| `edad` | Edad en años | Numérico |
| `ocupacion` | Ocupación o profesión | Texto |
| `genero_fav` | Género musical favorito | Categórico |
| `plataforma` | Plataforma de streaming musical | Categórico |
| `motivo` | Razón principal para escuchar música | Categórico |
| `cancion_01..30` | Puntuación de 1-5 para cada canción | Numérico (1-6) |

### Géneros musicales evaluados
- 🎸 **Rock** (10 canciones)
- 🎤 **Pop** (18 canciones)
- 🎧 **Hip-Hop** (2 canciones en versión reducida, 12 en catálogo completo)

---

## 🔍 Análisis y Relaciones Estadísticas

El sistema explora las siguientes hipótesis:

### Relación Edad - Género Musical
- Jóvenes (<25) → Pop, Electrónica, Reggaetón
- Adultos jóvenes (25-35) → Rock alternativo, Indie
- Adultos mayores (>35) → Baladas, música romántica
- El gusto musical se diversifica con la edad

### Relación Ocupación - Género Musical
- Estudiantes → Pop, Reggaetón
- Áreas creativas → Alternativo, Indie
- Profesionistas → Gustos más variados
- Trabajadores de tiempo completo → Jazz, música instrumental

### Relación Género - Preferencias Musicales
- Mujeres → ligera preferencia por pop y baladas
- Hombres → mayor frecuencia en rock y electrónica
- Diferencias mínimas en términos generales
- Reguetón es popular en todos los grupos

---

## 🗄️ Persistencia de Datos

El sistema utiliza **localStorage** del navegador para almacenar:
- `todasEncuestas`: Array con todas las encuestas enviadas
- `recomendacionResultado`: Última recomendación generada
- `recomendacionesHistorial`: Historial de recomendaciones (máx. 20)

### Base de datos precargada (CSV)
El proyecto incluye **27 encuestas reales** (archivo `base de datos_ev2.csv`) con datos de usuarios reales, que sirven como:
- Base histórica para estadísticas
- Ejemplos de visualización en el historial
- Datos de entrenamiento para el sistema (conceptualmente)

---

## 🛠️ Tecnologías Utilizadas

| Tecnología | Uso |
|------------|-----|
| **HTML5** | Estructura semántica de las páginas |
| **CSS3** | Estilos, diseño responsive, Flexbox, Grid |
| **JavaScript (ES6+)** | Lógica de aplicación, manipulación del DOM |
| **Chart.js** | Visualización de gráficos estadísticos |
| **Font Awesome 6** | Iconografía vectorial |
| **Google Fonts (Inter)** | Tipografía moderna |
| **localStorage API** | Persistencia de datos del lado del cliente |

---

## 📁 Estructura de Archivos
├── index.html # Página principal
├── recomendador.html # Formulario de encuesta
├── envio.html # Resultados y recomendación
├── encuestas_realizadas.html # Historial con filtros
├── estadisticas.html # Dashboard con gráficos
└── base de datos_ev2.csv # Datos históricos (27 encuestas)


---

## 🚦 Flujo de Uso

1. **Inicio** → Usuario ve estadísticas rápidas y últimas encuestas
2. **Realizar encuesta** → Completa el formulario con sus datos y evalúa 30 canciones
3. **Obtener recomendación** → Sistema analiza respuestas y sugiere canción/artista
4. **Ver historial** → Consulta todas las encuestas realizadas (históricas + nuevas)
5. **Explorar estadísticas** → Visualiza tendencias y gráficos interactivos

---

## 🧠 Lógica de Recomendación (IA simulada)

```javascript
1. Para cada género musical (Rock, Pop, Hip-Hop):
   - Sumar puntajes de canciones de ese género
   - Calcular promedio

2. Identificar género con mayor promedio

3. Seleccionar aleatoriamente una canción del banco correspondiente

4. Generar respuesta personalizada con:
   - Estilo recomendado
   - Artista sugerido
   - Canción específica
   - Insight explicativo

Consultas Estadísticas Disponibles
¿Qué género musical es más popular?
Visualización en gráfico de barras en estadisticas.html

¿Cuál es la edad promedio de los encuestados?
Tarjeta de resumen en todas las páginas

¿Qué plataforma prefieren los usuarios?
Gráfico de dona con distribución porcentual

¿Por qué motivos escuchan música?
Gráfico de pastel con razones principales

¿Cómo se distribuyen las ocupaciones?
Gráfico de barras horizontales

¿Qué relación hay entre variables demográficas y gustos?
Secciones explicativas en envio.html con insights predefinidos

Este proyecto es de uso académico y educativo. Los datos recolectados son anónimos y se utilizan exclusivamente con fines estadísticos y de investigación.




