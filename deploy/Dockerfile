FROM build_stage

# Ustawienie katalogu roboczego na /deploy
WORKDIR /ping-pong-java/build/libs
RUN ls -la
RUN ls -la build/libs
RUN ls -la deploy


# Komenda uruchamiająca aplikację
CMD ["java", "-jar", "my-app-1.0.jar"]