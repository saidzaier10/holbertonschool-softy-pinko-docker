# Use the latest Nginx image as the base
FROM nginx:latest

# Copy the front-end files to the appropriate directory in Nginx
COPY softy-pinko-front-end /var/www/html/softy-pinko-front-end

# Copy the custom Nginx configuration file
COPY softy-pinko-front-end.conf /etc/nginx/conf.d/default.conf

# Expose port 9000 for the web server
EXPOSE 9000
