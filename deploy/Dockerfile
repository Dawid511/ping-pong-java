FROM build_stage

# Ustawienie katalogu roboczego na /deploy
#WORKDIR /
COPY my-app-1.0.jar /ping-pong-java/
RUN pwd
RUN ls -la deploy
RUN cd deploy
RUN pwd


RUN ls -la


# Komenda uruchamiająca aplikację
CMD ["java", "-jar", "my-app-1.0.jar"]