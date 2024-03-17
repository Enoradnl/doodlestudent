# Utiliser une image de base légère
FROM eclipse-temurin:17.0.10_7-jdk-jammy

# Installations nécéssaires
RUN apt-get update
RUN apt-get install -y maven
RUN apt-get install -y git

# Téléchargement de l'application
RUN git clone https://github.com/barais/doodlestudent.git

# Build
WORKDIR doodlestudent/api
RUN ./mvnw clean package -Dquarkus.package.type=uber-jar

# Lancement de l'application
CMD java -jar target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar

# EXPOSE 8080