# MyMaCo Setup Guide

Welcome to the setup documentation for MyMaCo. This guide outlines the necessary configurations for deploying both the Main Image and the Sync Image. MyMaCo utilizes a PostgreSQL database for its core operations.

## Main Image Setup

Before deploying any supplementary services, you must first set up the Main Image. This container requires the following environment variables to successfully connect to your PostgreSQL database.

### Required Environment Variables

*   `MYMACO_DB_HOST` - The hostname or IP address of your database.
*   `MYMACO_DB_PORT` - The port used by your database (typically 5432).
*   `MYMACO_DB_DATABASE` - The name of your MyMaCo database.
*   `MYMACO_DB_USER` - The username for database access.
*   `MYMACO_DB_PASSWORD` - The password for the database user.
*   `MYMACO_ENCRYPTION_KEY` - Encryption Key for storing passwords.

### Network & Port Configuration
By default, the MyMaCo Main Image runs on port **8080**. When deploying for production, we strongly recommend using a reverse proxy (such as Nginx, Caddy, or Traefik) in front of the application to securely expose it over **HTTPS**.

---

## Sync Image Setup

The MyMaCo Sync Image is designed specifically for extracting data from n8n. 

### Prerequisites

Before running the Sync Image, ensure you have completed the following:
1.  **Main Image:** Make sure you have successfully set up and started the main MyMaCo Image first.
2.  **n8n Configuration:** You need to add an n8n environment in the MyMaCo settings before this Sync container will actively do anything.

### Required Environment Variables

The Sync Image needs to connect to the exact same PostgreSQL database as the main application. Therefore, the following environment variables **must** match the ones you set for the Main Image:

*   `MYMACO_DB_HOST`
*   `MYMACO_DB_PORT`
*   `MYMACO_DB_DATABASE`
*   `MYMACO_DB_USER`
*   `MYMACO_DB_PASSWORD`
*   `MYMACO_ENCRYPTION_KEY`

### Optional Environment Variables

*   `MYMACO_WORKER_ENV` 
    *   **Description:** This variable should be set if you want to sync a specific environment on this particular Sync Container.
    *   **Use Case:** This is highly useful if you have multiple n8n environments and want to scale by using specific, dedicated workers to SYNC them individually. 
    *   **Default Behavior:** If nothing is set for this variable, the container will automatically loop through all of the n8n environments available in your settings.
