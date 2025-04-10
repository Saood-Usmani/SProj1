To deploy/serve my model, simply pull my docker image from docker hub with docker pull usmanis0115754/ml-structures-api:latest. Then, run docker compose up -d to start the container. Now, once the container is started, you can easily run the ./start_grader.py file or can use curl to test the server. Here are some examples of using curl for both the get and post commands (note, you will probably have to change the image path for the curl command)
curl -X POST http://127.0.0.1:5000/inference -F "image=@data/damage/-93.66109_30.212114.jpeg"
  {
    "prediction": "damage"
  }
curl localhost:5000/summary
  {
    "description": "Classify images based on if they contain damage or no damage",
    "max_number_of_parameters": 14714688,
    "name": "damage or no damage",
    "version": "v1"
  }
To stop the container, simply use the command docker compose down, and the   container will stop.
