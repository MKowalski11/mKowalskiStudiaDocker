# na podstawie docs.docker.com/engine/examples/dotnetcore/
#FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build-env
WORKDIR /app
EXPOSE 8080
#ENV ASPNETCORE_URLS=http://+:8080
# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1

COPY --from=build-env /app/out .
ENTRYPOINT ["dotnet", "WebApi2.dll"]