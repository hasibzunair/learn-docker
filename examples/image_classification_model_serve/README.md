# CompVis Platter

This demo application deploys a deep learning image classification model that 
recognizes what object is present in the given input image and shows results in a simple UI. It demonstrates use-cases of different tools such as `PyTorch`, `FastAPI`, `Gradio` and `Docker`.

<p align="left">
  <a href="#"><img src="./frontend/test1.jpeg" width="200"></a> <br />
  <em> 
    Model Output: `king penguin: 0.99`.
  </em>
</p>


### Usage
To launch the app, run:
```
# run backend
docker run -p 8000:80 --name cls-serve hasibzunair/classification_model_serving
# run frontend
docker run -p 7860:7860 --add-host host.docker.internal:host-gateway --name frnt-serve hasibzunair/frontend_serving
```
Now, the app is live in `http://0.0.0.0:7860`. Drop your images to make a prediction, or simply use the examples! For details on how the `frontend` and `backend` components were built, see respective folders. 

### Note
I did this small project after completing [Docker for the Absolute Beginner - Hands On - DevOps](https://www.udemy.com/course/learn-docker/).

#### Todos
* Google cloud run for backend
* Docker compose
* Kubernetes (make some pods lol!)