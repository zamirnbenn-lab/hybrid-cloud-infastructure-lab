# Architecture

The environment follows a basic 3-tier design with separate web, application, and data layers.

Traffic follows this path:

Internet → Web VM → App Service → PostgreSQL VM

The web tier runs Nginx on an Ubuntu VM and handles traffic coming into the environment.

The application tier runs through Azure App Service. It handles the backend logic and communicates with the database.

PostgreSQL runs on a separate Ubuntu VM in the data subnet. The web server does not connect directly to the database. Requests that need data go through the application tier instead.

Keeping each part separate makes it easier to control traffic and gives each resource one main purpose.
