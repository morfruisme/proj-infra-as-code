FROM python:3.11-slim

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY --parents app.py static templates .
CMD ["python3", "app.py"]
