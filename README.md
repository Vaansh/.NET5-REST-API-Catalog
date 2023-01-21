<!-- PROJECT LOGO -->
<br />

  <h3 align="center">Catalog Api</h3>

  <p align="center">
    A .NET 5 based Rest Api.
    <br />
    <a href="https://github.com/Vaansh/.NET5-REST-API-Catalog"><strong>See the code »</strong></a>
    <br />
  </p>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=whit">
  <img src="https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white">
  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white">
  <img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white">
</p>

### Description

A REST API made using the .NET 5 framework – with GET, POST, PUT, DELETE endpoints to perform CRUD operations, as well as to practice important principles such as dependency injection, DTOs and to familiarize myself with the new .NET 5 framework. A docker image of the project was created.

## Technologies practiced

C#, .NET 5 Framework, Dependency Injection, Postman, SwaggerUI, MVC, MongoDB, REST API, Docker, Kubernetes

## Testing

Run the following two commands and test the endpoints on `http://localhost:8080/items`

```zsh
docker run -d --rm --name mongo -p 27017:27017 -v mongodbdata:/data/db
-e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=Pass#word1
--network=CatalogNetwork mongo
```

```zsh
docker run -it --rm -p 8080:80
-e MongoDbSettings:Host=mongo -e MongoDbSettings:Password=Pass#word1
--network=CatalogNetwork vaansh/catalog01:v1
```

![1](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/1.png)

## Endpoints

1. **GET** /items/{id}

   ![3](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/3.png)

2. **POST** /items

   ![7](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/7.png)
   ![8](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/8.png)

3. **PUT** /items/{id}

   ![9](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/9.png)
   ![10](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/10.png)

4. **DELETE** /items/{id}

   ![5](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/5.png)
   ![6](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/6.png)
