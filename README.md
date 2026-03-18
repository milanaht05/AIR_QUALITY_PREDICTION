# Air Quality Prediction

A Django-based air quality analytics and prediction platform with live dashboards, global maps, and AQI forecasting.

## Project structure

- `analytics/`: main Django app containing models, views, REST API, and templates.
- `pollu/`: Django project settings and URL configuration.
- `files/`: static assets (CSS, JS, admin resources).
- `env/`: Python virtual environment for dependencies.

## Features

- Live AQI dashboard (charts + metrics)
- City and location-specific pollution search
- Global heatmap of air quality
- Periodic AQI updates via management command
- REST API endpoints for integration

## Quick start

1. Create/activate the virtual environment
   ```powershell
   .\env\Scripts\activate
   ```

2. Install dependencies
   ```powershell
   pip install -r analytics\requirements.txt
   ```

3. Apply migrations
   ```powershell
   cd analytics
   python manage.py migrate
   ```

4. Start development server
   ```powershell
   python manage.py runserver
   ```

5. Open in browser
   http://127.0.0.1:8000/

## Update AQI data

Run scheduled update command (or hook to cron/task scheduler):
```powershell
python manage.py update_aqi
```

## API endpoints

- `GET /api/pollutiondata/` - list pollution data
- `GET /api/pollutiondata/<id>/` - detail

## Notes

- Ensure API keys (if used) are configured in `analytics/settings.py` or environment variables.
- If adding new cities/lon-lat points, update model migrations then run `migrate` and restart server.

## Contributors

- Milanaht05

