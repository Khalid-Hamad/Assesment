**How to solve it:**


* create applecations Dockers files 
- Dockerfile-aiport
- Dockerfile-country 

* Set Up Nginx for Reverse Proxy (nginx.conf)

* create Dockerfile-nginx

* commanding to building 
- docker build -t countries-assembly:1.0.1 -f Dockerfile-country .
- docker build -t airport-assembly:1.0.1 -f Dockerfile-airport .
- docker build -t custom-nginx:latest -f Dockerfile-nginx .

* create docker compose (docker-compose.yml)

* run sultion cmd
- docker-compose up -d 

* To change the airport application version follow: 
- change Dockerfile-airport version and docker-compose.yml
- cmd : docker build -t airport-assembly:[version] -f Dockerfile-airport .
- cmd : docker-compose down 
- cmd : docker-compose up -d 

