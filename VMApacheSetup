#!/bin/bash

# Update package lists
echo "Updating package lists..."
sudo apt update -y

# Install Apache
echo "Installing Apache..."
sudo apt install apache2 -y

# Enable Apache to start on boot
echo "Enabling Apache to start on boot..."
sudo systemctl enable apache2

# Start Apache
echo "Starting Apache..."
sudo systemctl start apache2

# Create a basic HTML file
echo "Creating a basic HTML file..."
sudo mkdir -p /var/www/html
echo "<!DOCTYPE html>
<html>
<head>
    <title>Welcome to Your Apache Web Server!</title>
</head>
<body>
    <h1>Hello from Azure!</h1>
    <p>Your Apache web server is up and running!</p>
</body>
</html>" | sudo tee /var/www/html/index.html

# Set permissions for /var/www/html
echo "Setting permissions for /var/www/html..."
sudo chmod -R 755 /var/www/html

# Allow HTTP traffic through the firewall
echo "Allowing HTTP traffic through the firewall..."
sudo ufw allow 'Apache'

# Reload firewall settings
echo "Reloading firewall settings..."
sudo ufw reload

# Restart Apache to apply changes
echo "Restarting Apache..."
sudo systemctl restart apache2

echo "Apache installation and configuration complete!"
