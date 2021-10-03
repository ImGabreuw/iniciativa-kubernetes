FROM mcr.microsoft.com/dotnet/sdk:5.0 AS builder
WORKDIR /source
COPY *.sln .
COPY ConversaoPeso.Web/*.csproj ./ConversaoPeso.Web/
RUN dotnet restore

COPY ConversaoPeso.Web/. ./ConversaoPeso.Web/
WORKDIR /source/ConversaoPeso.Web
RUN dotnet publish -c release -o /app --no-restore

FROM mcr.microsoft.com/dotnet/aspnet:5.0
WORKDIR /app
COPY --from=builder /app ./
ENTRYPOINT ["dotnet", "ConversaoPeso.Web.dll"]