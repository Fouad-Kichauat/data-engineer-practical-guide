# How to get started

1. Install docker and docker-compose

2. Change docker-compose.yml-file (line 71): using following logic:
    - M1-based mac: `image: 'pettenge/nifi-arm64:1.13.2'`
    - Intel-based pc/mac: `image: 'apache/nifi:latest'`
3. Run: `docker-compose up -d`
