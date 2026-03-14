SaludMX AI - Predictor Epidemiológico Familiar 🇲🇽🧠
SaludMX AI es una aplicación web de vanguardia que utiliza Machine Learning (TensorFlow.js) para predecir riesgos de enfermedades crónico-degenerativas (específicamente Diabetes) basándose en indicadores de salud pública de México.
La herramienta permite a un usuario cargar sus propios datasets, entrenar una red neuronal en tiempo real dentro del navegador y analizar el riesgo de hasta 15 integrantes de su familia.
✨ Características Principales
Privacidad Total: Todo el procesamiento de datos y el entrenamiento de la IA ocurre de forma local en el navegador. Ningún dato de salud sale de tu computadora.
Entrenamiento Personalizado: Permite cargar archivos CSV con el estándar de la Secretaría de Salud de México (SSA).
Persistencia de Pesos (IO de Disco): Capacidad de descargar el "cerebro" (pesos de la red neuronal) como archivos .json y .bin para su posterior carga instantánea sin necesidad de re-entrenar.
Detección Automática: Al alojarse en un servidor web, la app detecta automáticamente si existe un modelo entrenado en la carpeta raíz.
Visualización de Datos: Dashboards interactivos desarrollados con Chart.js para comparar riesgos entre familiares.
🛠️ Stack Tecnológico
Frontend: HTML5 Semántico, CSS3 (Custom Properties & Grid Layout).
Inteligencia Artificial: TensorFlow.js.
Procesamiento de Datos: PapaParse (Parsing de CSV de alto rendimiento).
Gráficos: Chart.js.
📊 Especificación del Dataset
Para que la IA aprenda correctamente, el archivo CSV debe seguir la estructura de los microdatos de la Secretaría de Salud de México:
Columna	Descripción	Valores
SEXO	Género biológico	1: Mujer, 2: Hombre
EDAD	Años cumplidos	Numérico (0-100)
OBESIDAD	Diagnóstico de obesidad	1: Sí, 2: No
HIPERTENSION	Diagnóstico de presión alta	1: Sí, 2: No
CARDIOVASCULAR	Problemas del corazón	1: Sí, 2: No
RENAL_CRONICA	Insuficiencia renal	1: Sí, 2: No
TABAQUISMO	Hábito de fumar	1: Sí, 2: No
EPOC	Enfermedad pulmonar	1: Sí, 2: No
ASMA	Diagnóstico de asma	1: Sí, 2: No
INMUSUPR	Inmunosupresión	1: Sí, 2: No
DIABETES	Variable Objetivo (Label)	1: Sí, 2: No
🚀 Instalación y Uso
Clonar el repositorio:
code
Bash
git clone https://github.com/tu-usuario/saludmx-ai.git
Ejecución Local:
Debido a las políticas de seguridad de los navegadores (CORS), para usar la función de Carga Automática, el proyecto debe ejecutarse en un servidor local.
Si usas VS Code, utiliza la extensión Live Server.
O usa Python: python -m http.server 8000.
Entrenamiento:
Sube tu archivo diabetes_prediction_sample.csv.
Haz clic en Entrenar.
Una vez finalizado, descarga los pesos (model.json y model.weights.bin) y colócalos en la carpeta raíz para que la carga sea automática en el futuro.
🧠 Arquitectura de la IA
El modelo consiste en una Red Neuronal Densa (Multicapa):
Capa de Entrada: 10 neuronas (una por cada indicador de salud).
Capas Ocultas: Arquitectura 16-8 con activación ReLU.
Capa de Salida: 1 neurona con activación Sigmoid para obtener una probabilidad de riesgo entre 0% y 100%.
Optimizador: Adam con una tasa de aprendizaje de 0.01.
⚠️ Descargo de Responsabilidad (Disclaimer)
Esta aplicación es una herramienta educativa y de análisis estadístico. Los resultados proporcionados por la IA son probabilidades basadas en patrones de datos y no constituyen un diagnóstico médico profesional. Siempre consulte a un médico certificado para cualquier evaluación de salud.
