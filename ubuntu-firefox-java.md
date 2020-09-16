# Description
Ubuntu 16.04 Base OS, with Firefox and openjdk-8-jdk installed 

# Use Case 
Running FitNesse (for Appian) with Headless Firefox

# Dockerfile
```
FROM ubuntu:16.04 
RUN apt-get update && apt-get -y install firefox openjdk-8-jdk && apt-get clean 

ENTRYPOINT ["/bin/sh"]
```
