# Frontend: show predictions from model in a simple UI

To see prediction in a simple frontend UI, run: 

```
# deploy backend FastAPI application
docker run --publish 80:80 --name cls-serve hasibzunair/classification_model_serving
# run frontend
python main.py
```

Drop your own images or simply use the examples.

### Dockerizing the UI
To build and run the gradio app as a docker container, run:
```
# build
docker build -t frontend_serving:latest .
# run
docker run -p 7860:7860 frontend_serving:latest
```

### Todo 
* Link with REST API app
* https://stackoverflow.com/questions/72943637/dockerizing-a-fastapi-backend-with-react-frontend-tips 
* https://blog.devgenius.io/api-calls-between-docker-instances-24124f5bf010 
* 