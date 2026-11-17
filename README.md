# fuel-cost-estimator-web

Prebuilt static bundle of the Fuel Cost Estimator web app. No build step required.

## Deploy

**Vercel:** import this repo, framework preset = Other, build command = empty, output directory = `.` (repo root). `vercel.json` adds the SPA rewrite.

**Netlify:** drag this folder into Netlify Drop, or import the repo with build command empty and publish directory `.`. `_redirects` handles the SPA fallback.

**Any static host / S3 / GitHub Pages:** upload the contents of this repo as-is.

## Pointing at your API

The API base URL is read at runtime from `config.js`:

```js
window.__FCE_API_BASE__ = "https://your-api.example.com/v1";
```

Edit `config.js` after deploying (no rebuild needed). If left empty it falls back to `http://localhost:3000/v1`.

The API must allow the deployed origin via `APP_ORIGIN` (CORS), e.g. `APP_ORIGIN=https://your-app.vercel.app`.
