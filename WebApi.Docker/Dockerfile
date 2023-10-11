
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["WebApi.Docker.csproj", "WebApi.Docker/"]
RUN dotnet restore "WebApi.Docker/WebApi.Docker.csproj"
COPY . WebApi.Docker
WORKDIR "/src/WebApi.Docker"
RUN dotnet build "WebApi.Docker.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebApi.Docker.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebApi.Docker.dll"]