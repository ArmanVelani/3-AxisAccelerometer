NAME: ARMAN VELANI (N01187157) (CENG317)
OTHER GROUP MEMBERS: SAJIVAAN RAMACHANDRAN (N01326022) (TECH 104)
FIRST STUDENT TECH 104
Setup {	Establish a connection with the database.
Ask the user to enter the address of the I2c (3 axis accelerometer MMA451)
Verify the I2c address with the addresses available in the database.
Prompt the user to enter their login credentials to give them a unique access
Enter the database credentials by using appropriate datatypes
Authenticate the user’s credentials and grant access to the user into the database.
}
3 axis accelerometer reads the x, y, and z coordinates and the degrees its point at and stores it in the data base refreshing every 0.05 milliseconds
Loop {	Takes the readings from the sensor for user’s reference
Match the sensor’s readings with the table (which way it’s facing)
Check if the database connection is still established and the sensor is connected to the database.
Send the readings from the sensor to the database for further use.
}
SECOND STUDENT AND THIRD STUDENT TECH 104 AND CENG 317
Setup {	Display a splash screen while establishing connection with the database
Ask the user to enter their database credentials or send them to a registration page. 
Verify the entered credentials with the ones in the database 
Confirm the user and grant access to database for further use.
}
Loop {	Select an option which shows what the user wants to see from the database
Send a SQL query to the database
Run the query and send the results to the application
Display the results of the query, if there was an error show an error code as to where the problem occurred.
}

 
UML Diagram
 

GRADES FOR OTHER STUDENTS
SAJIVAAN RAMACHANDRAN (N01326022) - Proficient 5/5
SHAWN QURESHI –NA 0
OTHER STUDENT (Qureshi, Shawn) DID NOT RESPOND TO THE CONTACT (HE WAS CONTACTED BY SAJIVAAN MULTIPLE TIMES BUT NO RESPONSE RECIEVED)

