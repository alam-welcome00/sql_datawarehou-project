/*
==================================
Create Database 'Datawarehouse'
===================================
Script purpose:
      This script will create new database 'Datawarehouse' after checking if it already exist.
If it already exist, it will drop and recreate dateabase, Moreover it will also create three 
schema with database 'Bronze', 'Silver' and 'Gold'.
Warning:
		Running this scrip will delete 'Datawarehouse' database if it already exists.
		All data will lost permanently. Proceed with caution and ensure you have proper backup of data
*/
--use master
use master;
 go
--Drop and create the database 'Datawarehouse'
if exists (select 1 from sys.databases where name = 'Datawarehouse')
Begin
	alter database 'Datawarehouse' set single_user with rollback immediate;
	drop database 'Datawarehouse'
end;
go

--create database 
create database Datawarehouse;
go 

--use datawarehouse
use Datawarehouse;
go 

--create schemas
create schema bronze;
Go -- GO is just seperator which tell first execute this then go to that.
create schema silver;
go
create schema gold;
go


# sql_datawarehou-project
Building a modern data warehouse with SQL server, include ELT process, data modelling and analytics.
