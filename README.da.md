[English](README.md) | **Dansk**

# Opgaver med .NET user secrets

Opret din egen .NET-solution med .NET CLI.

## 1. Installer .NET CLI

Åbn Terminal, PowerShell eller den terminal, du bruger.

### macOS

`brew install --cask dotnet-sdk`

### Windows

`winget install Microsoft.DotNet.SDK.8`

### Ubuntu

`sudo apt-get update`

`sudo apt-get install -y dotnet-sdk-8.0`

Kontroller altid installationen bagefter:

`dotnet --version`

## 2. Opret en ny solution

Vi vil oprette en ny solution med et Web API-projekt, ligesom når vi opretter det i Rider.

`dotnet new sln -n <solution-navn>`

Nu er solutionen oprettet, og vi vil oprette et nyt Web API-projekt:

`dotnet new webapi -o Api`

Nu vil vi tilføje API-projektet til solutionen:

`dotnet sln <solution-navn>.slnx add ./Api/Api.csproj`

Projektet skulle nu være tilføjet.

## 3. Hent `appsettings.json`

Før vi begynder på denne del, skal du sikre dig, at `appsettings.json` og `appsettings.Development.json` er tilføjet til `.gitignore`. Det gør du ved at åbne `.gitignore` og tilføje `appsettings.json` og `appsettings.Development.json`, hvis de ikke allerede står der.

Tilføj en connection string til en database i `appsettings.Development.json`.

## 4. Gem den som en user secret

Nu skal oplysningerne gøres endnu mere hemmelige ved hjælp af .NET user secrets.

Først skal du konfigurere projektet til user secrets ved at køre `dotnet user-secrets init`. Derefter er projektet klar.

Tilføj nu den angivne connection string til user secrets.

## 5. Tilføj andre secrets

Tilføj gerne andre secrets. Alle secrets kan gemmes som user secrets. Husk, at du altid kan se dem ved at køre `dotnet user-secrets list`.

## 6. Eksamensprojekt

Prøv at oprette forbindelse til dit eksamensprojekt fra sidste semester. Se, om du kan få forbindelse til databasen, når connection stringen er gemt som en user secret.
