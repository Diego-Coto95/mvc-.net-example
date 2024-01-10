# Sistema MVC Entity Framework Ejemplo Básico

## Descripción
Este proyecto es un Sistema de Gestión que utiliza MVC para la interfaz de usuario y SQL Server para la gestión de la base de datos. Permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) en [entidades específicas].

## Estado del Proyecto
El proyecto está finalizado y es una base para entender como se realiza un CRUD con MVC Entity Framework con SQL.

## Capturas de Pantalla
<img width="594" alt="image" src="https://github.com/Diego-Coto95/mvc-.net-example/assets/44104619/dbed4bc4-5eb2-44bb-be05-05eb7add1ca7">

## Instrucciones de Configuración
1. Clona el repositorio.
2. Configura la base de datos SQL Server según las instrucciones.
3. Abre el proyecto en Visual Studio.
4. Ejecuta la aplicación.

## Requisitos del Sistema
- .NET Framework
- SQL Server

## SQL
-- Creación Base de datos
CREATE DATABASE Supermercado
USE Supermercado

-- Creación de tablas
CREATE TABLE Categoria (
	CodigoCategoria int NOT NULL,
	NombreCategoria varchar(50) NULL,
CONSTRAINT PK_SUPERMERCADO PRIMARY KEY
(
	CodigoCategoria
)
)

CREATE TABLE Producto (
	Codigo int NOT NULL,
	Nombre varchar(50) NULL,
	Categoria int NULL,
CONSTRAINT PK_Producto PRIMARY KEY
(
	Codigo
),
CONSTRAINT FK_Producto_Categoria_Producto FOREIGN KEY
 (Categoria) REFERENCES Categoria (CodigoCategoria)
)

-- Insertar Categorias en la BD
insert into Categoria (CodigoCategoria,NombreCategoria) values (1,'Comida')
insert into Categoria (CodigoCategoria,NombreCategoria) values (2,'Limpieza')
insert into Categoria (CodigoCategoria,NombreCategoria) values (3,'Electronica')

-- Insertar Productos en la BD
insert into Producto (Codigo,Nombre, Categoria) values (2,'Jabón', 2)
insert into Producto (Codigo,Nombre, Categoria) values (3,'Laptop', 3)

-- Mostrar los datos
select * from Categoria
select * from Producto
