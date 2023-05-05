# GoViolin

GoViolin is a helpful way to practice violin written in Go. Listen to any scale or arpeggio with a few mouse clicks. Play along to improve your intonation.

<img src="https://user-images.githubusercontent.com/56788883/175832396-30f2b8cd-1963-4bcb-9d90-b8ee393b24ef.png" alt="drawing" width="400"/>


## Use GO Locally
Build, run and test Go locally:
- Initialize the module: 
  - `go mod init github.com/Rosalita/GoViolin`
  - `go mod tidy`
  - `go mod vendor`
- Build a runnable binary: `go build -o runnable.o .`
- Run the binary: `./runnable.o`
- Run the tests: `go test ./...`

## Docker
We used multi-stage docker file to build the app and the other stage based on lightweight image to run it
  To build the image use:
  -  docker build -t goviolin:latest .
  -  docker run -p 3000:8080 goviolin:latest

## Jenkins
![image](https://user-images.githubusercontent.com/56788883/175832347-652d700b-16e1-4b43-8fc2-30f39a86a287.png)
The pipeline supports three stages: Run the tests, Build the image and Push the image to Docker Hub.
It also supports sending emails with the pipeline status.


## Kubernetes
Deploy & access a service in kubernetes:
- Start the local cluster: minikube start
- Create the deployment  kubectl apply -f go-deployment.yaml
- Create the service: kubectl apply -f go-service.yaml
- Get the URL: minikube service goviolin-service --url
- Expose the port (optional): minikube tunnel


