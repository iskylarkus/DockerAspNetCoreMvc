FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
WORKDIR /app
COPY *.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish DockerAspNetCoreMvc.csproj -c Release -o out
FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
WORKDIR /app
COPY --from=build /app/out .
ENV ASPNETCORE_URLS="http://*:4500"
ENTRYPOINT ["dotnet", "DockerAspNetCoreMvc.dll"]


# docker build -t dockeraspnetcoremvc:v3 .
# docker run -p 5001:4500 --name dockeraspnetcoremvc-container-1 dockeraspnetcoremvc:v2
# docker run -d -p 5002:4500 --name dockeraspnetcoremvc-container-2 dockeraspnetcoremvc:v2
# docker rm c52 79b --force



####################################################################################################################################



## docker pull mcr.microsoft.com/dotnet/sdk:3.1
#FROM mcr.microsoft.com/dotnet/sdk:3.1
#WORKDIR /app
#COPY . .
#RUN dotnet restore
#RUN dotnet publish DockerAspNetCoreMvc.csproj -c Release -o out
#WORKDIR out
#ENV ASPNETCORE_URLS="http://*:4500"
#ENTRYPOINT ["dotnet", "DockerAspNetCoreMvc.dll"]


# docker build -t dockeraspnetcoremvc:v2 .
# docker run -p 5001:4500 --name dockeraspnetcoremvc-container-1 dockeraspnetcoremvc:v2
# docker run -d -p 5002:4500 --name dockeraspnetcoremvc-container-2 dockeraspnetcoremvc:v2
# docker rm c52 79b --force



####################################################################################################################################



## docker pull mcr.microsoft.com/dotnet/aspnet:3.1
#FROM mcr.microsoft.com/dotnet/aspnet:3.1
#WORKDIR /app
#COPY /bin/Release/netcoreapp3.1/publish /app/
#ENTRYPOINT ["dotnet", "DockerAspNetCoreMvc.dll"]


# docker build -t dockeraspnetcoremvc:v1 .

# cls

# docker run -p 5001:80 dockeraspnetcoremvc:v1
# docker run -d -p 5002:80 dockeraspnetcoremvc:v1
# docker run -d --name dockeraspnetcoremvc-container-3 -p 5003:80 dockeraspnetcoremvc:v1
# docker ps
# docker stop da3
# docker rm da3
# docker ps -a
# docker rm ac8 --force
# docker ps



####################################################################################################################################



#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

#FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
#WORKDIR /app
#EXPOSE 80
#EXPOSE 443

#FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
#WORKDIR /src
#COPY ["DockerAspNetCoreMvc/DockerAspNetCoreMvc.csproj", "DockerAspNetCoreMvc/"]
#RUN dotnet restore "DockerAspNetCoreMvc/DockerAspNetCoreMvc.csproj"
#COPY . .
#WORKDIR "/src/DockerAspNetCoreMvc"
#RUN dotnet build "DockerAspNetCoreMvc.csproj" -c Release -o /app/build

#FROM build AS publish
#RUN dotnet publish "DockerAspNetCoreMvc.csproj" -c Release -o /app/publish

#FROM base AS final
#WORKDIR /app
#COPY --from=publish /app/publish .
#ENTRYPOINT ["dotnet", "DockerAspNetCoreMvc.dll"]