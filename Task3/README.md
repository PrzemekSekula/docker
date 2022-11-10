# Understanding images
## Overview
In this task we will:
- build and run our own image (manually),
- create all the necessary scripts and build it automatically

This task should be done with a teacher, listening to the lecture will help you understand the content. In case  you stuck, the solution is available in the solved/ folder.

## Instructions

- Run Anaconda Powershell prompt
- Examine `app/myapp.py` and `Dockerfile`
- Build an image
```
docker build -t task3_app:v1.0 . 
```
- Run the container wtih /bin/bash command
```
docker run --rm -it -p 5000:5000 task3_app:v1.0 /bin/bash
```

- Try to run flask (should be command not found)
```
$flask run
```
- Install Flask and run it (still there is something wrong)
```
pip install Flask
flask run
```
- Set up all the necessary environmental variables and run it again
```
export FLASK_APP="myapp"
export FLASK_DEBUG=1
export FLASK_RUN_HOST="0.0.0.0"
flask run
```
- Check if it works with http://localhost:5000 and http://localhost:5000/?name=<ENTER_YOUR_NAME_HERE>

- in `Task3` folder create `requirements.txt` file that points out Flask package:
```
Flask
```
- in `Task3/app` folder create `start.sh` file that executes all the bash commands
```
cd /app
export FLASK_APP="myapp"
export FLASK_DEBUG=1
export FLASK_RUN_HOST="0.0.0.0"
flask run
```
- add requirements installation to Dockerfile:
```
COPY requirements.txt .
RUN pip install -r requirements.txt
```
- Change the copy line to copy the entire content of `./app`
```
COPY app/* .
```
- Add command that runs start.sh
CMD ["/bin/bash", "start.sh"]
- build your image and run your container. Check how it works.
```
docker build -t task3_app:v1.0 . 
docker run --rm -it -p 5000:5000 task3_app:v1.0
```
- remove your image
```
docker image rm task3_app:v1.0 
```

