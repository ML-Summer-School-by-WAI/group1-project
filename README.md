# group1-project
ML Project from Group 1

### Push docker image to Amazon ECR
```bash 
aws ecr get-login-password --region ap-southeast-1 | docker login --username AWS --password-stdin 043841769286.dkr.ecr.ap-southeast-1.amazonaws.com

docker build -t first-ml-app-container .
docker buildx build --platform linux/amd64 -t first-ml-app-container:latest .

docker tag first-ml-app-container:latest 043841769286.dkr.ecr.ap-southeast-1.amazonaws.com/first-ml-app-container:latest

docker push 043841769286.dkr.ecr.ap-southeast-1.amazonaws.com/first-ml-app-container:latest
```