Service Discovery
	Service discovery is a mechanism to automatically identify and locate the instances in microservice architecture.
	In which we have one eureka server and eureka clients.
	Each eureka clients register themselfe with Eureka server.
	So because of this we dont need to worry about the network addresses in terms of scalability of instances.
	In terms of fault tolerance it will help to direct request to healthy instances.

Steps To create Eureka Server:
Add Dependency :- spring-cloud-starter-netflix-eureka-server
Annotate @EnableEurekaServer along with @SpringBootApplication
Add Properties in Application.proerties.
server.port=8761
# set false because this application is acting as eureka server
# doesnt need to register with itself.
eureka.client.register-with-eureka=false
eureka.client.fetch-registry=false

Check the UI
http://localhost:8761/ 


Service Registory:
It is nothing but the database which holds the network addresses



- selfRegistry: 
Services keep updating the network addresses with the service registry is known as self Registry.
- Thirdparty Registry:
In which microservices does not register with service registry instead service registry used to check with the microservice about their network address.








Steps To create Eureka Clients:

Add Dependency :- spring-cloud-starter-netflix-eureka-client
Add Properties in Application.proerties.
server.port=8081
spring.application.name=crawler
#provide the url of Eureka Server
eureka.client.service-url.default-zone=http://eureka-server-url:8761/eureka
# ServiceDiscovery
