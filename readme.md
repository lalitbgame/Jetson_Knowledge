Running LLM model on Jetson Nano Board:

1. Check version of Docker installed
2. Test Docker using docker run hello-world
3. In case of permission denied due to API issues -
    ```js
    $ sudo usermod -aG docker $USER
    $ newgrp docker
    ```
5. Test running hello-world
6. Pull ollama using -
   ```
    $ docker run -d --runtime nvidia -v ollama:/root/.ollama -p 11434:11434 --restart always --name ollama ollama/ollama
   ```
8. check the docker image -
   ```
    $ docker ps
   ```
10. download and run the model -
    ```
    $ docker exec -it ollama ollama run XXX --verbose
    ```
12. For some reason llama3.2 model with 3b parameter does not work. I tried to update the cuda version as well but the issue was not solved.
