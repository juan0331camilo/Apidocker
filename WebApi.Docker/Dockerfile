FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS build
WORKDIR webapi
EXPOSE 80
EXPOSE 443

COPY ./*.csproj ./
RUN dotnet restore

COPY . .
RUN dotnet publish -c Release -o out 


FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /webapi
COPY --from=build /webapi/out .
ENTRYPOINT ["api", "WebApi.Docker.dll"] 