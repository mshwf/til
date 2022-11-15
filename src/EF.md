To execute migrations commands (i.e. `dotnet ef migration add..`)  
Move to the root folder of the migrations folder (the project that has the migrations folder)   
Try commenting-out the "win7-x86" RuntimeIdentifier tag from the csproj of projects with database related units.   
Run only `dotnet ef migrations add {InitialCreate OR JIRA reference, e.g. CTS-1234}`
