FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /build
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o /app
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS final
COPY --from=build /app .
 ENTRYPOINT ["dotnet", "DotCore.dll"]
