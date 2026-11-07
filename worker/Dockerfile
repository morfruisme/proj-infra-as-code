FROM --platform=$BUILDPLATFORM mcr.microsoft.com/dotnet/sdk:8.0

ARG BUILDPLATFORM
ARG TARGETPLATFORM
ARG TARGETARCH
RUN echo "build: $BUILDPLATFORM\n target: $TARGETPLATFORM ($TARGETARCH)"

WORKDIR /source
COPY Worker.csproj Program.cs .
RUN dotnet restore -a $TARGETARCH
RUN dotnet publish -c release -o /app -a $TARGETARCH --self-contained false --no-restore

WORKDIR /app
CMD ["dotnet", "Worker.dll"]
