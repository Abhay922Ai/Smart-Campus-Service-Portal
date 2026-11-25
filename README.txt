EX-11: SMART CAMPUS SERVICE PORTAL
Feature extension integrating ASP.NET Core MVC + SQL Server Database + REST API.

REQUIREMENTS
- Visual Studio 2022
- .NET 8 SDK
- SQL Server / SQL Server Express
- Internet connection for first NuGet package restore

PROJECT SETUP
1. Extract the ZIP file.
2. Open SmartCampusPortal.csproj in Visual Studio 2022.
3. Restore NuGet packages when prompted.
4. Open appsettings.json and update the Server value if your SQL Server instance is different.
   Default connection string uses: Server=.;Database=SmartCampusDB;Trusted_Connection=True;TrustServerCertificate=True
5. Open Package Manager Console and ensure the Default project is SmartCampusPortal.
6. Run: Add-Migration InitialCreate
7. Run: Update-Database
8. Press F5 to run the application.

If Add-Migration is not recognized, install/restore Microsoft.EntityFrameworkCore.Tools.
Alternatively, from a terminal in this folder run:
   dotnet tool install --global dotnet-ef --version 8.*
   dotnet ef migrations add InitialCreate
   dotnet ef database update

PAGES AND API
MVC dashboard: /
Submit request: POST /Home/Create
API list: GET /api/ServiceApi
API details: GET /api/ServiceApi/{id}
API create: POST /api/ServiceApi
API update: PUT /api/ServiceApi/{id}
API delete: DELETE /api/ServiceApi/{id}
Swagger UI: /swagger (Development environment)

SAMPLE API POST/PUT JSON
{
  "studentName": "Rahul Sharma",
  "serviceType": "IT Support",
  "description": "Wi-Fi is not working in the hostel",
  "status": "Pending"
}

NOTES
- MVC views use Razor syntax.
- Entity Framework Core creates and accesses the SQL Server table.
- The REST API and MVC dashboard use the same database.
- This is an educational demonstration. Authentication and role-based authorization are not included.
