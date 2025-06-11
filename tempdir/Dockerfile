FROM python:3.10-slim

# Variables d’environnement pour éviter les erreurs de thread
ENV PIP_NO_PROGRESS_BAR=off
ENV PIP_DISABLE_PIP_VERSION_CHECK=1
ENV PIP_PROGRESS_BAR=off

COPY requirements.txt /tmp/requirements.txt

# Installation des dépendances sans barres de progression ni vérif de version
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY ./static /home/myapp/static/
COPY ./templates /home/myapp/templates/
COPY sample_app.py /home/myapp/
WORKDIR /home/myapp

EXPOSE 5050

CMD ["python3", "sample_app.py"]

