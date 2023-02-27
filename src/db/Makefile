build:
	docker build -t db .

network:
	docker network create istio

run:
	docker rm db || true
	docker run -p 27017:27017 -it --net istio --name=db db

tag:
	docker tag db:latest moonblade/db:latest

push: tag
	docker push moonblade/db:latest
