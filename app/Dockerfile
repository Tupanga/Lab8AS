# Imagen base
FROM python:alpine

# Establece el directorio de trabajo
WORKDIR /code

# Variables de entorno
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0

# Instalación de dependencias del sistema (necesarias para compilar ciertas librerías de Python en Alpine)
RUN apk add --no-cache gcc musl-dev linux-headers

# Copia primero los requirements para aprovechar la caché de Docker
COPY requirements.txt requirements.txt

# Instala las dependencias de Python
RUN pip install -r requirements.txt

# Copia el código de la aplicación
COPY app.py .

# Comando de arranque
CMD ["flask", "run"]
