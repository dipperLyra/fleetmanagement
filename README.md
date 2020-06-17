# Fleet Management App
An application to manage fleet of cars. 

## User Story
1. User should be able to register cars
2. User should be able to register drivers
3. User should be able to assign a car to a driver
4. User should be able to send a notification when car servicing is due
5. User should be able to record car faults

## API Documentation
The documentation will be built with Swagger editor and hosted on swagger hub. 
The following table shows the summary of HTTP verbs, URI and nouns used. 

<table>
    <thead>
        <tr>
            <th>S/N</th>
            <th>Endpoints/Noun</th>
            <th>Verb(s)</th>
        </tr>
    </thead>
    <tr>
        <td>1</td>
        <td>/cars /cars/[i:id]</td>  
        <td>POST GET UPDATE DELETE</td>  
    </tr>
    <tr>
        <td>2</td>
        <td>/drivers /drivers/[i:id]</td>  
        <td>POST GET UPDATE DELETE</td>  
    </tr>
    <tr>
        <td>3</td>
        <td>/users /users/[i:id]</td>  
        <td>POST GET UPDATE DELETE</td>  
    </tr>
    <tr>
        <td>4</td>
        <td>/notifications /notifications/[i:id]</td>  
        <td>POST GET DELETE</td>  
    </tr>
</table>

Sample Request 

Db Schema
Admin
id INT(9) PRIMARY KEY AUTO_INCREMENT
first_name VARCHAR(45)
last_name VARCHAR(45)
full_name VARCHAR(45)
email VARCHAR(45)
password VARCHAR(45)
date_created DATETIME
Cars
id INT(9) PRIMARY KEY AUTO_INCREMENT
plate_number VARCHAR(45) UNIQUE
date_created DATETIME

Drivers
id INT(9) PRIMARY KEY AUTO_INCREMENT
first_name VARCHAR(45)
last_name VARCHAR(45)
full_name VARCHAR(45)
email_address VARCHAR(45)
date_created DATETIME

Assigned_Cars
id INT(9) PRIMARY KEY AUTO_INCREMENT
car_id INT(9) FOREIGN KEY REFERENCE(cars.id)
driver_id INT(9) FOREIGN KEY REFERENCE(drivers.id)
date_assigned DATETIME

Car_Servicing
id INT(9) PRIMARY KEY AUTO_INCREMENT
car_id INT(9) FOREIGN_KEY REFERENCE(car.id)
driver_id INT(9) FOREIGN_KEY REFERENCE(driver.id)
date_serviced DATETIME
Date_next_servicing DATETIME




Faults
id INT(9) PRIMARY KEY AUTO_INCREMENT
fault VARCHAR(45)
date_created DATETIME

Car_Faults
id INT(9) PRIMARY KEY AUTO_INCREMENT
car_id INT(9) FOREIGN KEY REFERENCE(car.id)
driver_id INT(9) FOREIGN KEY REFERENCE(driver.id)
fault_id INT(9) FOREIGN KEY REFERENCE(fault.id)
fault_date DATETIME

Messages
id INT(9) PRIMARY KEY AUTO_INCREMENT
message VARCHAR(45)
date_created DATETIME
date_updated DATETIME
Notifications
id INT(9) PRIMARY KEY AUTO_INCREMENT
driver_id INT(9) FOREIGN KEY REFERENCE(drivers.id)
message_id INT(9) FOREIGN KEY REFERENCE(message.id)
date_sent DATETIME 



API Design Story
Download springboot initializer and open a project in IntelliJ … done
Set up database connection… done
Define model schema
Implement repository that will use model
Implement services


controllers
