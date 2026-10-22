# Networking

The Azure VNet uses the 10.20.0.0/16 address space.

My pfSense homelab already uses networks in the 192.168.x.x range, so I used a different range for Azure. I plan on connecting the two later in the project so using different addresses will make that easier down the line.
The VNet is split into four subnets:

- snet-web - 10.20.10.0/24
- snet-app - 10.20.20.0/24
- snet-data - 10.20.30.0/24
- snet-management - 10.20.40.0/24

Each tier has its own subnet instead of putting everything on one network. This gives me more control over which systems can communicate with each other.

snet-app is dedicated to Azure App Service VNet Integration. App Service does not attach to the network like a normal VM, so the subnet is delegated to Microsoft.Web/serverFarms. This lets the application reach private resources inside the VNet, including the PostgreSQL server.

snet-management is kept separate for administrative access. I originally planned to place a management VM there, but because I use a Azure student subscription, I hit my quota. However, I still plan on utilizing this subnet and will deploy it in the future.
