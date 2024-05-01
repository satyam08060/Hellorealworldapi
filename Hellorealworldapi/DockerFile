FROM mcr.microsoft.com/dotnet/sdk:8.0 As build

COPY *.csproj ./
RUN dotnet restore
COPY . .
RUN dotnet publish -c Release -o out
FROM mcr.microsoft.com/dotnet/sdk:8.0 As build
WORKDIR /app
COPY --from=build /app/out ./
EXPOSE 80
ENTRYPOINT ["dotnet","Hellorealworldapi.dll"]