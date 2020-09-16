# Running the container
`docker run -it centos-jre-en_us-utf8:1.0`

This will throw you to its bash shell 

# OpenJDK Java 8 JRE is installed:
Once inside the container, you will be able to see the java version installed by running the following command:

```
[root@container /]# java -version
openjdk version "1.8.0_151" OpenJDK Runtime Environment (build 1.8.0_151-b12) OpenJDK 64-Bit Server VM (build 25.151-b12, mixed mode)
```

# en_US.UTF-8 Locale is set
To check the locale that has been set: 

```
[root@container /]# locale
LANG=en_US.UTF-8 
LC_CTYPE="en_US.UTF-8" 
LC_NUMERIC="en_US.UTF-8" 
LC_TIME="en_US.UTF-8" 
LC_COLLATE="en_US.UTF-8" 
LC_MONETARY="en_US.UTF-8" 
LC_MESSAGES="en_US.UTF-8" 
LC_PAPER="en_US.UTF-8" 
LC_NAME="en_US.UTF-8" 
LC_ADDRESS="en_US.UTF-8" 
LC_TELEPHONE="en_US.UTF-8" 
LC_MEASUREMENT="en_US.UTF-8" 
LC_IDENTIFICATION="en_US.UTF-8" 
LC_ALL=en_US.UTF-8
```

# Dockerfile:
```
FROM centos:7 
MAINTAINER luppeng "https://sg.linkedin.com/in/lup-peng-loke" 

ENV LANG=en_US.UTF-8 
LANGUAGE=en_US:en 
LC_ALL=en_US.UTF-8 
RUN yum update && yum install -y java-1.8.0-openjdk && yum clean all 

ENTRYPOINT ["/bin/bash"]
```
