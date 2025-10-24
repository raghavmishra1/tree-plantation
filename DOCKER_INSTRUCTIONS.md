# Docker Deployment Instructions

## Tree Plantation Foundation Website

This is a static HTML website for a tree plantation foundation that can be containerized using Docker and served with Nginx.

## Quick Start

### Using Docker Compose (Recommended)
```bash
# Build and run the container
docker-compose up -d

# Access the website at http://localhost:8080
```

### Using Docker Commands
```bash
# Build the Docker image
docker build -t tree-plantation-web .

# Run the container
docker run -d -p 8080:80 --name tree-plantation-website tree-plantation-web

# Access the website at http://localhost:8080
```

## Project Structure
```
tree-plantation/
├── index.html          # Homepage
├── aboutus.html        # About page
├── contact.html        # Contact page
├── donation.html       # Donation page
├── style.css          # Custom styles
├── Dockerfile         # Docker configuration
├── nginx.conf         # Nginx server configuration
├── docker-compose.yml # Docker Compose configuration
└── .dockerignore      # Docker ignore file
```

## Features
- **Lightweight**: Uses Alpine Linux base image (~5MB)
- **Optimized**: Gzip compression and static asset caching
- **Secure**: Security headers and hidden file protection
- **Fast**: Nginx web server for optimal performance

## Management Commands

### Stop the container
```bash
docker-compose down
# or
docker stop tree-plantation-website
```

### View logs
```bash
docker-compose logs
# or
docker logs tree-plantation-website
```

### Rebuild after changes
```bash
docker-compose up --build -d
```

## Production Deployment
For production, consider:
1. Using a reverse proxy (like Traefik or nginx-proxy)
2. Adding SSL/TLS certificates
3. Setting up proper domain configuration
4. Implementing monitoring and logging
