Build image
1. docker build -t flask_docker .
2. docker scan flask_docker

Run container
1. docker run -dp 80:80 flask_docker
2. See app in http://0.0.0.0:80/

Push to hub
1. docker tag flask_docker <your-docker-hub-username>/flask-docker
2. docker push hasibzunair/flask-docker

Run from hub
1. docker run -p 80:80 hasibzunair/flask-docker


Remove image
1. docker image rm IMAGEID
2. docker images

Stop container
1. docker ps -a
2. docker rm containerID