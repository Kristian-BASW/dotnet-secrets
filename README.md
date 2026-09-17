**English** | [Dansk](README.da.md)

# .NET user-secrets exercises

Create your own dotnet solution with dotnet cli

## 1. Install dotnet cli

Open terminal, powershell or whatever you got.

### MacOS 
`brew install --cask dotnet-sdk`

### Windows
`winget install Microsoft.DotNet.SDK.8`

### Ubuntu
`sudo apt-get update`

`sudo apt-get install -y dotnet-sdk-8.0`


After installation, always check the installation
`dotnet --version`

## 2. Create a new solution
We want to create a new solution with a WebApi projec, just like we know it, when we create it inside rider.

`dotnet new sln -n <soluntion-name>`

Now the solution is created, now we want to create a new WebApi project

`dotnet new webapi -o Api`

Now we want to add the Api project to the solutiion

`dotnet sln <solution-name>.slnx add ./Api/Api.csproj`

Now the project should be added.


## 3. Get appSettings.json 

Before we start with this part, i want you to make sure that `appsettings.json` and `appsettings.Development.json` is added to the gitignore.
This is done by opening the gitignore and add the `appsettings.json` and `appsettings.Development.json` if they aren't added.

We want to add the ConnectionString to a database in the appSettings.Development.json

## 4. Make it as user secret

Now we want things to be even more secret, this is done by using the user secrets for dotnet.
First you need to setup your project for the UserSecrets, this is done by typing `dotnet user-secrets init`.
Now you are all set and ready to go.

Now add the specified ConnectionString into the user-secrets.

## 5. Add some others

Feel free to add some other secrets, all secrets can be told inside the user-secrets. But remember you can always get the secrets by typing `dotnet user-secrets list`

## 6. Exam-project

Try to make a connection to your exam-project for last semester and see if you can get a fully connection to the database, where the connection string should be inside the user-secret.
