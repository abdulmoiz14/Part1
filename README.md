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
  **Add this code into the application.py**
  ```
  if __name__ == "__main__":
    app.run(host='0.0.0.0', port=8080)
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
## Step 4
**build the dockerfile.**
```
docker build -t finance_app -f dockerfile .
```
This will build the docker image. <br />
**Varify that the image is build successfully by using following command**
```
docker ps -a
```
![Screenshot (23)](https://user-images.githubusercontent.com/65711565/227139352-190f31d3-f801-4083-a9dc-a4010259ba52.png)
**run docker image**
```
docker run -it -e API_KEY=123 finance_flask
```
![Screenshot (24)](https://user-images.githubusercontent.com/65711565/227139615-657a66f4-dd8c-4500-93b0-416abbcfd32f.png)

## Step 5
**first login to docker**
```
docker login
```
**Push the docker image to docker hub.**
```
docker tag imageName:tag username/imageName:tag
docker push username/imageName:tag
```
**This is the link of my repository in dockerhub** <br />
https://hub.docker.com/repository/docker/abdulmoiz1443/finance_flask/general
## step 6
**Create the github repository by using following command**
First create the repository in github.com
```
git init
git add --all
git commit -m "adding codeSpace"
git branch -M main
git remote add origin https://github.com/abdulmoiz14/Part1-.git
git push -u origin main
```
## Step 7
**Create Readme.txt and push to github.**
```
touch readme.txt
```
Style and describe your project in Readme file
now push to the github
```
git add readme.txt
git commit -m "Adding readme.txt file"
git push -u origin main
```
## Step 8 
**Push your Codebase to Github.**
```
push add 
push commit -m "adding Codebase to github"
git push -u origin main
```
