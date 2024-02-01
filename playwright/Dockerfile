FROM mcr.microsoft.com/playwright/dotnet:next-jammy
MAINTAINER totonero
RUN apt-get update -y && \
    apt install openjdk-11-jdk openjdk-11-jre -y
ENV TZ="America/Sao_Paulo"
ENV JAVA_OPTS="-Xms1024m -Xmx2048m -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -Xss384k -XX:ParallelGCThreads=20 -XX:ConcGCThreads=5"
ADD ./build/libs/aviator-manager-0.0.1-SNAPSHOT.jar /usr/src/aviator-manager-0.0.1-SNAPSHOT.jar
WORKDIR usr/src
ENTRYPOINT ["java","-Dserver.port=$PORT","$JAVA_OPTS -XX:+UseContainerSupport","-jar","aviator-manager-0.0.1-SNAPSHOT.jar"]
