# Step 1: Use the legacy SDK image that natively understands project.json
FROM microsoft/dotnet:1.0.1-sdk-projectjson AS build

WORKDIR /app

# Copy your existing project file structure 
COPY src/Hello/project.json ./

# This will now successfully restore dependencies via project.json
RUN dotnet restore

COPY . .

RUN dotnet publish -c Release -o out

# Step 2: Use the matching 1.0 runtime to keep the final image clean
FROM microsoft/dotnet:1.0.5-runtime

WORKDIR /app

COPY --from=build /app/out .

EXPOSE 8080

CMD ["dotnet", "hello.dll"]
