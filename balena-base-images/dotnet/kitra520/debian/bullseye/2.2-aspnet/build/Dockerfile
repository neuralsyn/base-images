# AUTOGENERATED FILE
FROM balenalib/kitra520-debian:bullseye-build

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates \
        curl \
        \
# .NET Core dependencies
        libc6 \
        libgcc1 \
        libgssapi-krb5-2 \
        libicu57 \
        liblttng-ust0 \
        libssl1.0.2 \
        libstdc++6 \
        zlib1g \
    && rm -rf /var/lib/apt/lists/*

# Configure web servers to bind to port 80 when present
ENV ASPNETCORE_URLS=http://+:80 \
    # Enable detection of running in a container
    DOTNET_RUNNING_IN_CONTAINER=true

# Install .NET Core
ENV ASPNETCORE_VERSION 2.2.8

RUN curl -SL --output aspnetcore.tar.gz "https://dotnetcli.blob.core.windows.net/dotnet/aspnetcore/Runtime/$ASPNETCORE_VERSION/aspnetcore-runtime-$ASPNETCORE_VERSION-linux-arm.tar.gz" \
    && aspnetcore_sha512='fab9a1d9d101716337bb153af2ac36429fc387230c0c0bf2d639b31fb7f787bc8dbaaa31f28f9cbe69f117ffc78d8ddb5a5968da0e77785d3c12c6814ef50f7b' \
    && echo "$aspnetcore_sha512  aspnetcore.tar.gz" | sha512sum -c - \
    && mkdir -p /usr/share/dotnet \
    && tar -zxf aspnetcore.tar.gz -C /usr/share/dotnet \
    && rm aspnetcore.tar.gz \
    && ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet

CMD ["echo","'No CMD command was set in Dockerfile! Details about CMD command could be found in Dockerfile Guide section in our Docs. Here's the link: https://balena.io/docs"]

 RUN curl -SLO "https://raw.githubusercontent.com/balena-io-library/base-images/8accad6af708fca7271c5c65f18a86782e19f877/scripts/assets/tests/test-stack@dotnet.sh" \
  && echo "Running test-stack@dotnet" \
  && chmod +x test-stack@dotnet.sh \
  && bash test-stack@dotnet.sh \
  && rm -rf test-stack@dotnet.sh