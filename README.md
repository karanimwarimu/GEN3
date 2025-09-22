# File Upload & Unique ID Generator (C# WinForms)

A simple C# application that allows users to:
- Upload files and store details in a SQL Server database.
- View and manage uploaded data in tables.
- Automatically generate unique IDs based on the current date.

⚠️ **Note:** This app requires Microsoft SQL Server. You must create a table in your database before running the app.

---

## Features
- 📂 Upload and save files.
-  DisplayS data in a grid/table.
- 🔑 Generate unique IDs that uses the current date  and previous id from db .
- 🗄️ Store all information in SQL Server.

---

## Requirements
- Windows OS
- [Visual Studio](https://visualstudio.microsoft.com/) (2019 or later recommended)
- .NET Framework 4.7.2 (or higher)
- Microsoft SQL Server (local or remote)

---

## Database Setup
1. Create a SQL Server database (e.g. `FileDB`).
2. Run the following SQL script to create the table:

```sql if table isnt and the code to setup one isnt showing 
  CREATE TABLE EmployeeLeaveTypes (
                            LeaveTypeID NVARCHAR(50) PRIMARY KEY,
                            LeaveTypeName NVARCHAR(100),
                            MaxDaysPerYear INT,
                            CarryForwardAllowed BIT,
                            PaidLeave BIT,
                            RequiresApproval BIT,
                            ImageData VARBINARY(MAX) NULL,
                            FileData VARBINARY(MAX) NULL
```
## Configuration
1. Open **App.config** in the project.
2. Update the connection string to match your SQL Server setup:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <startup> 
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7.2" />
    </startup>
		<add name="MyDbConnection"	 
				 connectionString="Server=SERVERNAME\INSTANCE;Database=OWNDATABASENAME;Trusted_Connection=True;TrustServerCertificate=True"
				 providerName="System.Data.SqlClient" />
	</connectionStrings>
	
</configuration> 

