FROM mcr.microsoft.com/dotnet/sdk:5.0

# Install 'ps' as it is missing from the base image and omnisharp-vscode needs it:
RUN apt-get update && \
    apt-get install -y procps

# Create non-core user
RUN groupadd -g 1500 -r repro && \
    useradd -u 1500 -r -g repro -m -s $(which bash) repro

RUN mkdir /workspace

COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
