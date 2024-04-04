## 1. Introduction
 
### 1.1 Purpose
The purpose of this document is to provide a comprehensive overview of the technical aspects of the Ticket Booking. It covers the technology stack, integration with other services and key functionalities.
 
### 1.2 Scope
The Ticket Booking aims to facilitate the seamless booking of tickets for various movies. It is part of a microservice that integrates along with other services such as the ShowInformationService and the SeatAvailabilityService as discussed in detail in the following sections.
## 2. Technology Stack
| System Component| Tech Stack |
| ------------- | ------------- |
| Client-side Web  | Angular  |
| Backend Service  | Springboot  |
| Database  | H2  |
| Communication  | Restful API  |
 
 
## 3. Key Features
 
### 3.1 Event/Movie Listings
- Integrated with ShowInformationService to get movie information such as title, images, and schedule.
 
### 3.2 Booking and Seat Availability
- Integrated with SeatAvailabilityService to get information on which seats are occupied and which are still available.
 
 
## 4. Data Storage
 
- The data is stored in built-in database for SpringBoot which is H2
 
 
## 5. Future Enhancements
 
- Integration with third-party APIs for additional event information.
- Enhanced recommendation systems for personalized suggestions.
- Unit testing, integration testing, and user acceptance testing.
- Caching mechanisms for frequently accessed data.
- Content Delivery Network (CDN) for efficient content distribution.
- Secure Sockets Layer (SSL) for data encryption during transmission.
- Implementing security best practices to prevent common vulnerabilities (e.g., SQL injection, Cross-Site Scripting).
 
## Conclusion
 
This technical document outlines the architecture, features, and technologies used in the development of the Ticket Booking App. It serves as a guide for developers, administrators, and stakeholders involved in the project.

## Block Diagram for TheatreBooking System

```mermaid
graph LR
    subgraph "TheatreBooking System"
		THB(TheatreBooking)
        TB(TicketBooking)
		DB1[(H2)]
        SI(ShowInformation)
		DB2[(H2)]
        SA(SeatAvailability)
		DB3[(H2)]
        THB -- "Get /shows" --> SI
        THB -- "Get /seat-availability" --> SA
        THB -- "Get /bookings" --> TB
        TB -- "Post /seat-availability" --> SA
        TB -- "Get /shows/{showId}" --> SI
        SA -- "Get /shows/{showId}" --> SI
        SA -- "Get /seat-availability" --> TB
	TB <--> DB1
	SI <--> DB2
	SA <--> DB3
    end
```
