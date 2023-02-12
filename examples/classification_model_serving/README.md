# Serving image classification models

Serves a dockerized deep learning image classification model using FastAPI.

<p align="center">
  <a href="#"><img src="./test1.jpeg" width="100"></a> <br />
  <em> 
    Prediction from model: `king penguin: 0.9999`.
    </em>
</p>

### Local development
To use this code for local development, first clone the repo. Then navigate to the project folder `classification_model_serving` and install the requirements using (make sure Python version is 3.6):
```bash
pip install -r requirements.txt
```
Now, you're setup!

### Usage

To launch the FastAPI application, run:
```python
python server.py
```

A FastAPI application will run on your local machine. See Swagger UI at `http://127.0.0.1:8000/docs` for more info.
To interact with it, open a new terminal and just send a curl request like this:
```bash
$ curl -X POST -F image=@test1.jpeg "http://127.0.0.1:8000/api/predict"
```

Using the `test1.jpeg` image, the JSON response result should look like this, with labels and the probability values for the given image:
```json
{
  "success": true, 
  "predictions": 
  [
    {
      "label": "king penguin", 
      "probability": 0.999931812286377
    }, 
    {
      "label": "guenon", 
      "probability": 9.768833479029126e-06
    }, 
    {
      "label": "megalith", 
      "probability": 8.01052556198556e-06
    }, 
    {
      "label": "cliff", 
      "probability": 7.119778274500277e-06
    }, 
    {
      "label": "toucan", 
      "probability": 6.5011186052288394e-06
    }
  ]
}
```

Or, submit a request using Python like this:
```python
python request.py
```
The result should look like this:
```bash
1. king penguin: 0.9999
2. guenon: 0.0000
3. megalith: 0.0000
4. cliff: 0.0000
5. toucan: 0.0000
```

To try it with any of your own images(`*.jpg`,`*.jpeg`,`*.png`), set path to your image `YOUR_IMG_PATH` and run:
```bash
$ curl -X POST -F image=@YOUR_IMG_PATH "http://127.0.0.1:8000/api/predict"
```

### Dockerized FastAPI application

To build and run the FastAPI application as a docker container, run:
```
# build
docker build -t classification_model_serving .
# run
docker run --publish 80:80 --name cls-serve classification_model_serving
```

Finally, run `curl -X POST -F image=@test1.jpeg "http://0.0.0.0:80/api/predict"` in your terminal. You should get the same JSON response as above.

### Todo
* docker image to registry, pull and test
* run gradio frontend as docker container, link with fastapi container
* link with another container

### License
MIT