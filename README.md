# DATABASE-RESTORE

USE master;
GO

CREATE DATABASE [SoowGood_System_Dev]

GO

ALTER DATABASE [SoowGood_System_Dev]
SET SINGLE_USER
WITH ROLLBACK IMMEDIATE;
GO

RESTORE DATABASE [SoowGood_System_Dev]
FROM DISK = 'C:\04.Backups\soowgood_live_database_30.bak'
WITH REPLACE,
MOVE 'SoowGood_System' TO 'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\DATA\SoowGood_System_Dev.mdf',
MOVE 'SoowGood_System_log' TO 'C:\Program Files\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\DATA\SoowGood_System_Dev_log.ldf';
GO

ALTER DATABASE [SoowGood_System_Dev]
SET MULTI_USER;
GO
