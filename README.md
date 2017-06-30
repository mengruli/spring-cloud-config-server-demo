# spring-cloud-config-server-demo

## This project demoenstrates the concept of centralized configuration for microservices

### this project serves as the configuration server
### the physical configuration files for clients are hosted on git. Check the .yaml file for details.

For example, when a client named first-client starts up, the client checks its bootstrap.yml file to know how it should get additional configuration info. The yaml file tells the client to go to http://localhost:8001 to get it.

Then the client makes a call to the config server. The follows the following rule:

http://\<server-name>:\<port>/\<client-app-name>/\<profile>

When the config server receives the request, it actually goes to git to load the config files and return it/them to the client.

On git the naming convention of the config files is:

\<client-app-name>-\<profile>.yml

## Note that Spring Cloud prefers yml against properties.

## If you download this project, whithout running any client app, you can test the config by requesting:
## http://localhost:8001/first-client/abc
