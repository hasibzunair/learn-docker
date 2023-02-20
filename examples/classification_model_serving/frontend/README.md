# Gradio Frontend
Drop in your images to see model predictions in a gradio frontend app.

### Local development
To use this code for local development, install the requirements using (make sure Python version is 3.6):
```bash
pip install -r requirements.txt
```
Now, you're setup!

### Usage
To see prediction in a simple frontend UI, run: 
```
# run backend
docker run -p 8000:80 --name cls-serve hasibzunair/classification_model_serving
# run frontend locally
python main.py
```
Drop your own images or simply use the examples.

### Dockerized frontend UI
To build and run the Gradio app as a docker container, run:
```
# build
docker build -t frontend_serving .
# run container
docker run -p 7860:7860 --add-host host.docker.internal:host-gateway --name frnt-serve frontend_serving
```

#### Test image from Docker Hub
```
# tag
docker tag frontend_serving hasibzunair/frontend_serving
# push
docker push hasibzunair/frontend_serving
# test image from hub
docker run -p 7860:7860 --add-host host.docker.internal:host-gateway --name frnt-serve hasibzunair/frontend_serving
```