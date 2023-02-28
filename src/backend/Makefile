build:
	docker build -t counter .

network:
	docker network create istio

run:
	docker rm counter || true
	docker run -p 8080:8080 -it --net istio --name=counter counter

tag: build
	docker tag counter:latest moonblade/counter:latest

push: tag
	docker push moonblade/counter:latest
