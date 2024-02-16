FROM python:3.10

WORKDIR /app_document

COPY ./requirements.txt /app_document/
RUN pip install --no-cache-dir --upgrade -r /app_document/requirements.txt

COPY ./app /app_document/app
COPY .env /app_document

COPY ./migration /app_document/migration
COPY ./alembic.ini /app_document/alembic.ini

EXPOSE  8080

CMD ["/bin/sh", "-c", "alembic upgrade head && uvicorn app.main:app --host  0.0.0.0 --port  8080"]