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

# Wyświetlenie zawartości katalogu roboczego (do debugowania)
RUN ls -la

# Budowa projektu Gradle
RUN gradle build

# Wyświetlenie zawartości katalogu build/libs (do debugowania)
RUN ls -la build/libs

# Skopiowanie pliku JAR do katalogu docelowego
RUN cp build/libs/*.jar /deploy

# Czyszczenie pamięci podręcznej pakietów APT
RUN apt-get clean && rm -rf /var/lib/apt/lists/*
