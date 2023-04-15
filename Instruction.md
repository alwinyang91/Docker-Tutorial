# Docker



## 1. Install Docker

Check:

```shell
docker
docker -v
```



## 2. Create workspace `folder/app.py, requirements.txt`

```
mkdir Hello World
touch app.py
touch requirements.txt
```



## 3. Create a Dockerfile

```dockerfile
FROM python:3.7
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
CMD ["python","app.py"]
```



## 4. Build an image

```shell
cd Hello World
docker build -t welcome-flaskapp:1.0 .
```

- Check images

```shell
docker images
```

- Delete an image

```shell
docker image rm -f welcome-flaskapp:1.0
```



## 5. Run a Container

```shell
docker run -p 5050:5000 welcome-flaskapp
```



## 6. Deploy in DockerHub

```shell
docker build -t alwinyang/welcome-flaskapp:0.1 .
docker push alwinyang/welcome-flaskapp:0.1
```

- Change images name

```shell
docker tag alwinyang/welcome-flaskapp:0.1 alwinyang/welcome-flaskapp1:0.1
```



## 7. Download images

```shell
docker pull alwinyang/welcome-flaskapp:0.1
```

