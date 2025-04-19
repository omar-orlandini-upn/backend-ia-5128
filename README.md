
# 🍌 Banana Ripeness Predictor - ML Backend (TensorFlow + Node.js)

Este es el servicio backend encargado de realizar las **predicciones de madurez de plátanos** utilizando un modelo de **Machine Learning** entrenado con **TensorFlow**. A través de una API REST, este backend recibe imágenes, las preprocesa y retorna el nivel de madurez del plátano detectado.

Este módulo puede funcionar como un microservicio dentro de un sistema más grande, y está diseñado para integrarse fácilmente con otros servicios como el backend general (Express API) o el frontend en Angular.

---

## 🧠 ¿Qué hace este backend?

- Recibe una imagen de entrada (por ejemplo, `.jpg` o `.png`).
- Preprocesa la imagen (redimensionamiento, normalización).
- Ejecuta una predicción usando un modelo cargado con TensorFlow.
- Retorna la categoría de madurez (por ejemplo: verde, semi-maduro, maduro, pasado).

---

## 🚀 Tecnologías utilizadas

- **Node.js** – Entorno de ejecución para el servidor.
- **TensorFlow.js** – Librería para ejecutar modelos de ML directamente desde Node.
- **Express** – API REST para recibir imágenes y enviar predicciones.
- **Multer** – Middleware para carga de archivos.
- **Jimp** / **Sharp** – Procesamiento de imágenes (redimensionamiento, formato).
- **Dotenv** – Variables de entorno.

---

## 📁 Estructura del proyecto

```
banana-ml-backend/
├── src/
│   ├── model/              # Carga del modelo de TensorFlow
│   ├── utils/              # Funciones auxiliares de preprocesamiento
│   ├── routes/             # Rutas de la API (predicción, salud del sistema)
│   └── app.js              # Configuración y arranque del servidor
├── model/                  # Modelo entrenado (formato .json + .bin)
├── uploads/                # Carpeta para imágenes temporales
├── .env                    # Variables de entorno
├── package.json
└── README.md
```

---

## ⚙️ Instalación

### 1. Clona el repositorio

```bash
git clone https://github.com/tu-usuario/banana-ml-backend.git
cd banana-ml-backend
```

### 2. Instala las dependencias

```bash
npm install
```

### 3. Coloca tu modelo entrenado en la carpeta `model/`

Ejemplo de archivos esperados:

```
model/
├── model.json
├── group1-shard1of1.bin
```

### 4. Crea un archivo `.env`

```env
PORT=4000
MODEL_PATH=./model/model.json
```

### 5. Inicia el servidor

```bash
npm start
```

El servidor quedará disponible en `http://localhost:4000/`.

---

## 📦 Endpoints

- `POST /predict` – Recibe una imagen y responde con la predicción del nivel de madurez.
- `GET /status` – Retorna el estado del servidor.

---

## 📷 Cómo probar

Puedes usar **Postman** o **cURL** para enviar una imagen como `form-data` al endpoint `/predict`. Ejemplo en cURL:

```bash
curl -X POST http://localhost:4000/predict   -F "image=@./ruta/platano.jpg"
```

---

## 📝 Estado del proyecto

- [x] Carga del modelo TensorFlow.js
- [x] Preprocesamiento de imágenes
- [x] API REST con predicción
- [ ] Validación de imágenes
- [ ] Logging y métricas
- [ ] Autenticación (opcional)

---

## 📄 Licencia

Este proyecto se distribuye bajo la licencia [MIT](LICENSE).
