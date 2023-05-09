## Demo RPG Game API application with ASP.NET Core

This Project based on [patrickgod/dotnet7-rpg](https://github.com/patrickgod/dotnet7-rpg) project.

It showcases:
- Blazor WebAssembly
- Minimal APIs
- Using EntityFramework and SQL Server for data access
- JWT authentication

## Prerequisites

### .NET
1. [Install .NET 7](https://dotnet.microsoft.com/en-us/download)

### Database
1. Install the **dotnet-ef** tool: `dotnet tool install dotnet-ef -g`
2. Run `dotnet ef database update` to create the database.
Learn more about [dotnet-ef](https://learn.microsoft.com/en-us/ef/core/cli/dotnet)

### JWT 

1. To initialize the keys for JWT generation, run `dotnet user-jwts` in to [TodoApi](TodoApi) folder:

    ```
    dotnet user-jwts create
    ```

### Running the application
To run the application:

   - **Visual Studio Code** - Open up terminal windows, on root dir run: 
   
      ```
      dotnet watch run
      ```
This will run application with hot reload.


## Optional

### Using the API standalone
The Todo REST API can run standalone as well. You can run the project and make requests to various endpoints using the Swagger UI (or a client of your choice):


Before executing any requests, you need to create a user and get an auth token.

1. To create a new user, run the application and POST a JSON payload to `/users` endpoint:

    ```json
    {
      "username": "myuser",
      "password": "<put a password here>"
    }
    ```
1. To get a token for the above user run `dotnet user-jwts` to create a JWT token with the same user name specified above e.g:

    ```
    dotnet user-jwts create -n myuser
    ```
1. You should be able to use this token to make authenticated requests to the todo endpoints.
1. Learn more about [user-jwts](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/minimal-apis/security?view=aspnetcore-7.0#using-dotnet-user-jwts-to-improve-development-time-testing)