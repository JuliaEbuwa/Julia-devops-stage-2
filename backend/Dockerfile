FROM python:3.9-slim
WORKDIR /app
COPY pyproject.toml poetry.lock ./
RUN python -m venv /opt/venv && . /opt/venv/bin/activate && pip install poetry && poetry install
COPY . .
EXPOSE 8000
CMD ["/opt/venv/bin/uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
