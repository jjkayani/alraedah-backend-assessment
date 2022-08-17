# Read Me First
This is a demo service which is built using spring-boot 2xx.
# Getting Started
./gradlew clean build
This service is running on port 8090, you can access the below URL to access swagger and call the api:
* http://localhost:8090/swagger-ui/index.html#/

<img width="1669" alt="Screen Shot 2022-08-17 at 3 34 34 PM" src="https://user-images.githubusercontent.com/25216840/185115119-c42207c5-11ad-4a7e-9af0-346711cecb2e.png">>


# Security

The api is protected by spring-security and needs an addtional header which containt the secret key to access the apis.

* x-application-secret: 92d4f86r-8768a-4b79m-8a7a-c97d33722019

While using swagger the app secret can be passed in authorize section.

# Dockerized Solution

The project also contain a docker file if you want to run the application as container. Please use the below commands.

* docker build  -t demo-service:0.0.1-SNAPSHOT .
* docker run --name demo-service -p 8090:8090 demo-service:0.0.1-SNAPSHOT


curl command for the endpoint:

curl -X POST "http://localhost:8090/perfect-cycle" -H "accept: */*" -H "x-application-secret: 92d4f86r-8768a-4b79m-8a7a-c97d33722019" -H "Content-Type: application/json" -d "{ \"input\": { \"list1\": [1,2,3], \"list2\": [0,2,5], \"list3\": [3,0,1,2] }}"
