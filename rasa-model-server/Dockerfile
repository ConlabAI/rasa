FROM python:3.10-slim

ENV MODELS_DIR models
ENV PORT 8080
ENV MAX_REQUEST_SIZE_MB 64
ENV API_KEY ""
ENV DEBUG 0

WORKDIR /app
COPY ./requirements.txt .

RUN pip install --upgrade pip && pip install -r requirements.txt

RUN useradd 1000 || mkdir models || chown -R 1000 models
USER 1000

COPY . .

CMD [ "python", "-u", "app.py" ]