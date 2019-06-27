# Moesif .NET Example

[Moesif](https://www.moesif.com) is an API analytics platform. [Moesif.Middleware](https://github.com/Moesif/moesif-dotnet)
is a middleware that makes integration with Moesif easy for .NET applications.

This is an example of .NET application with Moesif integrated.

## Key files

Moesif Middleware's [github readme](https://github.com/Moesif/moesif-dotnet) already documented
the steps to setup Moesif Middleware. But here is the key file where the Moesif integration is added:

- `Startup.cs` added the Moesif middleware to the pipeline.
- `Settings/MoesifOptions.cs` added Moesif middleware related settings.

## How to run this example.

1. Install Moesif Middleware if you haven't done so. `Install-Package Moesif.Middleware`

2. Be sure to edit the `Settings/MoesifOptions.cs` to change the application id to your
application id obtained from Moesif.

  ```csharp
  Dictionary<string, object> moesifOptions = new Dictionary<string, object>
        {
            {"ApplicationId", 'Your Application ID Found in Settings on Moesif'},
            {"LogBody", true},
            ...
        }
  ```

3. See `EmployeeController.cs` for some urls that you can hit the server with
(e.g. `http://localhost:5000/api/employee/42`), and the data
should be captured in the corresponding Moesif account of the application id.
