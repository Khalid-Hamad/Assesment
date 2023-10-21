#Foodics Assesment 

We’d like to invite you to do the # DevOps technical assignment
This repo contains the assignment and should contain all the information you need


**Goals**

The applicant should be able to:

1. deploy isolated web applications
2. write infrastructure as code
3. explain design decisions and chosen technologies
4. handover the project to new colleagues

**Background**
Provided are two different web API's for a fictional airport application, only GET requests are supported:

1. country-service:
```
            A service which returns basic information about countries
            Endpoint: /countries to get a full list of countries
            Endpoint: /countries/<query> to search for country by name / ISO code.
```

3. airport-service
```

      A service which returns information about airports with country codes
          Endpoint: /airports to get a full list of airports and their runways
          Endpoint: /airports/<query> to get a list of airports based on country code (e.g.: "NL")
```

Version Update:
```

          version 1.1.0: a service which returns information about airports with country codes
          Endpoint: /airports?full=[0|1] returns a summary or all details of all airports, depending on the value of full.
          Endpoint: /airports/<id> returns the full information of an airport based on its identifier. E.g.: /airports/EHAM returns all information for Schiphol.
          Endpoint: /search/<qry> returns a list of airports based on a country code search.
```

In addition to their application-specific endpoints all versions of both services expose the following two endpoints:

```

/health/live returns 200 when the HTTP server is up.
/health/ready returns 200 when the service is done initializing and ready to serve requests, 503 when the service is still initializing.
```

The above-mentioned services should run in isolated environments and both endpoints are combined and exposed using a reverse-proxy and/or load-balancer.


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

