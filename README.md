# SmartLogix

## Descripción
SmartLogix es una plataforma de gestión logística para eCommerce PYMEs,
desarrollada sobre una arquitectura de microservicios desplegada en AWS.
Permite gestionar pedidos, inventario y envíos de forma eficiente y escalable.

## Arquitectura
SmartLogix está compuesto por los siguientes componentes:

smartlogix/
├── smartlogix-frontend      # Interfaz de usuario (React/NPM)
├── smartlogix-bff           # Backend For Frontend
├── smartlogix-ms-pedidos    # Microservicio de Pedidos
├── smartlogix-ms-inventario # Microservicio de Inventario
└── archetype/               # Arquetipo Maven para microservicios


## Patrones Arquitectónicos Implementados
- **API Gateway**: Punto de entrada único al sistema
- **Repository Pattern**: Abstracción de acceso a datos
- **Factory Method**: Creación estandarizada de objetos
- **CQRS**: Separación de comandos y consultas
- **BFF (Backend For Frontend)**: Intermediario entre frontend y microservicios
- **DTO**: Transferencia de datos entre capas

## Repositorios

| Componente | Repositorio | Puerto |
|---|---|---|
| Frontend | [smartlogix-frontend](https://github.com/GenesisEroj/smartlogix-frontend) | 3000 |
| BFF | [smartlogix-bff](https://github.com/GenesisEroj/smartlogix-bff) | 8080 |
| MS Pedidos | [smartlogix-ms-pedidos](https://github.com/GenesisEroj/smartlogix-ms-pedidos) | 8081 |
| MS Inventario | [smartlogix-ms-inventario](https://github.com/GenesisEroj/smartlogix-ms-inventario) | 8082 |

## Estrategia de Branching
Se utiliza **GitHub Flow**:
main        ← rama principal, siempre desplegable
feature/*   ← ramas de funcionalidad creadas desde main, integradas vía Pull Request

## Requisitos del Sistema
- Java 17+
- Maven 3.9+
- Node.js 18+
- MySQL 8.0+

## Orden de Ejecución
1. MS Inventario (puerto 8082)
2. MS Pedidos (puerto 8081)
3. BFF (puerto 8080)
4. Frontend (puerto 3000)

## Equipo
- Genesis Eroj
- Francisco Monsalve

**DSY1106 - Desarrollo Fullstack III**