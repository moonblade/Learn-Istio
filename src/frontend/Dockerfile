# Start from a minimal Nginx base image
FROM nginx:latest

# Copy the HTML page into the container
COPY index.html /usr/share/nginx/html/

# Expose the port Nginx listens on
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
