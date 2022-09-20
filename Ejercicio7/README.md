Se estan ejecutando 2 contenedores
El primero esta basado en una imagen de rubi que obtiene de aca: 
nicopaez/jobvacancy-ruby:1.3.0
El segundo esta basado en una imagen de postgres que obtiene desde:
postgres:14.4-alpine

services: Establece la cantidad de servicios que quiero montar 
  web:
    image: nicopaez/jobvacancy-ruby:1.3.0	Indica la imagen base que va a tener mi contenedor
    links:	Establece una comunicacion entre contenedores 
      - db	
    ports:	Define los puertos que se van a mappear
      - "3000:3000"	
    environment:	Aca se escriben comandos dedicados al ambiente declarado
      PORT: "3000"
      RACK_ENV: "production"
      DATABASE_URL: "postgres://postgres:Passw0rd!@db:5432/postgres"
    depends_on:		Indica la depedencia de ontros contenedores
      - db
  db:
    image: postgres:14.4-alpine
    environment:
      POSTGRES_PASSWORD: Passw0rd!


Los contenedores pueden verse debido a que yo le indico al docker compose que va a interactuar
con los otros contenedores que cree
