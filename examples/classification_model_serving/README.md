# CompVis Platter

This demo application deploys a deep learning image classification model that 
recognizes what object is present in the given image. It demonstrates use-cases of different tools such as `PyTorch`, `FastAPI`, `Gradio` and `Docker`.

<p align="left">
  <a href="#"><img src="./frontend/test1.jpeg" width="200"></a> <br />
  <em> 
    Model Output: `king penguin: 0.9999`.
  </em>
</p>


### Usage

To launch this application, run:

```
# run backend
docker run -p 8000:80 --name cls-serve hasibzunair/classification_model_serving
# run frontend
docker run -p 7860:7860 --add-host host.docker.internal:host-gateway --name frnt-serve hasibzunair/frontend_serving
```

Now, open the app using `http://0.0.0.0:7860` and drop your images to make a prediction, or simply use the examples!

### Note
I did this project after completing (Docker for the Absolute Beginner - Hands On - DevOps)[https://www.udemy.com/course/learn-docker/].