# 🌍 Nation Info — Country Dashboard

A modern **Country Information Dashboard** built using **Vite + Tailwind CSS + Vanilla JavaScript**.

This project displays detailed information about countries including population, region, borders, interactive map location, and **live GDP data** fetched from the World Bank API.

-----

## 🚀 Features

- 🌎 Browse and search countries
- 📊 View detailed country information
- 🗺 Interactive map using Leaflet.js
- 🌐 Border country navigation
- 🌙 Dark mode support
- 💰 Live GDP (Nominal, Current USD) integration
- ⚡ In-memory caching for GDP API calls
- 📱 Fully responsive design

-----

## 🛠 Tech Stack

- **Vite** – Development server & bundler  
- **Tailwind CSS** – Utility-first styling  
- **Vanilla JavaScript (ES Modules)** – API handling & dynamic rendering  
- **Leaflet.js** – Interactive map integration  
- **World Bank API** – Live GDP data source  

-----

## 📂 Project Structure

```
Nation-Info/
│
├── index.html
├── package.json
├── tailwind.config.js
├── postcss.config.js
│
└── src/
    ├── app.js
    └── style.css
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone <your-repository-url>
cd Nation-Info
```

---

### 2️⃣ Install Dependencies

```bash
npm install
```

This installs:

- vite
- tailwindcss
- postcss
- autoprefixer

-----

### 3️⃣ Run Development Server

```bash
npm run dev
```

You will see:

```
VITE vX.X.X ready in XXX ms
Local: http://localhost:5173/
```

Open the provided URL in your browser.

---

### 4️⃣ Build for Production

```bash
npm run build
```

To preview production build:

```bash
npm run preview
```

---

# 🌐 APIs Used

## 1️⃣ REST Countries Dataset (Static JSON)

Dataset Source:

https://raw.githubusercontent.com/the-user01/rest-countries-frontend-mentor/main/data.json

Used for:

- Country name
- Population
- Region & Subregion
- Capital
- Borders
- Currencies
- Languages
- Coordinates
- Flag images

This is a static JSON dataset (no backend required).

---

## 2️⃣ World Bank API (Live GDP)

Indicator Used:

```
NY.GDP.MKTP.CD
```

Endpoint Format:

```
https://api.worldbank.org/v2/country/{ISO2}/indicator/NY.GDP.MKTP.CD?format=json&per_page=5
```

Example:

```
https://api.worldbank.org/v2/country/IN/indicator/NY.GDP.MKTP.CD?format=json&per_page=5
```

Used For:

- Fetching latest available GDP (Nominal, Current USD)
- Dynamically displaying GDP in country detail view

### GDP Integration Logic

- Uses ISO2 country code (`alpha2Code`)
- Fetches latest non-null GDP value
- Formats large numbers into readable format:
  - Trillion
  - Billion
  - Million
- Implements in-memory caching to prevent duplicate API calls
- Handles loading state and API errors gracefully

Example Display:

```
GDP (2024): $3.91 Trillion
```

---

## 🧠 How It Works

1. The app loads the static country dataset.
2. When a country is selected:
   - Basic information renders instantly.
   - GDP API request is triggered.
3. A loading indicator is shown while fetching GDP.
4. The GDP value is formatted and displayed.
5. The result is cached to avoid repeated API calls.

---

## 🧪 Testing GDP Integration

To verify everything works:

1. Run:

```bash
npm run dev
```

2. Click on:
   - India
   - United States
   - China
   - Germany

3. Confirm GDP loads correctly.
4. Open DevTools → Network → Confirm World Bank API request.
5. Click the same country twice → confirm cached result (no duplicate API call).

---

## 🔮 Future Improvements

- Add GDP per capita
- Add GDP growth rate
- Add historical GDP chart
- Compare two countries side-by-side
- Add military & defense budget integration

---

## 👨‍💻 Author

Built as a frontend dashboard project to demonstrate:

- API integration
- Asynchronous rendering
- State management
- Third-party library integration
- Real-world data handling

-----

## 📄 License

This project is for educational and portfolio purposes.
