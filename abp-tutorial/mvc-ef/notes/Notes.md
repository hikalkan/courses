# Introduction

Hello everybody,

I am Halil İbrahim Kalkan, the lead developer behind the ABP Framework.

ABP is an open source web application framework to create modern web applications based on the ASP.NET Core. It provides infrastructure to implement enterprise level software requirements. Handles and automates common development tasks for you to make you focus on your own business code, without repeating yourself.

In this video course, we will create a new web application based on the ABP Framework. The example application, called BookStore, is a typical back office application to manage books and their authors. The course will proceed step by step and will cover all the aspects of a typical web application, including localization, authorization, database integration, HTTP APIs, user interfaces and so on. It will also covers some basic principles of the Domain Driven Design.

---------------------------------------

Let's begin by creating the application.

-------------

The solution created has been layered based on the Domain Driven Design principles. You can find all details of the solution in the ABP documentation.

For now, you may not understand the full solution. But don't worry, you will recognize the projects through the development of the application.

In brief;

* Domain layer is separated into two projects:
  * Domain project contains the domain layer of the solution; entities, domain services, repository interfaces and so on.
  * Domain.Shared project is a part of the domain layer, but it is shared among all the layers. It typically contains constants and enum types.
* Application layer is separated into two projects;
  * Application.Contracts project contains the interface of the application services as well as the Data Transfer Objects defined for these application service interfaces.
  * Application project has the implementations of the services defined in the Contracts project. In this way, we have separated the interface from the application, so clients can only depend on the interfaces without knowing the implementations.
* EntityFramework project contains our DbContext and database mappings for the entities.
  * There is a separate EntityFramework.DbMigrations project that is used to unify the database migration. This solution uses code first approach to manage the database schema.
  * There is also a handy console application, named DbMigrator, which simple migrates and seeds the database. It is useful on development and production environments.
* HttpApi project contains API Controllers of the solution. Since the ABP Framework has conventional API controllers system, you mostly don't need to create the API Controllers manually. But, if you need, here the project you typically want to create API Controllers.
* HttpApi.Client project contains client proxies for dotnet applications those want to use your HTTP APIs. You can share this project to a client application, so it can easily consume your APIs. Again, ABP Framework automates to create dynamic c# proxies, so you typically don't write any code here, it automatically works.
* Finally, the Web project contains the user interface of your application.
* test folder contains unit and integration tests separated for each layer.

-----------

