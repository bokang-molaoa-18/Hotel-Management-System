# Hotel Management System Architecture

## Introduction
This document outlines the C4 architectural diagrams for the Hotel Management System. The C4 model provides a simple yet powerful way to describe and visualize software architecture at different levels of abstraction.

## Level 1: System Context Diagram
The System Context Diagram provides a high-level overview of the Hotel Management System, showing how it interacts with external entities.

```mermaid
graph TD
    Guest -->|Book Room| WebApplication
    HousekeepingStaff -->|Receive Tasks| MobileApp
    FrontDeskStaff -->|Manage Reservations| WebApplication
    Management -->|View Reports| WebApplication
    WebApplication -->|Read/Write Data| Database
    MobileApp -->|Read/Write Data| Database
    subgraph Hotel Management System
        WebApplication
        MobileApp
        Database
    end
```

## Level 2: Container Diagram
The Container Diagram shows the high-level architecture of the Hotel Management System, including the major containers such as the web application, mobile app, and database.

```mermaid
graph TD
    Guest -->|Book Room| WebApplication
    HousekeepingStaff -->|Receive Tasks| MobileApp
    FrontDeskStaff -->|Manage Reservations| WebApplication
    Management -->|View Reports| WebApplication
    WebApplication -->|Backend API| BackendAPI
    MobileApp -->|Backend API| BackendAPI
    BackendAPI -->|Read/Write Data| Database

    subgraph Hotel Management System
        subgraph Web Server
            WebApplication
            BackendAPI
        end
        subgraph Mobile Device
            MobileApp
        end
        subgraph Database Server
            Database
        end
    end
```

## Level 3: Component Diagram
The Component Diagram provides a more detailed view of the internal structure of the Web Application and Mobile App, showing the key components and their interactions.

### Web Application Components
```mermaid
graph TD
    subgraph Web Application
        Frontend -->|Authentication Service| AuthenticationService
        Frontend -->|Reservation Service| ReservationService
        Frontend -->|Housekeeping Service| HousekeepingService
        Frontend -->|Reporting Service| ReportingService
        AuthenticationService -->|Backend API| BackendAPI
        ReservationService -->|Backend API| BackendAPI
        HousekeepingService -->|Backend API| BackendAPI
        ReportingService -->|Backend API| BackendAPI
    end
```

### Mobile App Components
```mermaid
graph TD
    subgraph Mobile App
        TaskManager -->|Authentication Service| MobileAuthService
        TaskManager -->|Housekeeping Service| MobileHousekeepingService
        MobileAuthService -->|Backend API| BackendAPI
        MobileHousekeepingService -->|Backend API| BackendAPI
    end
```

## Level 4: Code Diagram
The Code Diagram provides a detailed view of the internal structure of a specific component, such as the Reservation Service.

### Reservation Service (Example in Node.js)
```mermaid
classDiagram
    class ReservationController {
        +createReservation()
        +cancelReservation()
        +getReservation()
    }

    class ReservationService {
        +bookRoom()
        +processCancellation()
        +fetchReservation()
    }

    class ReservationRepository {
        +save()
        +delete()
        +findById()
    }

    ReservationController --> ReservationService
    ReservationService --> ReservationRepository
```

## Conclusion
The C4 architectural diagrams provide a comprehensive view of the Hotel Management System at different levels of abstraction. These diagrams help in understanding the system's structure, components, and interactions, facilitating better planning, development, and maintenance.
