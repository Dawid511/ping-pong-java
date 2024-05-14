FROM bitnami/java:latest

# Aktualizacja istniejących pakietów
RUN apt-get update -y && \
    apt-get upgrade -y

# Instalacja git, JDK i Gradle
RUN apt-get install git -y && \
    apt-get install default-jdk -y && \
    apt-get install gradle -y

# Pobranie repozytorium z GitHuba
RUN git clone https://github.com/Dawid511/ping-pong-java

# Ustawienie katalogu roboczego na ping-pong-java
WORKDIR /ping-pong-java

# Budowa projektu Gradle
RUN gradle build