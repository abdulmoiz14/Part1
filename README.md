# Assignment 1

# Part 1: Dockerfile Creation, GitHub and DockerHub Integration

## Step 1
  I'm using Finance web app in flask python.
  **use following commands to download flask web app:**
  **first create directory for project.**
  ```
  mkdir project
  cd project
  ```
  **clone the project from github.**
  ```
  git clone https://github.com/abdulmoiz14/CS50x
  ```
  **change the branch to the finance.**
  ```
  git checkout cs50/problems/2020/x/tracks/web/finance
  ```
  
## Step 2
### dependencies: 
```
* cs50
* Flask
* Flask-Session
* requests
```
## Step 3
**Create Dockerfile by using following command.**
```
touch dockerfile
```
**open dockerfile in editor mode.**
```
nano dockerfile
```
**write and save following text in dockerfile.**
```
FROM python:3.6
LABEL maintainer = "abdulmoiz1443@gmail.com"
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
EXPOSE 8080
entrypoint ["python"]
CMD ["application.py"]
```
**build the dockerfile.**
```
docker build -t finance_app -f dockerfile .
```
This will build the docker image.
