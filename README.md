Step 1: Clone the repository
git clone https://github.com/jorgealdaba022416-coder/IM2Project.git

cd IM2Project



Step 2: Restore NuGet packages

dotnet restore



Step 3: Import the database

Open SSMS (or your SQL client).

Connect to your SQL Server instance (e.g., localhost).

Create a new database:

CREATE DATABASE aldaba_fmarketdirect;



Step 4: Create the SQL user account
When using SQL Server:

-- Create the login (if not already exists)

CREATE LOGIN root WITH PASSWORD = '0430';

-- Create a user in your database

USE FMarketDirect;

CREATE USER root FOR LOGIN root;

-- Give the user full permissions (so the project can read/write)

ALTER ROLE db_owner ADD MEMBER root;


When using MYSQL:

CREATE USER 'root'@'localhost' IDENTIFIED BY '0430';

GRANT ALL PRIVILEGES ON FMarketDirect.* TO 'root'@'localhost';

FLUSH PRIVILEGES;


Step 6: Run the project
