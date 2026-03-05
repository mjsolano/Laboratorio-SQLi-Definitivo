FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
# Copia y restaura (ajusta el nombre del .csproj si es necesario)
COPY ["LaboratorioSQLi.csproj", "./"]
RUN dotnet restore
# Compila
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "LaboratorioSQLi.dll"]
