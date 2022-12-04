-- SYSADMIN --

-- Create a warehouse of size X-SMALL
create warehouse public_wh with
warehouse_size='X-SMALL'
auto_suspend=300 
auto_resume= true

-- grant usage to role public
grant usage on warehouse public_wh 
to role public

-- create a database accessible to everyone
create database common_db;
grant usage on database common_db to role public

-- create sales database for sales
create database sales_database;
grant ownership on database sales_database to role sales_admin;
grant ownership on schema sales_database.public to role sales_admin

SHOW DATABASES;


-- create database for hr
drop database hr_db;
grant ownership on database hr_db to role hr_admin;
grant ownership on schema hr_db.public to role hr_admin
