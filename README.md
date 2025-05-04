# airbnb-clone-project

## Brief Overview

This project as the name suggests, will be a clone of the infamous airbnb, but it is backend oriented, this is part of the ProDev Backend Software engineering program. I will be using Django, Javascript and PostgreSQL as the main tech stack, there will be some more like Graphql, Redis, Celery, Docker and CI/CD Pipelines.


## Team Roles

### for team roles, currently its just me, but even for a solo developer i have to take different roles at the same time, the following roles is the perfect scenario and not reality

#this will be role : responsibility/mainly do
- **Business analyst** (BA) : Meets with the stakeholders/customers/users as they are the middle ground between them and the developers and the upper management.

- **Project manager (PM)** : Manages the development team and is responsible to meet deadlines.

- **UI/UX designer** : Creates the initial design according to the specifications of the customer until approval.

- **Software architect** : Designs the High-level architecture of the system and decides on the tools to be used but mostly the team uses the tools they are best at.

- **Software developer/Engineer** : Develops the code according to the UI/UX and the architecture may do unit tests

- **Quality assurance (QA) engineer** : Makes sure an application performs according to requirements, may do manual and automated tests.

this may vary depending on company size, culture and available personnal



## Technology Stack

- **Django**: A high-level Python web framework for building the RESTful API and backend systems
- **Django REST Framework**: Toolkit for creating powerful and flexible RESTful APIs
- **PostgreSQL**: Robust relational database for persistent data storage
- **GraphQL**: Query language for API to enable flexible data retrieval
- **JavaScript**: Client-side scripting for dynamic UI elements
- **Redis**: In-memory data store for caching and session management
- **Celery**: Asynchronous task queue for handling background processes
- **Docker**: Containerization platform for consistent development and deployment
- **CI/CD Pipelines**: Automated workflows for testing and deployment

## Database Design

### Key Entities and Relationships

#### Users
- **Fields**: username, email, password, profile_picture, date_joined
- **Relationships**: 
  - A User can own multiple Properties (as a host)
  - A User can make multiple Bookings (as a guest)
  - A User can leave multiple Reviews

#### Properties
- **Fields**: title, description, location, price_per_night, available_dates
- **Relationships**: 
  - A Property belongs to a User (host)
  - A Property can have multiple Bookings
  - A Property can have multiple Reviews
  - A Property can have multiple Images

#### Bookings
- **Fields**: check_in_date, check_out_date, total_price, status, guests_count
- **Relationships**: 
  - A Booking belongs to a User (guest)
  - A Booking belongs to a Property
  - A Booking can have one Payment

#### Reviews
- **Fields**: rating, comment, date_posted, review_title
- **Relationships**: 
  - A Review belongs to a User
  - A Review belongs to a Property
  - A Review is associated with a Booking

#### Payments
- **Fields**: amount, payment_date, payment_method, status
- **Relationships**: 
  - A Payment belongs to a Booking
  - A Payment belongs to a User (guest)