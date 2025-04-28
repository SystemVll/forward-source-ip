# 🔄 Source-Preserving Port Forwarding Tool

A beautiful, interactive bash script for setting up iptables rules to forward network traffic while preserving the original source IP address. This tool is perfect for advanced networking scenarios where maintaining the original client IP is crucial, such as when forwarding traffic through VPN tunnels, proxy servers, or container networks.

## ✨ Features

- **Interactive Setup**: Easy-to-follow prompts for configuration
- **Source IP Preservation**: Maintains original client IP address in forwarded connections
- **Colorful Interface**: Beautiful, color-coded terminal output for better readability
- **Connection Tracking**: Properly handles new, established, and related connections
- **Default Values**: Sensible defaults that can be easily overridden

## 🚀 One-Line Command

```bash
curl -s https://raw.githubusercontent.com/SystemVll/forward-source-ip/main/setup.sh | bash
```

## 🔧 How It Works

The script creates a complete set of iptables rules to:

1. Forward new TCP connections on the specified port
2. Allow established/related connections in both directions
3. Set up DNAT (Destination NAT) to redirect traffic
4. Configure SNAT (Source NAT) to preserve the original source IP

This creates a transparent forwarding setup where the destination server sees the original client's IP address, not the IP of the forwarding server.

## 📋 Configuration Options

- **Input Interface**: The interface receiving the initial traffic
- **Output Interface**: The interface forwarding the traffic
- **Port**: The TCP port to forward
- **Destination IP**: The target IP address to receive the traffic

## 🔒 Security Considerations

This script uses `iptables-legacy` which may require root privileges. Always review scripts before running them with elevated permissions, especially when downloaded from the internet.
