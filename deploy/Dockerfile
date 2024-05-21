FROM build_stage

# Ustawienie katalogu roboczego na /deploy
WORKDIR /ping-pong-java/build/libs

RUN jar tf my-app-1.0.jar
RUN jar xf my-app-1.0.jar META-INF/MANIFEST.MF

RUN cat META-INF/MANIFEST.MF
# Komenda uruchamiająca aplikację
CMD ["java", "-jar", "my-app-1.0.jar"]