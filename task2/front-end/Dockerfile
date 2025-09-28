FROM nginx:latest

# Copy the front-end files to the nginx html directory
COPY ./softy-pinko-front-end /var/www/html/softy-pinko-front-end

# Copy the nginx configuration file
COPY ./softy-pinko-front-end.conf /etc/nginx/conf.d/default.conf

# Expose port 9000
EXPOSE 9000