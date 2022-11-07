# Understanding images
## Overview
In this task we will:
- run a simple flask app
- understand Dockerfile
- build an image using dockerfile
- run this image

This task should be done with a teacher, listening to the lecture will help you understand the content.

## Instructions
- Examine `helloworld.py` and `requirements.txt
- Run Anaconda Powershell prompt
- enter current directory. use `cd` to change directories
- create and activate new environment
```
conda create --name dockertest python=3.9.12
conda activate dockertest
```
- install dependencies and run `helloworld.py` with
```
pip install -r requirements.txt
python helloworld.py
```
- Enter http://localhost:5000 and http://localhost:5000/info
- stop `helloword.py` (ctrl+c)
- Examine `Dockerfile`
- build an image
```
docker build -t hello:v1.0 . 
```
- Run the image
```
docker run --rm -it -p 5001:5000 hello:v1.0
```
- Enter http://localhost:5001 and http://localhost:5001/info
- Stop the container (ctrl+c) and clean the environment
```
docker image rm hello:v1.0
conda activate base
conda remove --name dockertest --all
```
