# Stage 1: Build
FROM msimons/dotnet:1.0-sdk AS build

WORKDIR /app

COPY src/Hello/project.json ./src/Hello/

WORKDIR /app/src/Hello

RUN dotnet restore project.json

WORKDIR /app

COPY . .

WORKDIR /app/src/Hello

RUN dotnet publish -c Release -o /app/out


# Stage 2: Runtime
FROM msimons/dotnet:1.0-runtime

WORKDIR /app

COPY --from=build /app/out .

EXPOSE 8080

CMD ["dotnet", "Hello.dll"]