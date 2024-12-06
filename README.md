
# BASE DE DATOS DEL CRUD 

BASE DE DATOS:

create user 'manuel07'@'localhost' identified by '0421';


create database adso;
use adso;


grant all privileges on adso.* to 'manuel07'@'localhost';
FLUSH PRIVILEGES; 


use adso;

create table lenguajes(
     id_lenguaje int auto_increment,
     lenguaje varchar(30),
     primary key(id_lenguaje)
);


create table generos(
     id_genero int auto_increment,
     genero varchar(15),
     primary key(id_genero)


);


create table ciudades(
        id_ciudad int auto_increment,
        ciudad varchar(30),
        primary key(id_ciudad)

);




create table usuarios(
       id_usuario int auto_increment,
       nombres  varchar(50) not null ,
       apellidos varchar(50) not null,
       correo varchar (100) not null,
       fecha_nacimiento date,
       id_genero int ,
       id_ciudad int,
       primary key(id_usuario),
       unique(correo),
       foreign key (id_genero) references generos(id_genero),
       foreign key (id_ciudad) references ciudades(id_ciudad)


);


create table lenguaje_usuarios(
         id int auto_increment,
         id_usuario int,
         id_lenguaje int,
         primary key(id),
		 foreign key(id_usuario) references usuarios(id_usuario),
         foreign key(id_lenguaje) references lenguajes(id_lenguaje)


);


insert into ciudades (ciudad) values ('Bucaramanga'),('Floridablanca'),('Giron'),('Piedecuesta'),('Lebrija');
insert into generos (genero) values('Masculino'),('Femenino'),('Otro');
insert into lenguajes (lenguaje) values ('JAVA'),('.NET'),('Python'),('JavaScript'),('SQL'),('PHP');

insert into generos (genero) value("Transformer");
