SmartLogix
Descripción
SmartLogix es una plataforma de gestión logística para eCommerce PYMEs,
desarrollada sobre una arquitectura de microservicios.
Permite gestionar pedidos e inventario de forma eficiente y escalable.
Arquitectura
SmartLogix está compuesto por los siguientes componentes:

smartlogix/
├── smartlogix-frontend      # Interfaz de usuario (React/NPM)
├── smartlogix-bff           # Backend For Frontend
├── smartlogix-ms-pedidos    # Microservicio de Pedidos
├── smartlogix-ms-inventario # Microservicio de Inventario
└── smartlogix-archetype/    # Arquetipo Maven para microservicios

                    ┌─────────────────────┐
                    │  smartlogix-frontend │  puerto 3000
                    │  React + Vite (NPM)  │
                    └──────────┬──────────┘
                               │ REST API
                    ┌──────────▼──────────┐
                    │   smartlogix-bff     │  puerto 8084
                    │  Backend For Frontend│
                    └────┬─────────────┬──┘
                         │             │
           ┌─────────────▼──┐    ┌─────▼──────────────┐
           │ ms-inventario  │    │    ms-pedidos        │
           │  puerto 8082   │    │    puerto 8081       │
           │  MySQL JPA     │    │    MySQL JPA         │
           └────────────────┘    └──────────────────────┘
           
Patrones Arquitectónicos Implementados

BFF (Backend For Frontend): Intermediario entre frontend y microservicios
Repository Pattern: Abstracción de acceso a datos vía Spring Data JPA
Factory Method: Creación estandarizada de objetos
CQRS: Separación de comandos y consultas
Strategy: Encapsulación de lógica de comunicación entre servicios
Observer: Sistema de notificaciones desacoplado en el frontend
DTO: Transferencia de datos entre capas

Repositorios
ComponenteRepositorioPuertoFrontendsmartlogix-frontend3000BFFsmartlogix-bff8084MS Pedidossmartlogix-ms-pedidos8081MS Inventariosmartlogix-ms-inventario8082Arquetiposmartlogix-archetype—
Estrategia de Branching
Se utiliza GitHub Flow:
main        ← rama principal, siempre desplegable
feature/*   ← ramas de funcionalidad creadas desde main
               integradas vía Pull Request
Requisitos del Sistema

Java 17+ (probado con Java 25 / Amazon Corretto)
Maven 3.9+
Node.js 18+
MySQL 8.0+

Orden de Ejecución

MySQL (puerto 3306)
MS Inventario (puerto 8082): mvn spring-boot:run
MS Pedidos (puerto 8081): mvn spring-boot:run
BFF (puerto 8084): mvn spring-boot:run
Frontend (puerto 3000): npm install && npm run dev

Equipo

Genesis Eroj
Francisco Monsalve

DSY1106 - Desarrollo Fullstack III
