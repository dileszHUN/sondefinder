# 🎈 SondeFinder

**Magyar** | [English](#english)

## Magyar

A **SondeFinder** egy egyszerű, magyar nyelvű, böngészőben futó rádiószonda-kereső weboldal. A [SondeHub](https://sondehub.org/) online API-jából kér le szondaészleléseket a megadott hely közelében, majd térképen és távolság szerint rendezett listában jeleníti meg őket.

A projekt jelenleg **egyetlen `index.html` fájlból áll**: nincs szükség PHP-ra, saját adatbázisra vagy külön szerveroldali programra. Statikus webtárhelyen, például GitHub Pages-en is használható.

### Funkciók

- 📍 **Saját helyzet** lekérése a böngésző helymeghatározásával, illetve földrajzi szélesség és hosszúság kézi megadása.
- 🔎 **Keresési sugár:** 10, 25, 50, 75 vagy 100 km.
- 📅 **Időszak:** az utolsó 1, 3 vagy 7 nap; egyéni kezdő- és záródátum az elmúlt 7 napon belül.
- 📏 **Magasságszűrés** az utolsó mért magasság alapján.
- 🎈 **SondeHub-adatok:** sorozatszám, szondatípus (ha ismert), időpont, koordináták, magasság és frekvencia (ha elérhető).
- ✅ **Megtalálási bejelentések ellenőrzése**, valamint a bejelentetten megtalált szondák elrejtése.
- 🗺️ **Interaktív térkép** Leaflet és OpenStreetMap használatával, tartalék térképcsempe-forrással.
- 📍 **Távolság szerinti lista**, Google Maps navigációs hivatkozás és SondeHub-adatlap.
- ⚠️ **Hiba- és állapotjelzések**, ha egy API-kérés vagy a megtalálási állapot ellenőrzése nem sikerül.

### Használat

1. Nyisd meg a közzétett weboldalt.
2. Kattints a **„Saját helyzet”** gombra, vagy add meg a koordinátákat kézzel.
3. Válaszd ki a keresési sugarat, az időszakot és a magasságszűrőt.
4. Kattints a **„Szondák keresése”** gombra.
5. Válassz a találati listából; nézd meg a szondát a térképen, vagy nyisd meg a navigációt.

A kezdő koordináták előre ki vannak töltve, de szabadon módosíthatók. A GPS-helymeghatározáshoz a böngésző engedélye és **HTTPS** szükséges (a `localhost` fejlesztői kivétel). A kézi koordináták GPS-engedély nélkül is használhatók.

### Telepítés GitHub Pages-re

1. Hozz létre egy **nyilvános** GitHub repositoryt (például `sondefinder`).
2. Töltsd fel az **`index.html`** fájlt a repository gyökérkönyvtárába.
3. A repositoryban válaszd: **Settings → Pages → Build and deployment → Deploy from a branch**.
4. Állítsd be: **`main` → `/(root)`**, majd mentsd el.
5. A közzétett cím például: `https://FELHASZNALONEV.github.io/sondefinder/`.

Frissítéskor a GitHubon cseréld le az `index.html` fájlt és végezz **Commit changes** műveletet. A GitHub Pages ezután automatikusan újra közzéteszi az oldalt.

### Fontos korlátok

- Az alkalmazás a SondeHub **élő `/sondes` API-ját** használja: **nem teljes, többéves rádiószonda-archívum**. A kezelőfelület legfeljebb az utolsó 7 napra enged keresni.
- A **„nincs megtalálási bejelentés” nem jelenti azt**, hogy a szonda biztosan a terepen van. Ha az ellenőrzés sikertelen, az állapot nem ellenőrzöttként jelenhet meg.
- A térképen megjelenített hely **az utolsó észlelt pozíció**, nem feltétlenül a tényleges földet érési pont.
- Internetkapcsolat és a SondeHub API elérhetősége szükséges. A közvetlen böngészős API-kérések működése a szolgáltató CORS-beállításaitól is függ.
- A SondeFinder tájékoztató célú keresőeszköz; a terepi megközelítésnél tartsd tiszteletben a magánterületet, a természetvédelmi területeket és a biztonsági szabályokat.

### Felhasznált szolgáltatások

- [SondeHub](https://sondehub.org/) – szondaészlelések és megtalálási bejelentések (`https://api.v2.sondehub.org/sondes` és `/recovered`).
- [Leaflet](https://leafletjs.com/) – interaktív térkép.
- [OpenStreetMap](https://www.openstreetmap.org/copyright) – térképadatok és alaptérkép; szükség esetén tartalék Esri-csempék.

---

<a id="english"></a>
## English

**SondeFinder** is a lightweight, Hungarian-language radiosonde finder that runs directly in a web browser. It retrieves online observations from the [SondeHub](https://sondehub.org/) API for a selected location and displays matching radiosondes on an interactive map and in a list sorted by distance.

The project consists of **a single `index.html` file**. No PHP, database, or custom backend is required. It can be hosted on any suitable static web host, including GitHub Pages.

### Features

- 📍 **Use your current location** through the browser's geolocation API, or enter latitude and longitude manually.
- 🔎 **Search radius:** 10, 25, 50, 75, or 100 km.
- 📅 **Time filters:** last 1, 3, or 7 days, or custom dates within the past 7 days.
- 📏 **Altitude filter** based on the last reported altitude.
- 🎈 **SondeHub information:** serial number, radiosonde type (if known), observation time, coordinates, altitude, and frequency (where available).
- ✅ **Recovery report checks**, with an option to hide radiosondes reported as recovered.
- 🗺️ **Interactive map** powered by Leaflet and OpenStreetMap, with a fallback tile source.
- 📍 **Distance-sorted results**, Google Maps directions, and links to SondeHub radiosonde pages.
- ⚠️ **Clear status and error messages** when API requests or recovery checks fail.

### How to use

1. Open the published website.
2. Select **“📍 Saját helyzet” (My location)**, or enter coordinates manually.
3. Choose the search radius, time range, and altitude filter.
4. Click **“🔎 Szondák keresése” (Search radiosondes)**.
5. Select a result to view it on the map, open directions, or view its SondeHub page.

Initial coordinates are prefilled but editable. Browser-based geolocation requires permission and **HTTPS** (`localhost` is an exception for local development). Manual coordinate entry works without GPS access.

### Deploy to GitHub Pages

1. Create a **public** GitHub repository (for example, `sondefinder`).
2. Upload **`index.html`** to the repository root.
3. Go to **Settings → Pages → Build and deployment → Deploy from a branch**.
4. Select **`main` → `/(root)`** and save.
5. Your website URL will look like `https://USERNAME.github.io/sondefinder/`.

To update the website, replace `index.html` on GitHub and **commit the changes**. GitHub Pages will redeploy automatically.

### Important limitations

- The application queries SondeHub's **live `/sondes` endpoint**; it is **not a complete multi-year historical archive**. The interface limits searches to the most recent 7 days.
- **No recovery report does not mean a radiosonde is definitely still on the ground.** If a recovery check fails, its status may be shown as unverified.
- Map markers indicate the **last observed position**, which may differ from the actual landing location.
- Internet access and a functioning SondeHub API are required. Direct browser requests may also depend on the provider's CORS configuration.
- This is an informational tool. Please respect private property, protected areas, and safety requirements while searching in the field.

### Services and attribution

- [SondeHub](https://sondehub.org/) – radiosonde observations and recovery reports (`https://api.v2.sondehub.org/sondes` and `/recovered`).
- [Leaflet](https://leafletjs.com/) – interactive mapping.
- [OpenStreetMap](https://www.openstreetmap.org/copyright) – base maps and map data; Esri tiles are used as a fallback when needed.

---

**SondeFinder** · A simple, single-file online radiosonde search interface.
