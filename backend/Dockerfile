FROM python:3.9-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    libffi-dev \
    libssl-dev \
    libblas-dev \
    liblapack-dev \
    && apt-get clean

# Set the working directory to /backend
WORKDIR /backend

# Copy application code and model files into the container
COPY server.py .
COPY rgb_model.pkl .
COPY word2vec_genres.model .
COPY label_encoders.pkl .
COPY requirements.txt .

RUN pip3 install --no-cache-dir -r requirements.txt

EXPOSE 5000

CMD ["python", "server.py"]
