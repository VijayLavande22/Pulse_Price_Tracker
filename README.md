# Pulse Price Tracker

Pulse Price Tracker is a Flask-based web application that helps users search products, compare prices from multiple sources, and view the best available offers in one place. It is designed as a simple price-comparison project with support for live providers, demo data, and saved search history using MySQL.

## Features

- Search products from a clean web interface
- Compare offers from multiple data providers
- Show lowest-price results first
- Highlight price savings where available
- Support demo data when live API keys are not configured
- Save product search history in MySQL
- Expose both web pages and JSON API endpoints

## Tech Stack

- Python
- Flask
- MySQL
- HTML, CSS, JavaScript
- SerpApi
- DataForSEO

## Project Structure

```text
.
|-- app.py
|-- database.sql
|-- requirements.txt
|-- data/
|   `-- demo_products.json
|-- static/
|   |-- app.js
|   `-- styles.css
|-- templates/
|   |-- history.html
|   `-- index.html
`-- src/
    `-- pricepulse_compare/
        |-- __init__.py
        |-- database.py
        |-- models.py
        |-- rate_limit.py
        |-- settings.py
        `-- services/
            |-- search_service.py
            `-- providers/
                |-- base.py
                |-- dataforseo_provider.py
                |-- demo_provider.py
                `-- serpapi_provider.py
```

## Setup

1. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

2. Create your environment file:

   ```bash
   copy .env.example .env
   ```

3. Update `.env` with your local configuration.

4. Start MySQL and make sure your database settings are correct.

5. Run the application:

   ```bash
   python app.py
   ```

6. Open the app in your browser:

   ```text
   http://127.0.0.1:5000
   ```

## Environment Variables

This project uses `.env` for local secrets and configuration.

Common values include:

- `DATA_PROVIDERS`
- `SERPAPI_KEY`
- `DATAFORSEO_LOGIN`
- `DATAFORSEO_PASSWORD`
- `MYSQL_HOST`
- `MYSQL_PORT`
- `MYSQL_USER`
- `MYSQL_PASSWORD`
- `MYSQL_DATABASE`

`.env` is ignored by Git, so your local secrets are not uploaded to GitHub. Use `.env.example` as the shareable template.

## API Endpoints

- `GET /`
  Main web interface
- `GET /api/search?q=product-name`
  Return search results in JSON format
- `GET /search-history`
  Show saved search history in the browser
- `GET /api/search-history`
  Return saved search history in JSON format
- `GET /health`
  Health check endpoint

## Notes

- Demo data allows the project to run even without paid API credentials.
- MySQL is used for storing searched product history.
- This repository is safe to push as long as you do not manually add `.env`.

## Author

Developed by Vijay Lavande.
