# SaludMX AI - Predictor Epidemiológico Familiar 🇲🇽🧠

**SaludMX AI** es una aplicación de grado profesional que utiliza **Machine Learning (TensorFlow.js)** para predecir el riesgo de enfermedades crónico-degenerativas (enfocada en Diabetes) dentro del entorno familiar. La app permite entrenar una red neuronal personalizada utilizando microdatos reales de salud pública de México.

---

## ✨ Características Principales

- **Entrenamiento con Datos Reales**: Procesa archivos CSV con el estándar de la Secretaría de Salud (SSA) de México.
- **Privacidad Local**: Los datos y el entrenamiento nunca salen del navegador del usuario (Edge Computing).
- **Análisis de 10 Variables**: Evalúa Sexo, Edad, Obesidad, Hipertensión, Problemas Cardiovasculares, Insuficiencia Renal, Tabaquismo, EPOC, Asma e Inmunosupresión.
- **Persistencia de Pesos (I/O)**: Permite descargar la IA entrenada como archivos físicos (`.json` + `.bin`) y cargarlos automáticamente al iniciar la app.
- **Dashboard Comparativo**: Visualización dinámica con **Chart.js** para analizar hasta 15 integrantes de la familia simultáneamente.

---

## 🛠️ Stack Tecnológico

- **IA**: [TensorFlow.js](https://www.tensorflow.org/js) (Redes Neuronales Densas).
- **Visualización**: [Chart.js](https://www.chartjs.org/) (Gráficos de barras interactivos).
- **Parser**: [PapaParse](https://www.papaparse.com/) (Procesamiento de CSV de alto rendimiento).
- **Frontend**: HTML5, CSS3 (Grid & Flexbox), Vanilla JavaScript.

---

## 📊 Especificación del Dataset (CSV)

Para que el modelo funcione correctamente, el archivo cargado debe contener las siguientes columnas (basadas en el estándar oficial de México):

| Columna | Descripción | Formato de Datos |
| :--- | :--- | :--- |
| **SEXO** | Género biológico | 1: Mujer, 2: Hombre |
| **EDAD** | Años cumplidos | Numérico (0-100) |
| **OBESIDAD** | Diagnóstico previo | 1: Sí, 2: No |
| **HIPERTENSION** | Presión arterial alta | 1: Sí, 2: No |
| **CARDIOVASCULAR**| Problemas cardiacos | 1: Sí, 2: No |
| **RENAL_CRONICA** | Problemas de riñón | 1: Sí, 2: No |
| **TABAQUISMO** | Consumo de tabaco | 1: Sí, 2: No |
| **EPOC** | Enf. Pulmonar Obstructiva | 1: Sí, 2: No |
| **ASMA** | Diagnóstico de asma | 1: Sí, 2: No |
| **INMUSUPR** | Inmunosupresión | 1: Sí, 2: No |
| **DIABETES** | **Variable a predecir** | 1: Sí, 2: No |

---

## 🚀 Instalación y Uso

### 1. Despliegue en Servidor
Dado que la app utiliza `fetch` para cargar los pesos de la IA automáticamente, se requiere un servidor web para evitar errores de CORS.

- **Opción A (GitHub Pages):** Sube el archivo `index.html`, `model.json` y `model.weights.bin` a tu repositorio y activa Pages.
- **Opción B (Local):** Usa la extensión **Live Server** en VS Code o ejecuta:
  ```bash
  # Usando Python
  python -m http.server 8000
