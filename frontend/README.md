# Frontend — MapLibre GL JS + Vite

## Cara Menjalankan (Development)

```bash
cd frontend
npm install
npm run dev
```

Buka: http://localhost:3000

## Build untuk Production

```bash
npm run build
# Output di folder: dist/
```

## Fitur Peta
- Basemap: OpenStreetMap, Satelit, Dark Mode
- Layer titik penting Balikpapan + IKN (data GeoJSON)
- WMS Layer dari GeoServer (aktifkan setelah docker berjalan)
- Popup informasi saat klik marker
- Koordinat kursor real-time

## Struktur File
```
frontend/
├── index.html        ← Peta utama (MapLibre GL JS)
├── package.json
├── vite.config.js
└── dist/             ← hasil build (auto-generate)
```

## Menghubungkan ke GeoServer

Edit bagian WMS di `index.html`:
```javascript
const WMS_URL = 'http://localhost:8080/geoserver/oikn/wms';
const LAYER   = 'oikn:titik_penting';  // workspace:layer
```

Ganti sesuai workspace dan nama layer yang kamu buat di GeoServer.
