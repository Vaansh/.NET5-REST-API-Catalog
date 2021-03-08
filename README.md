# Catalog 

## Description
A REST API made using the .NET 5 framework. Deployed alongside MongoDB to Kubernetes. 

## Technologies practiced
C#, .NET 5 Framework, Dependency Injection, Postman, SwaggerUI, CRUD (GET/POST/PUT/DELETE), MVC, MongoDB, REST API, Docker, Kubernetes

---

## Testing
Run the following two commands and test the endpoints on `http://localhost:8080/items`
```
docker run -d --rm --name mongo -p 27017:27017 -v mongodbdata:/data/db 
-e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=Pass#word1 
--network=CatalogNetwork mongo
```
```
docker run -it --rm -p 8080:80
-e MongoDbSettings:Host=mongo -e MongoDbSettings:Password=Pass#word1 
--network=CatalogNetwork vaansh/catalog01:v1
```
![1](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/1.png)

---

## Stages of the project

1. ### Getting Started/Inital Commit
Create a .NET 5 Web API project from scratch, use VS Code for building and debugging the project, trust the development certificate and use Swagger UI to interact with the API.
![2](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/2.png)

2. ### Entity, Repository, Controller (GET)
Model an entity via C# record types, implement an in-memory repository of resources and implement a controller with GET routes to retrieve resources.
![3](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/3.png)

3. ### Dependency Injection, DTOs
Register and inject dependencies in .NET 5 and implement Data Transfer Objects (DTOs).
![4](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/4.png)

4. ### POST, PUT, DELETE
Create resources with POST, validate the values of DTO properties, update resources with PUT and delete resources with DELETE.

#### POST Endpoint:
![7](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/7.png)
![8](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/8.png)

#### PUT Endpoint:
![9](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/9.png)
![10](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/10.png)

#### DELETE Endpoint:
![5](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/5.png)
![6](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/6.png)

5. ### Persisting entities with MongoDB
Implement a simple MongoDB repository, run MongoDB as a docker container and use Postman to interact with a REST API.


6. ### Tasks, Async and Await
The asynchronous programming model - use tasks, async and await to add asynchronous programming to the REST API.
![12](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/12.png)

7. ### Secrets and Health Checks
Store and use secrets via the .NET Secret Manager and use health checks to report the health of the rest API and its dependencies.
![13](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/13.png)

8. ### Docker
Turn the REST API into a docker image and run it as a docker container.
![14](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/14.png)
![15](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/15.png)

9. ### Kubernetes
Stand up a basic Kubernetes cluster in the box, deploy the REST API (and MongoDB) to Kubernetes and scale the Kubernetes deployment.
![12](https://github.com/Vaansh/.NET5-REST-API-Catalog/blob/main/images/16.png)

---

## Folder structure
```
|-- Catalog
    |-- .dockerignore
    |-- .gitignore
    |-- Catalog.csproj
    |-- Dockerfile
    |-- Extensions.cs
    |-- Program.cs
    |-- README.md
    |-- Startup.cs
    |-- appsettings.Development.json
    |-- appsettings.json
    |-- .vscode
    |   |-- launch.json
    |   |-- settings.json
    |   |-- tasks.json
    |-- Controllers
    |   |-- ItemsController.cs
    |-- Dtos
    |   |-- CreateItemDto.cs
    |   |-- ItemDto.cs
    |   |-- UpdateItemDto.cs
    |-- Entities
    |   |-- Item.cs
    |-- Properties
    |   |-- launchSettings.json
    |-- Repositories
    |   |-- IItemsRepository.cs
    |   |-- InMemItemsRepository.cs
    |   |-- MongoDbItemsRepository.cs
    |-- Settings
    |   |-- MongoDbSettings.cs
    |-- bin
    |   |-- Debug
    |       |-- net5.0
    |           |-- Catalog.deps.json
    |           |-- Catalog.dll
    |           |-- Catalog.pdb
    |           |-- Catalog.runtimeconfig.dev.json
    |           |-- Catalog.runtimeconfig.json
    |           |-- DnsClient.dll
    |           |-- HealthChecks.MongoDb.dll
    |           |-- Microsoft.AspNetCore.Authentication.JwtBearer.dll
    |           |-- Microsoft.AspNetCore.Authentication.OpenIdConnect.dll
    |           |-- Microsoft.Extensions.Diagnostics.HealthChecks.Abstractions.dll
    |           |-- Microsoft.Extensions.Diagnostics.HealthChecks.dll
    |           |-- Microsoft.IdentityModel.JsonWebTokens.dll
    |           |-- Microsoft.IdentityModel.Logging.dll
    |           |-- Microsoft.IdentityModel.Protocols.OpenIdConnect.dll
    |           |-- Microsoft.IdentityModel.Protocols.dll
    |           |-- Microsoft.IdentityModel.Tokens.dll
    |           |-- Microsoft.OpenApi.dll
    |           |-- MongoDB.Bson.dll
    |           |-- MongoDB.Driver.Core.dll
    |           |-- MongoDB.Driver.dll
    |           |-- MongoDB.Libmongocrypt.dll
    |           |-- SharpCompress.dll
    |           |-- Swashbuckle.AspNetCore.Swagger.dll
    |           |-- Swashbuckle.AspNetCore.SwaggerGen.dll
    |           |-- Swashbuckle.AspNetCore.SwaggerUI.dll
    |           |-- System.IdentityModel.Tokens.Jwt.dll
    |           |-- appsettings.Development.json
    |           |-- appsettings.json
    |           |-- ref
    |           |   |-- Catalog.dll
    |           |-- runtimes
    |               |-- win
    |                   |-- native
    |                       |-- libzstd.dll
    |                       |-- snappy32.dll
    |                       |-- snappy64.dll
    |-- kubernetes
    |   |-- catalog.yaml
    |   |-- mongodb.yaml
    |-- obj
        |-- Catalog.csproj.nuget.dgspec.json
        |-- Catalog.csproj.nuget.g.props
        |-- Catalog.csproj.nuget.g.targets
        |-- project.assets.json
        |-- project.nuget.cache
        |-- Debug
            |-- net5.0
                |-- .NETCoreApp,Version=v5.0.AssemblyAttributes.cs
                |-- Catalog.AssemblyInfo.cs
                |-- Catalog.AssemblyInfoInputs.cache
                |-- Catalog.GeneratedMSBuildEditorConfig.editorconfig
                |-- Catalog.MvcApplicationPartsAssemblyInfo.cache
                |-- Catalog.MvcApplicationPartsAssemblyInfo.cs
                |-- Catalog.RazorTargetAssemblyInfo.cache
                |-- Catalog.assets.cache
                |-- Catalog.csproj.CopyComplete
                |-- Catalog.csproj.CoreCompileInputs.cache
                |-- Catalog.csproj.FileListAbsolute.txt
                |-- Catalog.csprojAssemblyReference.cache
                |-- Catalog.dll
                |-- Catalog.genruntimeconfig.cache
                |-- Catalog.pdb
                |-- project.razor.json
                |-- ref
                |   |-- Catalog.dll
                |-- staticwebassets
                    |-- Catalog.StaticWebAssets.Manifest.cache
                    |-- Catalog.StaticWebAssets.xml
```

---

## Conclusion
A REST API was created with GET, POST, PUT, DELETE to perform CRUD operations, as well as to practice important principles such as dependency principle, DTOs and familiarize myself with the new .NET5 framework. A docker image was created and deployed to kubernetes.
