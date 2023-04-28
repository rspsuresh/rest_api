# REST API Auth JWT Example
**First create users in the "rest_api" database**

	CREATE TABLE users (
		id int NOT NULL AUTO_INCREMENT, 
		firstname varchar(255) NOT NULL,
		lastname varchar(255) NOT NULL, 
		email varchar(255) NOT NULL, 
		password varchar(255) NOT NULL, 
		created datetime  DEFAULT CURRENT_TIMESTAMP NOT NULL, 
		modified timestamp DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP NOT NULL,
		PRIMARY KEY (id)
	);

**Create user**
	
	http://localhost/rest_api/api/create_user.php

With request body data

	{
    	"firstname" : "test",
    	"lastname" : "test",
    	"email" : "test@dummymail.com",
    	"password" : "555"
	}

**Login user**

	http://localhost/rest_api/api/login.php

Enter in body
	
	{
    "email" : "test@dummymail.com",
    "password" : "555"
	}

**Test token access**

	http://localhost/rest_api/api/validate_token.php

Enter in request body

	{
    "jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3Q6ODA4MFwvIiwiYXVkIjoiaHR0cDpcL1wvbG9jYWxob3N0OjgwODBcLyIsImlhdCI6MTM1Njk5OTUyNCwibmJmIjoxMzU3MDAwMDAwLCJkYXRhIjp7ImlkIjoiMiIsImZpcnN0bmFtZSI6Ik1pa2UiLCJsYXN0bmFtZSI6IkRhbGlzYXkiLCJlbWFpbCI6Im1pa2VAY29kZW9mYW5pbmphLmNvbSJ9fQ.nyMRPlg0MSI_8xevui3aeW9suDHjBA6PWk05igYT_OY"
	}

**Update user**

	http://localhost/rest_api/api/update_user.php

Body has the following details

	{
	    "firstname" : "test",
	    "lastname" : "test",
	    "email" : "test@dummymail.com",
		"jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3Q6ODA4MFwvIiwiYXVkIjoiaHR0cDpcL1wvbG9jYWxob3N0OjgwODBcLyIsImlhdCI6MTM1Njk5OTUyNCwibmJmIjoxMzU3MDAwMDAwLCJkYXRhIjp7ImlkIjoiMiIsImZpcnN0bmFtZSI6Ik1pa2UiLCJsYXN0bmFtZSI6IkRhbGlzYXkiLCJlbWFpbCI6Im1pa2VAY29kZW9mYW5pbmphLmNvbSJ9fQ.nyMRPlg0MSI_8xevui3aeW9suDHjBA6PWk05igYT_OY"
	}					
