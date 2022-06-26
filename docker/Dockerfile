FROM python:3.7

WORKDIR /opt/app

RUN python3 -m venv venv
RUN . venv/bin/activate

# optimize image caching
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
RUN apt-get update && apt-get install -y netcat
#RUN yum install -y nc
COPY . .

EXPOSE 8081

CMD ["python3", "-m", "flask", "run", "--host=0.0.0.0"]