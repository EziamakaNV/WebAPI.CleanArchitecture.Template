#See https://aka.ms/customizecontainer to learn how to customize your debug container and how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["Directory.Build.props", "."]
COPY ["WebAPI.CleanArchitecture.Template/WebAPI.CleanArchitecture.Template.csproj", "WebAPI.CleanArchitecture.Template/"]
RUN dotnet restore "WebAPI.CleanArchitecture.Template/WebAPI.CleanArchitecture.Template.csproj"
COPY . .
WORKDIR "/src/WebAPI.CleanArchitecture.Template"
RUN dotnet build "WebAPI.CleanArchitecture.Template.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebAPI.CleanArchitecture.Template.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebAPI.CleanArchitecture.Template.dll"]