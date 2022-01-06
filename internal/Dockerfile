FROM python:3.7-slim

WORKDIR .

COPY ./requirements.txt ./requirements.txt

RUN apt-get update \
    && apt-get install gcc -y \
    && apt-get clean

RUN pip install --upgrade pip \
    && pip install -r ./requirements.txt \
    && rm -rf /root/.cache/pip

COPY . .

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "5000", "--reload"]