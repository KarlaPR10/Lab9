Tasks:
 Design Exercise:
  Application Brief: Participants are given a description of a monolithic e-commerce application handling user management, product catalog, order processing, and customer support.
    Task: Identify and outline potential microservices based on domain-driven design principles. Participants will determine service boundaries, define how services will communicate, and plan how to handle shared data.
  Monolithic E-Commerce Application Description:
  The application is a traditional e-commerce platform that encompasses all functionalities within a single, unified software architecture. The application handles the following key operations:
  User Management: Manages user profiles, authentication, and authorization. It stores personal information, manages login sessions, and handles user preferences.
  Product Catalog: Maintains a comprehensive list of products, including descriptions, pricing, images, and inventory levels. It supports product search and categorization functionalities.
  Order Processing: Manages all aspects of the ordering process, from cart management to order placement, payment processing, and order history tracking.
  Customer Support: Handles customer inquiries, returns, complaints, and feedback through a ticket-based system integrated with the user and order databases.
  The application is built on a single relational database that holds all user data, product information, orders, and customer support interactions. It currently operates on a single code base with a web-based frontend that communicates directly with the backend server.
  The platform has been experiencing challenges with scaling during high-traffic periods, frequent downtimes during updates, and increasing difficulty in implementing new features without affecting existing functionalities. The goal is to decompose this monolithic architecture into a microservices-based architecture to address these issues and improve overall agility and scalability.
  Implementation Simulation:
  Migration Roadmap: Develop a detailed plan for migrating the identified monolithic components to microservices. This plan should include prioritization of services to be migrated, identification of dependencies, and a strategy for data migration.

  Se empezaria con realizar un Respaldo de la base de datos existen para posteriormente ir alimentando las entidades que van a consumir cada microservicio derivado de su flujo dando la siguiente prioridad  login y nuevos usuarios,  productos, proceso ordenes dejando al final atencion al cliente.
  
  Architecture Documentation: Document the proposed microservices architecture, illustrating the interaction between services and the migration steps. Include a brief narrative explaining the rationale behind key decisions.
  Lo primero que debemos hacer es crear las bases de datos y migrar lo más importante para los clientes, su información personal, también debemos crear la API de administración de usuarios y modificar y borrar todas las cosas en las que usamos información de usuario en el servicio monolítico, luego Cuando el microservicio se está ejecutando, debemos señalar esos puntos finales desde el frente. Deberíamos repetir esto para crear todos los microservicios en el siguiente orden de API:

  Se toma la decision de dividirlo en 5 Microservicio para poder gestionar y administrar mejor la informacion y los flujos y su deber ser de unica responsabilidad, contemplando que seria bueno desde un principio tener un orquestador  ya que es una migracion ya se cuenta con una demanda importante de eventos.

User Management
Order Processing
Product Catalog
Customer Support
Orchestrator API
