

#crear un contenedor en docker de mysql

#iniciar un contendor 
docker run --name nombre_contenedor -e MYSQL_ROOT_PASSWORD=admin -p 3306:3306 -d mysql:latest

#ingresar a mysql en el contenedor

docker exec -it nombre_contendor mysql -u root -p

#creacion de BD  en mysql

#comandos de mysql

CREATE DATABASE nombre_base;
USE nombre_base;

#creacion de tabla 


CREATE TABLE Persons (
    PersonID int NOT NULL AUTO_INCREMENT,
    LastName varchar(255),
    FirstName varchar(255),
    PRIMARY KEY (PersonID)
);


#ingresa datos a la tabla 
INSERT INTO Persons (LastName, FirstName) VALUES("Torres","Santi");


#ver registros en la base de datos 
SELECT * FROM Persons;

#realizar backup de la BD en tu maquina 


mysqldump -P 3306 -h 172.17.0.3 -u root -p nombre_base_datos > db_backup.sql docker exec -it nombre_contenedor mysql -u root



