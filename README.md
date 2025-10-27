# Docker Practice: Flask → Docker → EC2 (Terraform)

- App in `app/`
- Infra in `infra/`
- Build locally, push to Docker Hub, deploy via Terraform.

## Local
cd app
docker build -t hello-docker:v1 .
docker run -d -p 8080:5000 --name web hello-docker:v1

## Publish
docker tag hello-docker:v1 tawanperry/hello-docker:v1
docker push tawanperry/hello-docker:v1

## Deploy
cd infra
terraform init
terraform apply -auto-approve
