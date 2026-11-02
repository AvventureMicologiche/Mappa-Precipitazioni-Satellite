# Foto dal satellite della Mappa Pluviometrica

Tessere WebP 256×256 della foto dal satellite usata dalla mappa
(https://precipitazioni.avventuremicologiche.it) sotto la pioggia e le previsioni,
dallo zoom 4 al 10, in `europa/{z}/{x}/{y}.webp` (Europa da 25° O a 45° E, da 34° N a 72° N).
Oltre lo zoom 10 la mappa usa un'altra foto.

**Dato derivato e rigenerabile.** Il repo tiene un commit solo e si sovrascrive;
il sito punta sempre a un commit preciso, servito da jsDelivr.

## Fonti e licenze

- **NASA Blue Marble Next Generation** con il rilievo del fondale (luglio 2004),
  NASA Earth Observatory, Reto Stöckli. Pubblico dominio.
  Zoom 4-8 e tutto il mare.
- **ESA WorldCover 2021, Sentinel-2 RGBNIR**: © ESA WorldCover project 2021 /
  Contains modified Copernicus Sentinel data (2021) processed by ESA WorldCover
  consortium. Licenza CC BY 4.0. La terra agli zoom 9 e 10.

I colori sono stati ritoccati per somigliare alla foto del resto della mappa.

## Come si rigenera

Dal banco di lavoro (`D:\video youtube\claudio\mockup-pluvio-104\`):

1. `satellite-europa.py gradi`, poi `z10` e `acqua`: la terra ESA (zoom 10 e piramide).
2. `blue-marble.py calibra`, poi `tutto` con `SAT_BOX="-25,34,45,72"`: Blue Marble e il
   montaggio con ESA.
3. Si copia `tessere\bm\` in `europa/`, un commit solo, push forzato, e nel sito il
   commit nuovo.
