DE microsoft / dotnet: 2.2-sdk AS build
WORKDIR / app

# Copiar csproj e restaurar como camadas distintas
COPIAR * .csproj ./
RUN restauração dotnet

# Copie todo o resto e construa
COPY . ./
EXECUTAR dotnet publish -c Release -o out

# Build runtime image
DE microsoft / dotnet: 2.2-aspnetcore-runtime AS runtime

WORKDIR / app

COPY --from = build / app / out.

ENTRYPOINT [ "dotnet" , "publisher_api.dll" ]