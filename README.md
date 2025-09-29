# Mihomo Proxy Tool User Guide

Mihomo is a high-performance proxy tool designed for command-line environments, supporting Clash configuration format, allowing you to easily use proxy services in the terminal.

## Installation

```bash
git clone https://github.com/potentialming/mihomo.git
```

## Quick Start

### 1. Prepare Configuration File

#### Get Existing Configuration from Clash
If you're already using Clash, you can directly copy the existing configuration:

![Clash Configuration](images/clash.png)

1. Open Clash client
2. Click on "Subscriptions" or "Profiles" option on the left
3. Find the subscription configuration you want to use
4. Right-click on that subscription
5. Select "Edit File"
6. Select all configuration content (Ctrl+A) and copy (Ctrl+C)
7. Paste the copied content into the `config.yaml` file in the project directory

### 2. Start Proxy Service
```bash
# Navigate to project directory
cd /path/to/mihomo

# Add execution permission to the program
chmod +x ./mihomo-linux-amd64-v1.18.1

# Start mihomo (note there's a space after -d .)
./mihomo-linux-amd64-v1.18.1 -d . 
```

### 3. Configure System Proxy
**Open a new terminal**, set environment variables (port number should match the configuration in config.yaml):
```bash
export https_proxy=http://127.0.0.1:7890/
export http_proxy=http://127.0.0.1:7890/
```

### 4. Verify Proxy
```bash
# Test if proxy is working
wget www.google.com
```

## File Description
- `mihomo-linux-amd64-v1.18.1` - Main program file
- `config.yaml` - Configuration file (needs to be replaced with your configuration)
- `Country.mmdb` - GeoIP database
- `GeoSite.dat` - Domain rules database

## Important Notes
- Ensure port 7890 is not occupied by other programs
- Configuration file format must comply with mihomo specifications
- Proxy settings are only effective in the current terminal session

## Stop Service
Press `Ctrl+C` in the terminal running mihomo to stop the service.