# Car Rental System

A Java-based car rental management system with GUI and database integration.

## Features

- **Car Management**:
  - Add new cars to the system
  - View available cars
  - Rent and return cars
- **Customer Management**:
  - Register new customers
  - Track customer rentals
- **Database Integration**:
  - MySQL database for persistent storage
  - CRUD operations for cars, customers, and rentals
- **User Interface**:
  - Graphical user interface using Java AWT
  - Real-time updates of car availability

## Technologies Used

- Java 8+
- Java AWT for GUI
- MySQL Database
- JDBC for database connectivity

## Database Setup

1. Create a MySQL database named `car_rental_system`
2. Run the following SQL scripts to create the necessary tables:

```sql
CREATE TABLE cars (
    car_id VARCHAR(10) PRIMARY KEY,
    brand VARCHAR(50) NOT NULL,
    model VARCHAR(50) NOT NULL,
    base_price_per_day DECIMAL(10,2) NOT NULL,
    is_available BOOLEAN DEFAULT TRUE
);

CREATE TABLE customers (
    customer_id VARCHAR(10) PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

CREATE TABLE rentals (
    rental_id INT AUTO_INCREMENT PRIMARY KEY,
    car_id VARCHAR(10),
    customer_id VARCHAR(10),
    days INT NOT NULL,
    FOREIGN KEY (car_id) REFERENCES cars(car_id),
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);
```
## Clone Repo 
 -git clone https://github.com/yourusername/car-rental-system.git
