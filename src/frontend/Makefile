build:
	docker build -t frontend .

network:
	docker network create istio

run:
	docker rm frontend || true
	docker run -p 8081:80 -it --net istio --name=frontend frontend

tag:
	docker tag frontend:latest moonblade/frontend:latest

push: tag
	docker push moonblade/frontend:latest
