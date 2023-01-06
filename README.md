# ER Modeling and JPA Lab

## Learning Goals

- Develop an **Entity Relationship Data Model** for a specific problem domain.
- Use `dbdiagram.io` to create an **Entity Relationship Diagram (ERD)**.
- Use Java Persistence API (JPA) to implement the entities and relationships.

## Setup

1. [Fork and clone](https://github.com/learn-co-curriculum/java-mod-5-data-modeling-lab) the starter project.  
   - The `pom.xml` file contains the Hibernate and PostgreSQL dependencies.
   - The `org.example` directory contains `JpaCreate` and `JpaRead` classes with empty `main` methods.
   - The `org.example.model` directory is empty.  Add your JPA entity classes in this directory.
   - The `persistence.xml` file is configured to connect to `erd_lab_db`.
2. Use the `pgAdmin` application to create a new database named `erd_lab_db`.

## Instructions

Pick one of the following problem domains:

1. Hotel reservation database:  
   A hotel has rooms available for customers to reserve. Data about each room includes
   the room number, number and size of beds (i.e. full, queen, king), and whether it is a
   pet-friendly room.
   A customer makes a reservation to reserve one or more hotel rooms
   for a specific arrival and departure date.
   A customer must provide their name, email, phone number, and credit/debit card number
   to make a reservation.  Customers may make many reservations, but each reservation is for a single customer.
2. Vehicle repair appointment database:    
   An auto shop takes appointments to repair vehicles. 
   Data about each vehicle includes the make, model, year, and VIN.  An appointment
   is scheduled for one vehicle at a particular date and time, and
   a comment about the intended repair is included with the appointment.
   One or more mechanics may work on the vehicle during the appointment.  Data about each
   mechanic includes their name, date of hire, and social security number.
3. Airline flight scheduling database:    
   An airline flight has a scheduled departure and arrival date and time, and reserves
   a specific aircraft to be flown from a departure airport to a destination airport.
   Airports are identified with a unique 3 character code called an IATA location identifier,
   such as ORD for Chicago O'Hare Airport or BOS for Boston Logan Airport.
   Data about each aircraft includes the year built, type, make, model, and a unique registration number.
   One or more pilots are scheduled to fly the aircraft during a flight.
   Data about each pilot includes their name, flying certificate identifier, and age.


## Task #1

Create an **Entity Relation Diagram (ERD)** using `dbdiagram.io`
for one of the problem domains listed above.
You are free to adapt the problem description to add or
remove entities and attributes as long as your model includes the following:

- The ERD should contain at least 3 entities with appropriately named and typed attributes,
  including a primary key.
- The ERD should contain at least one one-to-many relationship.
- The ERD should contain at least one many-to-many relationship.

Make sure to name and save your ERD in `dbdiagram.io`.

## Task #2

1. Create Java classes in the `org.example.model` directory to implement
   the entities and relationships from your ERD.
2. Add comments to your Java classes to describe assumptions you made about the entities and relationships.
3. Edit `JpaCreate` to create several entities along with
   one-to-many and many-to-many relationships between the entities.
   Make sure `persistence.xml` sets `hibernate.hbm2ddl.auto` to `create`.    
   ```xml
   <property name="hibernate.hbm2ddl.auto" value="create" /> <!-- create / create-drop / update / none -->
   ```
4. Edit `JpaRead` to fetch a few entities from the database and print their state.
   Make sure `persistence.xml` sets `hibernate.hbm2ddl.auto` to `none`.
   ```xml
   <property name="hibernate.hbm2ddl.auto" value="none" /> <!-- create / create-drop / update / none -->
   ```

## Deliverables

1. Export your ERD as a pdf:  
   ![export erd pdf](https://curriculum-content.s3.amazonaws.com/6036/java-mod-5-erd-lab/export_erd_pdf.png)
2. Copy the exported pdf into your project folder.
3. Submit your completed project to Canvas.

## Resources

- [dbdiagram.io](https://dbdiagram.io/home)