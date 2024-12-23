# Week 1 — App Containerization

## Containerize the Backend

### Add a Dockerfile

Create a file here: backend-flask/Dockerfile

```
FROM python:3.10-slim-bullseye

WORKDIR /backend- flask

COPY requirements.txt requirements.txt

RUN pip install -r requirements.txt

COPY . .

ENV FLASK_ENV=development
ENV FLASK_APP=app.py

EXPOSE ${PORT}

CMD ["python", "-m", "flask", "run", "--host=0.0.0.0", "--port=4567"]
```

### Build the docker image

``` docker build -t backend-flask ./backend-flask ```

### Run the container from the image

``` docker run -p 4567:4567 -e FRONTEND_URL='*' -e BACKEND_URL='*' -it backend-flask ```

### Check the following end point

```api/activities/home```