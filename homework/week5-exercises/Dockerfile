FROM svizor/zoomcamp-model:3.9.12-slim

RUN pip install pipenv

COPY ["Pipfile", "Pipfile.lock", "./"]

RUN pipenv install --system --deploy

COPY ["q6-docker_predict.py", "./"]
COPY ["*.bin", "./"]

EXPOSE 9696

ENTRYPOINT ["gunicorn", "--bind=0.0.0.0", "q6-docker_predict:app"]