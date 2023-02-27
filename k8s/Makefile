install:
	helm upgrade --install counter counter

frontend:
	kubectl port-forward svc/frontend-service 8081:80

.PHONY: counter
counter:
	kubectl port-forward svc/counter 8080:8080
