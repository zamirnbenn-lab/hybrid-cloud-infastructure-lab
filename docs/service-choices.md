# Service Choices

The web tier uses an Ubuntu VM running Nginx. I wanted direct experience managing a cloud server, including Linux services, packages, SSH, networking, and Nginx configuration.

The application tier uses Azure App Service instead of another VM. A second VM would have repeated a lot of the same server administration work, and I already got experience with that in my last lab. I wanted to take a different approach with this project. App Service gives me experience with a managed Azure service alongside the VMs and lets Azure handle more of the underlying platform.

The backend will run through App Service and connect to PostgreSQL over the private Azure network.

PostgreSQL runs on an Ubuntu VM. I originally looked at Azure Database for PostgreSQL, but my Azure student subscription would not allow me to deploy it in the same region as the rest of the environment. Most of the available regions were outside the US and rather than split the environment across unrelated regions, I decided to run PostgreSQL on a VM and keep everything in the same VNet. 
