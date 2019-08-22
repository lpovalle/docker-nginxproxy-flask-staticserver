FROM python:3.4-alpine

ADD . /code

WORKDIR /code

RUN apk update \
&& pip install flask \
&& pip install flask_restful \
&& pip install redis

CMD ["python", "app.py"]