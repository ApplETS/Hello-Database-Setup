# Databases Setup Guide

To create the database simply clone this repository and do these command:
1. Clone the repo and navigate in a terminal to the directory.
2. Copy `.env.template` into `.env` and modify the values according to your need. (Keep in mind theses values will be used to create the DB and will be needed to connect to the DB). You can keep the default values for a local development setup. 
4. Run this in a terminal: `docker compose -f .\bd-compose.yml up -d`

And that's it, you have a database running on your machine! This will look a bit like this:
![Docker look into database](image.png)

You can then set your connection string in both your project with theses values:
```
# Pour ps
User ID=$POSTGRES_USER;Password=$POSTGRES_PASSWORD;Host=host.docker.internal;Port=5432;Database=ps;

# Pour pfe
User ID=$POSTGRES_USER;Password=$POSTGRES_PASSWORD;Host=host.docker.internal;Port=5432;Database=pfe;
```

## Access using Adminer

To access the adminer, navigate to `localhost:8090` and use the following credentials:
- System: `PostgreSQL`
- Server: `host.docker.internal`
- Username: `$POSTGRES_USER`
- Password: `$POSTGRES_PASSWORD`
- Database: `$POSTGRES_DB`
