# Networking

The Azure VNet uses the 10.20.0.0/16 address space.

My pfSense homelab already uses networks in the 192.168.x.x range, so I used a different range for Azure. I plan on connecting the two later in the project so using different addresses will make that easier down the line.
The VNet is split into four subnets:

![VNet Subnets](images/networking/vnet-subnets.png)

snet-web is used for the Ubuntu VM running Nginx. 

snet-app is dedicated to Azure App Service VNet Integration with a delegation to Microsoft.Web/serverFarms. 

snet-data is used for the PostgreSQL VM so the database can stay separated from the web and application tiers.

snet-management is kept separate for administrative access. I originally planned to place a management VM there, but because I use a Azure student subscription, I hit my quota. However, I still plan on utilizing this subnet and will deploy it in the future.

