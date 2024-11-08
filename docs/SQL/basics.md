# Basics

## Login

`sudo mariadb -u root -p`  
`CREATE DATABASE your_database_name;`  
`CREATE USER 'your_username'@'localhost' IDENTIFIED BY 'your_password';`  
`GRANT ALL PRIVILEGES ON your_database_name.* TO 'your_username'@'localhost';`  
`FLUSH PRIVILEGES;`

## Create table

```sql
CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Insert data
```sql
INSERT INTO users (username, email) VALUES
('john_doe', 'john@example.com'),
('jane_smith', 'jane@example.com'),
('mike_jones', 'mike@example.com');
```

## Query