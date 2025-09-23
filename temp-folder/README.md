# Dockerized Website Project

## Project Overview
This project demonstrates how to containerize a static website using Docker.
The website template was taken from **Tooplate (free website templates) and packaged into a Docker image using Ubuntu as the base image.

## Technologies Used
- Ubuntu
- Docker

## Steps to Run
1. **Clone the repository**
   ```bash
      git clone https://github.com/Shikha-1811/Devops-Miniproject1
      cd Devops_Miniproject1/
2. Build the docker image
   ```bash
      docker build -t miniproject1:latest .
3. Run the Container
   ```bash
      docker run -d -p 9080:80 miniproject1:latest
4. Access the website
   Open your browser and go to:
      http://localhost:9080      
